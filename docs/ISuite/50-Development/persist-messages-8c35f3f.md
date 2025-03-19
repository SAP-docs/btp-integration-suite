<!-- loio8c35f3fa3b9c42c5b810332eccbc5a2f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Persist Messages

Store a message so that you can access the stored message and analyze it at a later point in time.



## Context

In an integration flow, you add a Persist step to store a message at a specific point in the process.

The message storage feature is useful for auditing purposes.

To imagine a use case for this feature, think of the following situation: Your integration flow receives orders for products by a sender system, processes these orders and, finally, updates a product catalog according to the received order. To meet certain compliance requirements, your IT department is asked to be able to prove \(for a dedicated point in time\):

-   Which message has been received by the sender

-   Which message has been sent to the receiver component to update the product catalog


To meet these requirements, you can add two Persist steps to your integration flow:

-   One Persist step after the message start event that receives the message from the sender component

-   Another Persist step before or after the Send or Request Reply step that sends the message to the receiver component


The logical storage location used by the Persist step is the message store. Physically, the message store uses the same tenant database as the data store \(see also: [Using Data Storage Features When Designing Integration Flows](using-data-storage-features-when-designing-integration-flows-a836b4e.md)\).

This component stores data on your tenant. Note that there is an overall disk space limit of 32 GB.

However, other than for the data store, there is no user interface-based option to access the content of the message store. To get its content, you need to use the Cloud Integration OData API.

There is also no option to access a message store entry during the execution of the integration flow that writes the entry. You can only access the message store content written by an integration flow after the integration flow has been processed.

> ### Note:  
> -   In case an error is thrown which is not caught, the messages cannot be persisted. This measure avoids filling up the database with the same messages again and again if messages are retried in fast intervals.
> 
>     An alternative is writing message processing log \(MPL\) attachments in this case: [Message Processing Log](message-processing-log-b32f8cd.md).
> 
>     If you use *Message Processing Log Attachments*: In case an error is thrown and you have integration flows that will write MPL attachments with a short retry interval, your overall disk space limit might be reached quickly.
> 
>     MPL attachments and message store content are stored in the SAP BTP object store. There’s a limit of 1 GB quota per 24 hours for object store usage. If you need to increase the object store size, refer to SAP note [3380591](https://me.sap.com/notes/3380591).
> 
> -   In case the processing ends with an escalation end event, whether or not messages are persisted depends on the scenario:
> 
>     -   Request reply/synchronous: in case of an escalation end event, the message is not persisted.
> 
>     -   One-Way/timer/asynchronous: in case of an escalation end event, the message is persisted successfully.
> 
> 
> -   A message is stored for 30 days. After this time, the message is deleted automatically.

The messages are persisted along with the Message ID, which you will need in order to retrieve the persisted entry via the Cloud Integration OData API: [Message Stores](https://api.sap.com/api/MessageStore/resource).



## Procedure

1.  In the palette, choose <span class="SAP-icons-V5"></span> \(Persistence\), then *Persist*.

2.  Place the step in your integration flow model at the location where you want to store the message.

3.  On the *General* tab, you can change the name of the *Persist* element.

4.  On the *Processing* tab, specify the following attributes:


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Step ID
    
    </td>
    <td valign="top">
    
    Provide a unique Step ID, which can be a descriptive name or a step number. For example, for a persistence step configured after a mapping step it could be `MessageStoredAfterMapping`.

    When analyzing the message store entry at a later point in time using the OData API, the Step ID of a dedicated Persist step is provided by the `MessageStoreId` element in the OData API response.

    > ### Caution:  
    > Note the following when using Cloud Integration in the Cloud Foundry environment:
    > 
    > Do not use any personal data as part of the *Step ID* parameter.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Encrypt Stored Message
    
    </td>
    <td valign="top">
    
    To store the message encrypted, keep the checkbox selected.

    If selected, the stored message is encrypted with an encryption key that is unique for each tenant \(using AES and a key length of 128 bits\). The encryption key is generated automatically, stored in a different database than the encrypted data, and periodically regenerated \(to increase security\).
    
    </td>
    </tr>
    </table>
    



<a name="loio8c35f3fa3b9c42c5b810332eccbc5a2f__postreq_nnt_j44_jdb"/>

## Next Steps

To access and analyze the stored messages, you can use the OData API. For more information, see [Message Stores](message-stores-1aab5e9.md).

To get the message store entries stored by a certain message processing run \(identified by a dedicated message processing log ID or: Message ID, perform the following OData API call:

<code>https://&lt;Cloud Integration host&gt;/api/v1/MessageProcessingLogs('&lt;Message ID&gt;')/MessageStoreEntries</code>

Example: `https://mytenant.tmn.hci.eu1.hana.ondemand.com/api/v1/MessageProcessingLogs('ABCD-1234-EFG')/MessageStoreEntries`

> ### Note:  
> You find the value for `Message ID` for the relevant message processing run when monitoring the integration flow using the Web UI \(under *Monitor Message Processing*\).

The OData response provides as many store entries as there are Persist steps in the associated integration flow. For more information on the attributes provided for each message store entry, see [Message Stores](https://api.sap.com/api/MessageStore/overview).

To get the message, you need to perform another OData API call providing the unique Id of the message store entry as input parameter.

There is a design guideline that shows you in detail how to write message store entries with an integration flow and how to retrieve the content after the integration flow has been executed \(see: [Use the Persist Step](use-the-persist-step-2707077.md)\).

