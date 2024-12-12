<!-- loio86f97fd7bb944349946f94ec0a8375b9 -->

# Aggregator

Let's assume that your integration flow contains an aggregator to collect messages so that they can be processed in a bulk. In the example described in this topic individual product items related to the same order are collected. Cloud Integration sends the aggregated items as one single order with multiple items to a receiver system.

In this example, we have enhanced the Aggregator pattern to support the quality of service Exactly Once from end-to-end. First of all, we need to avoid that a single message is added to the aggregated message multiple times. Furthermore, the aggregated message should be sent to the receiver only once.

The *Pattern Quality Of Service - Scenario 07*integration flow illustrates this scenario.

![](images/Aggregator_with_idempotent_process_call_14f47b5.png)

The *Integration Process: Scenario 07 with idempotent local integration process to avoid duplicates in aggregates* integration process receives the individual product items. Each single message contains the same order number and a unique item number.

The *Fetch order ID and item number* content modifier step stores the item number in an exchange property with name *itemNumber* using the following settings \(*Exchange Property* tab\):

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

Name

</td>
<td valign="top">

itemNumber

</td>
</tr>
<tr>
<td valign="top">

Source Type

</td>
<td valign="top">

XPath

</td>
</tr>
<tr>
<td valign="top">

Data Type

</td>
<td valign="top">

java.lang.String

</td>
</tr>
<tr>
<td valign="top">

Source Value

</td>
<td valign="top">

//@ItemNumber

</td>
</tr>
</table>

Furthermore, the same content modifier stores the order number in a header with name *orderNumber* using the following settings \(*Message Header* tab\):

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

Name

</td>
<td valign="top">

orderNumber

</td>
</tr>
<tr>
<td valign="top">

Source Type

</td>
<td valign="top">

XPath

</td>
</tr>
<tr>
<td valign="top">

Data Type

</td>
<td valign="top">

java.lang.String

</td>
</tr>
<tr>
<td valign="top">

Source Value

</td>
<td valign="top">

//@PurchaseOrderNumber

</td>
</tr>
</table>

> ### Note:  
> For the order number a header is used instead of an exchange property to be able to pass on the value to the second integration process. For this purpose, the value *orderNumber* is maintained in the *Allowed Header\(s\)* list of the integration flow \(*Runtime Configuration* tab\).

The *Set unique ID* content modifier step creates a unique ID as a combination of the order number and the item number. This step creates an exchange property with name *uniqueID* using the following settings \(*Exchange Property* tab\):

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

Name

</td>
<td valign="top">

uniqueID

</td>
</tr>
<tr>
<td valign="top">

Source Type

</td>
<td valign="top">

Expression

</td>
</tr>
<tr>
<td valign="top">

Data Type

</td>
<td valign="top">

java.lang.String

</td>
</tr>
<tr>
<td valign="top">

Source Value

</td>
<td valign="top">

$\{header.orderNumber\}\_$\{property.itemNumber\}

</td>
</tr>
</table>

In order to avoid any duplicates, the *Idempotent Process Call* step sends the message to the *Local Integration Process: Send message to aggregator* subprocess. This step uses the following settings:

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

Message ID

</td>
<td valign="top">

$\{property.uniqueID\}

</td>
</tr>
<tr>
<td valign="top">

Skip Process Call for Duplicates

</td>
<td valign="top">

Selected

</td>
</tr>
</table>

The *Local Integration Process: Send message to aggregator* subprocess process passes on the single message to the *Integration Process: Aggregator* integration process using a *Request Reply* step and a ProcessDirect adapter.

This integration process contains the *Aggregator* step with the correlation expression `//@PurchaseOrderNumber`. That means that all product items with the same order number are combined into an aggregated message.

> ### Note:  
> This integration process represents the receiver in this scenario.

The following aggregation strategy has been defined for the Aggregator step:

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

Incoming Format

</td>
<td valign="top">

XML \(Same Format\)

</td>
</tr>
<tr>
<td valign="top">

