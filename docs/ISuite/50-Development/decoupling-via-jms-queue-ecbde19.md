<!-- loioecbde19b7d184f5e8528a936f0d5f780 -->

# Decoupling via JMS Queue

The scenario described in this topic is similar to the scenarios [Sender and Receiver with SAP RM Protocol](sender-and-receiver-with-sap-rm-protocol-9f3e2b6.md) and [Sender and Receiver with SOAP Protocol](sender-and-receiver-with-soap-protocol-cd4c6e0.md). There's the following difference: The middleware needs to carry out the retry of the message delivery if there's an error.

The following use cases require such a behavior:

-   The sender system isn't able to retry messages.

-   The sender system requires a fast response to avoid potential timeouts.


The following assumptions apply for the design of this scenario:

-   It implements the communication between exactly 1 sender and 1 receiver.

-   The sender doesn't retry messages.

    Therefore, the middleware \(Cloud Integration\) needs to carry out the retry of the message delivery if there's an error.

-   The receiver is **idempotent**. This means that the receiver is able to detect and ignore duplicate messages.

-   The integration flow design bears no risk of any side effects that can result in nondeterministic behavior. For example: During message processing, Cloud Integration writes variables and doesn't roll back the write action on failure.


In order to enable Cloud Integration to perform a retry, the message must be persisted.

Cloud Integration comes with the following storage options to serve this purpose:

-   JMS message queue

-   Data store


A first integration flow stores the message in the specified storage.

A second integration flow reads the message from the storage to carry out the actual message processing steps. If the message is persisted in a data store, the second integration flow holds a JDBC transaction to guarantee data consistency \(see [Define Proper Transaction Handling](define-proper-transaction-handling-1c31963.md)\). Only this setting ensures that the message is deleted from the persistence once the processing finished successfully. If there's an error during message processing, the message stays in the storage and is retried based on the configured retry or scheduler interval. For JMS queues, this step is performed automatically.

> ### Note:  
> If an error happens during the processing of the first integration flow during the attempt to store the message in the Cloud Integration persistence, the sender receives an error message. In this case, Cloud Integration can't retry the message because the message wasn't stored on Cloud Integration before. Therefore, in this case the sender needs to resend the message. For the use case where an automatic retry isn't supported on sender side, a user can decide to do a manual retry.



<a name="loioecbde19b7d184f5e8528a936f0d5f780__section_d1v_k4c_nrb"/>

## Involved Integration Flows

To simulate the communication of sender and receiver systems through Cloud Integration for the different scenarios, the integration package comes with multiple integration flows. To learn more about how these integration flows interact with each other during the processing of a scenario, see [Interaction of the Involved Integration Flows](interaction-of-the-involved-integration-flows-44be68d.md).



<a name="loioecbde19b7d184f5e8528a936f0d5f780__section_y3z_zpb_nrb"/>

## Example: Decoupling Via JMS Queue

As an example, we have modified scenario [Sender and Receiver with SAP RM Protocol](sender-and-receiver-with-sap-rm-protocol-9f3e2b6.md) by decoupling sender and receiver using a JMS queue. The remaining steps are mostly identical. The *Pattern Quality Of Service - Scenario 03* integration flow contains two integration processes.

![](images/Pattern_EO_03_11a25db.png)

The integration process *Integration Process Scenario 03 with retry via JMS: write to JMS queue* stores the message in a JMS queue after is is received from the sender system. The integration process contains one single JMS receiver channel with no further integration flow steps. Therefore, a JMS transaction handler isn't required. The JMS transaction is committed directly. After storing the message to the JMS queue, the sender receives the technical response. At sender side, the integration process uses a SOAP \(SAP RM\) sender adapter. Because the retry is performed by the second integration process, there's no need that the sender system passes on a message id to the middleware. Instead of this, the scenario uses an ID that is unique to the message exchange.

The second integration process *Integration Process Scenario 03 with retry via JMS: read from JMS queue* reads the message from the same JMS queue, and carries out the flow steps. The system automatically initiates a JMS transaction when reading the message from the JMS queue. Therefore, there's no need to explicitly set the transaction behavior.

At receiver side, the scenario uses the SOAP \(SAP RM\) receiver adapter. When checking out the adapter settings \(go to the *Processing* tab\), the *SAP RM Message ID Determination* property is set to *Map*. As *Source for SAP RM Message ID*, an ID is required that is constant throughout all potential retries from the JMS queue. For this purpose, the message ID of the message processing log is used. At runtime, Cloud Integration gets the actual value for the message ID from the header `SAP_MessageProcessingLogID`. The expression `${header.SAP_MessageProcessingLogID}` is used to specify the source for the ID Determination. Cloud Integration uses the mapped unique ID as SAP RM Message ID.

