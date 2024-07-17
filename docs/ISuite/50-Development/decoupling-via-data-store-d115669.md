<!-- loiod115669dcb694ae0b9dccd04bf3d889f -->

# Decoupling via Data Store

The scenario described in this topic is similar to the scenario [Decoupling via JMS Queue](decoupling-via-jms-queue-ecbde19.md) where the middleware needs to carry out the retry of the message delivery if there's an error. There's the following difference: Instead of using a JMS queue to decouple sender and receiver, a data store is used.

The following use case requires such a behavior:

The sender system isn't able to retry messages.

The following assumptions apply for the design of this scenario:

-   It implements the communication between exactly 1 sender and 1 receiver.

-   The sender doesn't retry messages.

    Therefore, the middleware \(Cloud Integration\) needs to carry out the retry of the message delivery if there's an error.

-   The receiver is **idempotent**. This means that the receiver is able to detect and ignore duplicate messages.

-   The integration flow design bears no risk of any side effects that can result in nondeterministic behavior. For example: During message processing, Cloud Integration writes variables and doesn't roll back the write action on failure.


In order to enable Cloud Integration to perform a retry, the message must be persisted.

In this case, a data store is used as temporary storage.

A first integration flow receives the sender’s message and uses a Data Store Write step to store the message in a data store \(see [Define Data Store Write Operations](define-data-store-write-operations-46260ee.md)\).

A second integration flow reads the message from the storage using the data store sender adapter \(see [Data Store Sender Adapter](data-store-sender-adapter-4f5ef3f.md)\). The second integration flow performs the actual message processing steps and takes care of the message delivery to the receiver. This second integration flow holds a JDBC transaction to guarantee data consistency \(see [Define Proper Transaction Handling](define-proper-transaction-handling-1c31963.md)\). Only this setting ensures that the message is deleted from the persistence once the processing finished successfully. If there's an error during message processing, the message stays in the storage and is retried based on the configured retry or scheduler interval.

> ### Note:  
> If an error happens during the processing of the first integration flow during the attempt to store the message in the Cloud Integration persistence, the sender receives an error message. In this case, Cloud Integration can't retry the message because the message wasn't stored on Cloud Integration before. Therefore, in this case the sender needs to resend the message. For the use case where an automatic retry isn't supported on sender side, a user can decide to do a manual retry.



<a name="loiod115669dcb694ae0b9dccd04bf3d889f__section_d1v_k4c_nrb"/>

## Involved Integration Flows

To simulate the communication of sender and receiver systems through Cloud Integration for the different scenarios, the integration package comes with multiple integration flows. To learn more about how these integration flows interact with each other during the processing of a scenario, see [Interaction of the Involved Integration Flows](interaction-of-the-involved-integration-flows-44be68d.md).



<a name="loiod115669dcb694ae0b9dccd04bf3d889f__section_y3z_zpb_nrb"/>

## Example: Decoupling via Data Store

As an example, we have modified scenario [Decoupling via JMS Queue](decoupling-via-jms-queue-ecbde19.md) by replacing the JMS queue with a data store. The *Pattern Quality Of Service - Scenario 03a* integration flow contains two integration processes.

![](images/Scenario_3a_2d4ab8f.png)

The integration process *Integration Process Scenario 03a with retry via data store: write to data store* stores the message in a data store after it is received from the sender system. As *Entry ID* of the write operation, a unique ID is used \(the order number that is part of the message payload\).

A content modifier step right before the data store write step stores the order number in an exchange property with name `orderNumber`. The content modifier step uses the following parameters \(tab *Exchange Property*\):

****


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

*Action*

</td>
<td valign="top">

Create

</td>
</tr>
<tr>
<td valign="top">

*Name* 

</td>
<td valign="top">

orderNumber

</td>
</tr>
<tr>
<td valign="top">

*Source Type*

</td>
<td valign="top">

XPath

</td>
</tr>
<tr>
<td valign="top">

*Source Value* 

</td>
<td valign="top">