Aggregation Algorithm

</td>
<td valign="top">

Combine

</td>
</tr>
<tr>
<td valign="top">

Last Message Condition \(XPath\)

</td>
<td valign="top">

ns0:Item/LastMessageIndicator='X'

</td>
</tr>
<tr>
<td valign="top">

Completion Timeout \(in min\)

</td>
<td valign="top">

2

</td>
</tr>
<tr>
<td valign="top">

Data Store Name

</td>
<td valign="top">

QoS-Aggregator

</td>
</tr>
</table>

As a result, the aggregator either waits until the messages have a *Last Message* status, or it waits for 2 minutes.

Once the completion condition is met, the aggregated multimap items message is mapped to a multimap order message. The subsequent filter step *Remove multimap wrapper* then removes the multimapping from the message.

At receiver side, the scenario uses the SOAP \(SAP RM\) receiver adapter with the following *Processing* settings:

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

SAP RM Message ID Determination

</td>
<td valign="top">

Map

</td>
</tr>
<tr>
<td valign="top">

Source for SAP RM Message ID

</td>
<td valign="top">

$\{header.orderNumber\}

</td>
</tr>
</table>

With this setting, the value of the order number is mapped to an `SAP RM Message ID` which is passed on to the idempotent receiver. The aggregator includes a message storage which can act as persistent storage for retry. If the delivery of the aggregated message fails in the first place, the aggregator retries every 5 minutes until the message is successfully delivered. If the message was successfully delivered to the receiver system, but the positive acknowledgment from the receiver got lost in between, the aggregator assumes that the call failed and therefore resends the message. This behavior results in duplicate messages arriving at the receiver side. Since the receiver is idempotent, the system discards the duplicate message.

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
    > When you check out the integration flows *Pattern Quality Of Service – Mocked Sender* and *Pattern Quality Of Service - Scenario 07*, you notice that the receiver adapters refer to a *User Credentials* artifact with the name *OWN*. Both integration flows operate on the same tenant and use the same user credentials for outbound requests.

3.  Deploy all 3 integration flows *Generic Receiver*, *Pattern Quality Of Service – Mocked Sender*, and *Pattern Quality Of Service - Scenario 07*.
4.  In the Postman client, open the *QualityOfService* \> *QualityOfService – Scenario 07* folder of the Postman collection that has been provided with the *Integration Flow Design Guidelines - Enterprise Integration Patterns* package. There you find 3 POST requests, each having a unique item number. The request with the item number 30 contains the last message indicator.
5.  Run all 3 requests. If you set the request parameter `sendDuplicates` to `true` \(in the *Params* tab of Postman\), the *Pattern Quality Of Service – Mocked Sender* integration flow sends a second message to the *Pattern Quality Of Service - Scenario 07* integration flow with a delay of 5 seconds.
6.  Once the system has processed all messages successfully, check the data store *Pattern-QualityOfService* \(open the *Monitor* application and select the *Data Stores* tile under *Manage Stores*\).

    > ### Tip:  
    > You see 1 entry with an entry ID that is automatically generated by the data store write operation. The payload of the data store entry should contain an order with all 3 items. Check out that no duplicate items have been added to the aggregated message.

7.  Before rerunning the test, clean up the data store. Furthermore, change the purchase order number. You notice that for the purchase order number in the request body, a Postman collection variable is used. You can change the value of the variable on the Pre-request Script tab of the first POST request before re-running the scenario.
8.  Optionally, you can switch on the trace to be able to verify the overall behavior.

**Related Information**  


[Aggregator](aggregator-5f5e01b.md "You want to combine related individual messages so that they can be processed in bulk. Using an Aggregator pattern, you can collect and store individual messages until a complete set of related messages has been received. The aggregated message is then sent to the actual receiver.")

[Define Idempotent Process Call](define-idempotent-process-call-84c85d7.md "Execute a process call step to check if an incoming message was already processed, and skip the processing of this message.")