See: [Configure the SOAP \(SAP RM\) Receiver Adapter](configure-the-soap-sap-rm-receiver-adapter-8366495.md)

These integration flow settings ensure that Cloud Integration passes on a unique ID to the receiver system. If there's an error during message processing, Cloud Integration retries the message from the JMS queue. Because the retry is performed within the same instance of the message processing log, the message processing log ID and, as a result, the mapped unique ID remain the same.

If the message delivery fails, the JMS persistence ensures that the message is retried. If the message hasn't been sent to the receiver in the first place, a unique ID does not have any effect anyway. If the message has been delivered successfully to the receiver, however, the positive acknowledgment got lost in between, a unique and repeatable ID is required. Otherwise, this behavior can lead to duplicate messages arriving at the receiver. Because the receiver is idempotent, it recognizes the duplicate message based on the ID and discards it.

To test the scenario, perform the following steps:

1.  Set up inbound *Basic* authentication for integration flow endpoints.

    See:

    [Basic Authentication with clientId and clientsecret for Integration Flow Processing](../40-RemoteSystems/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)

    [Setting Up Inbound HTTP Connections (with Basic Authentication), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/391c45cfcd0f4435952ab085283b7f7d.html "") :arrow_upper_right:

2.  Deploy a *User Credentials* artifact with the following parameters using the *Monitor* application \(*Security Material* tile under *Manage Security*\).


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Setting
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    `OWN`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *User*
    
    </td>
    <td valign="top">
    
    Enter the user as specified when setting up inbound basic authentication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Password*
    
    </td>
    <td valign="top">
    
    Enter the password as specified when setting up inbound basic authentication.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > When you check out the integration flows *Pattern Quality Of Service – Mocked Sender* and *Pattern Quality Of Service - Scenario 03*, you notice that certain receiver adapters refer to a *User Credentials* artifact with the name *OWN*.
    > 
    > Both integration flows operate on the same tenant and use the same user credentials for inbound requests.

3.  Deploy all 3 integration flows *Generic Receiver*, *Pattern Quality Of Service – Mocked Sender*, and *Pattern Quality Of Service - Scenario 03*.

4.  In the Postman client, open the *QualityOfService* folder in the *Enterprise Integration Patterns* collection, and run the *QualityOfService – Scenario 03* request.

    We assume that the sender isn't able to resend messages. Therefore, the request doesn't contain a parameter `sendDuplicates`.

5.  Once the system has processed the second message successfully, check the data store *Pattern-QualityOfService* \(open the *Monitor* application and select the *Data Stores* tile under *Manage Stores*\).

    > ### Tip:  
    > You should see 1 entry with an entry *ID* that is identical to the mapped ID based on the message processing log.

6.  Before rerunning the test, clean up the data store.

7.  Optionally, you can switch on the trace to be able to verify the overall behavior.




<a name="loioecbde19b7d184f5e8528a936f0d5f780__section_fcr_jtb_nrb"/>

## Example: Sender Needs a Fast Response

Even if the sender is able to retry messages, it can make sense to decouple the message receipt from the actual message processing. Especially in cases where the integration flow is complex and, therefore, long-running, the decoupling can avoid running into timeouts while waiting for the acknowledgment. Timeout situations can lead to inconsistencies because the sender doesn't know if the message was successfully processed or not and therefore need to be avoided.

Like in the example before, the decoupling can be achieved via a JMS queue. Once the message is successfully stored in the JMS queue, a positive acknowledgment is returned to the sender. From this point on, Cloud Integration takes care of the further processing of the message and potential retries.

Such an example is described at [Decouple Sender and Flows Using Persistence](decouple-sender-and-flows-using-persistence-c5591df.md).

In the current example, we don't rule out that the sender retries the message. Therefore, other than in the previous example, duplicate handling requires that the sender system passes on a message ID to the middleware. This can be implemented similar to scenario [Sender and Receiver with SAP RM Protocol](sender-and-receiver-with-sap-rm-protocol-9f3e2b6.md). Together with the payload, the header is also stored in the JMS queue. Therefore, it can be passed on to the second integration process that reads the message including header from the JMS queue. As a prerequisite, the header is defined as allowed header in the *Runtime Configuration* of the integration flow.

