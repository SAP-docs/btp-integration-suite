<!-- loio776b64099da84c5697a84c1b6ce7be03 -->

# IDoc Receiver Handles Duplicates \(with decoupling via JMS Queue\)

The scenario described in this topic is similar to the scenario[Decoupling via JMS Queue](decoupling-via-jms-queue-ecbde19.md). A JMS queue is used to handle the retry of the message delivery if an error occurs. The receiver is idempotent, however here we describe how to ensure duplicate handling in case of an IDoc receiver instead of using SAP RM.

The following assumptions apply for the design of this scenario:

-   It implements the communication between exactly 1 sender and 1 receiver.
-   The sender doesn't retry messages. Therefore, the middleware \(Cloud Integration\) needs to carry out the retry of the message delivery if there's an error.
-   The IDoc receiver adapter is used to exchange Intermediate Document \(IDoc\) messages with the receiver.

> ### Note:  
> The IDoc runtime in the backend is able to detect and ignore duplicate messages, hence is idempotent, if the following prerequisites are fulfilled:
> 
> -   IDoc Content Type equals Application/x-sap.doc
> -   Header SapMessageId remains the same for each message retry.

In order to enable Cloud Integration to perform a retry, the message must be persisted. In this scenario, we use a JMS message queue.

A first integration flow stores the message in the specified storage.

A second integration flow reads the message from the storage to carry out the actual message processing steps. If there's an error during message processing, the message stays in the JMS queue and is retried based on the configured retry.



## Involved Integration Flows

To simulate the communication of sender and receiver systems through Cloud Integration for the different scenarios, the integration package comes with multiple integration flows. To learn more about how these integration flows interact with each other during the processing of a scenario, see Interaction of the [Involved Integration Flows](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/interaction-of-involved-integration-flows).



<a name="loio776b64099da84c5697a84c1b6ce7be03__section_bqh_5nj_gyb"/>

## Example Scenario

As an example, we have modified scenario [XI Receiver Handles Duplicates](xi-receiver-handles-duplicates-fcf026b.md) by decoupling sender and receiver using a JMS queue. The Pattern Quality Of Service - Scenario 03b integration flow contains two integration processes.

![](images/Example_Scenario_68be585.png)

The integration process **Integration Process Scenario 03b with retry via JMS and IDoc receiver: write to JMS queue** stores the message in a JMS queue after it is received from the sender system. The integration process contains one single JMS receiver channel with no further integration flow steps. Therefore, a JMS transaction handler isn't required. The JMS transaction is committed directly. After storing the message to the JMS queue, the sender receives the technical response. At sender side, the integration process uses a SOAP sender adapter. Because the retry is performed by the second integration process, there's no need that the sender system passes on a message id to the middleware. Instead of this, the scenario uses an ID that is unique to the message exchange.

The second integration process **Integration Process Scenario 03b with retry via JMS and IDoc receiver: read from JMS queue** reads the message from the same JMS queue, and carries out the flow steps. The system automatically initiates a JMS transaction when reading the message from the JMS queue. Therefore, there's no need to explicitly set the transaction behavior.

On the receiver side, the scenario uses an IDoc receiver adapter. The IDoc receiver adapter passes on the header `SapMessageId` to the backend which is used to detect duplicates.

You can choose between three options how to specify the target ID `SapMessageId`:

-   *Generate*

-   *Reuse*

-   *Map*


See[Configure the IDoc Receiver Adapter](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/configure-idoc-receiver-adapter)

So, we need to ensure that the header `SapMessageId` is set with an ID that is constant throughout all potential retries from the JMS queue. For this purpose, the message ID of the message processing log is used. At runtime, Cloud Integration gets the actual value for the message ID from the header `SAP_MessageProcessingLogID`.

On the *Processing* tab of the IDoc receiver adapter, the following settings have to be configured:


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

*SapMessageId Determination*

</td>
<td valign="top">

*Map*

</td>
</tr>
<tr>
<td valign="top">

*Source for SapMessageId*

</td>
<td valign="top">

`${header.SAP_MessageProcessingLogID}`

</td>
</tr>
</table>

To test the scenario, perform the following steps:

1.  Set up inbound *Basic* authentication for integration flow endpoints.

    See:

    [Basic Authentication with clientId and clientsecret for Integration Flow Processing](../40-RemoteSystems/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)

    [Setting Up Inbound HTTP Connections (with Basic Authentication), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/391c45cfcd0f4435952ab085283b7f7d.html "") :arrow_upper_right: 

2.  Deploy a *User Credentials* artifact with the following parameters using the *Monitor* application \(*Security Material* tile under *Manage Security*\).


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
    
    Name
    
    </td>
    <td valign="top">
    
    OWN
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User
    
    </td>
    <td valign="top">
    
    Enter the user as specified when setting up inbound basic authentication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Password
    
    </td>
    <td valign="top">
    
    Enter the password as specified when setting up inbound basic authentication.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > When you check out the integration flows *Pattern Quality Of Service – Mocked Sender* and *Pattern Quality Of Service - Scenario 03b*, you notice that the receiver adapters refer to a *User Credentials* artifact with the name *OWN*.

    Both integration flows operate on the same tenant and use the same user credentials for inbound requests.

3.  Deploy all 3 integration flows *Generic Receiver*, *Pattern Quality Of Service – Mocked Sender*, and *Pattern Quality Of Service - Scenario 03b*.
4.  In the Postman client, open the *QualityOfService* folder in the *Enterprise Integration Patterns* collection, and run the *QualityOfService – Scenario 03b* request.

    We assume that the sender isn't able to resend messages. Therefore, the request doesn't contain a parameter `sendDuplicates`.

5.  Once the system has processed the second message successfully, check the data store *Pattern-QualityOfService* \(open the *Monitor* application and select the *Data Stores* tile under *Manage Stores*\).

    > ### Tip:  
    > You see only 1 entry with an entry *ID* that is identical to the mapped ID based on the message processing log.

6.  Before rerunning the test, clean up the data store.

7.  Optionally, you can switch on the trace to be able to verify the overall behavior.