string\(//@PurchaseOrderNumber\)

</td>
</tr>
<tr>
<td valign="top">

*Data Type*

</td>
<td valign="top">

java.lang.String

</td>
</tr>
</table>

The write data store step is defined as follows \(tab *Processing*\):

****


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

*Data Store Name*

</td>
<td valign="top">

PatternQoS-03a

</td>
</tr>
<tr>
<td valign="top">

*Visibility*

</td>
<td valign="top">

Integration Flow

</td>
</tr>
<tr>
<td valign="top">

*Entry ID* 

</td>
<td valign="top">

$\{property.orderNumber\}

</td>
</tr>
<tr>
<td valign="top">

*Retention Threshold for Alerting \(in d\)* 

</td>
<td valign="top">

2

</td>
</tr>
<tr>
<td valign="top">

*Expiration Period \(in d\)* 

</td>
<td valign="top">

30

</td>
</tr>
</table>

The second integration process *Integration Process Scenario 03a with retry via data store: read from data store* reads the message from the same data store using a data store sender adapter, and carries out the subsequent integration flow steps.

At receiver side, the scenario uses the SOAP \(SAP RM\) receiver adapter. When checking out the adapter settings \(go to the *Processing* tab\), the *SAP RM Message ID Determination* property is set to *Map*. As *Source* for *SAP RM Message ID*, an ID is required that is constant throughout all potential retries from the data store. For this purpose, the data store entry ID is used. At runtime, Cloud Integration gets the actual value for the entry ID from the header `SapDataStoreId`. The expression `${header.SapDataStoreId}` is used to specify the source for the ID Determination. Cloud Integration uses the mapped unique ID as SAP RM Message ID.

See: [Configure the SOAP \(SAP RM\) Receiver Adapter](configure-the-soap-sap-rm-receiver-adapter-8366495.md)

These integration flow settings ensure that Cloud Integration passes on a unique ID to the receiver system. If there's an error during message processing, Cloud Integration retries the message from the data store.

If message delivery fails, the data store ensures that the message is retried. If the message hasn't been sent to the receiver in the first place, a unique ID does not have any effect anyway. If the message has been delivered successfully to the receiver, however, the positive acknowledgment got lost in between, a unique and repeatable ID is required. Otherwise, this behavior can lead to duplicate messages arriving at the receiver. Because the receiver is idempotent, it recognizes the duplicate message based on the ID and discards it.

> ### Note:  
> If the second integration flow contains further database operations, you need to set the transaction handling to *Required for JDBC* to ensure that all database operations are carried out within one transaction. Otherwise, if an error occurs, and the message is retried from the data store sender adapter, this could lead to data inconsistencies.

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
    > When you check out the integration flows *Pattern Quality Of Service – Mocked Sender* and *Pattern Quality Of Service - Scenario 03a*, you notice that certain receiver adapters refer to a *User Credentials* artifact with the name *OWN*.
    > 
    > Both integration flows operate on the same tenant and use the same user credentials for inbound requests.

3.  Deploy all 3 integration flows *Generic Receiver*, *Pattern Quality Of Service – Mocked Sender*, and *Pattern Quality Of Service - Scenario 03a*.

4.  In the Postman client, open the *QualityOfService* folder in the *Enterprise Integration Patterns* collection, and run the *QualityOfService – Scenario 03a* request.

    We assume that the sender isn't able to resend messages. Therefore, the request doesn't contain a parameter `sendDuplicates`.

5.  Once the system has processed the second message successfully, check the data store *Pattern-QualityOfService* \(open the *Monitor* application and select the *Data Stores* tile under *Manage Stores*\).

    > ### Tip:  
    > You should see 1 entry with an entry *ID* that is identical to the mapped ID based on the message processing log.

6.  Before rerunning the test, clean up the data store.

7.  Optionally, you can switch on log level *Trace* to be able to verify the overall behavior.

    > ### Note:  
    > That way, you can verity that the *Generic Receiver* integration flow receives the header `sapmessageidex`. The value of this header is used as Entry ID for the data store created by the *Generic Receiver*.


