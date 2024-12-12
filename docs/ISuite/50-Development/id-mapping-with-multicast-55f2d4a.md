<!-- loio55f2d4a6f98e482ab1ec79b227030bc9 -->

# ID Mapping \(with Multicast\)

Items of a purchase order are sent to different suppliers depending on a particular product category. For this, a multicast flow step with different filters in each multicast branch is used.



<a name="loio55f2d4a6f98e482ab1ec79b227030bc9__section_ylf_h5t_f5b"/>

## Implementation

The purchase order items for flat screens and notebooks are sent to the same receiver. The receiver carries out the duplicate check if Cloud Integration resends the message with the same message ID. The duplicate check at receiver side requires a unique ID for each item.

Because those two corresponding multicast branches do send messages to the same receiver, we use an *ID Mapping* integration flow step to generate a unique ID for the combination of a source message ID and a branch-specific context. When processing the ID Mapping step with a dedicated combination of parameter settings the first time, Cloud Integration stores the generated ID temporarily in the tenant database. When executed with the same combination again, the ID mapping provides the same previously generated ID.

> ### Note:  
> To avoid database overflows, the ID mapping stores the generated ID with a limited lifetime. You can customize the corresponding parameterExpiration Period when designing the ID Mapping integration flow step. To be more specific, the expiration period, that is the number of days after which the system deletes the stored ID mapping. The default setting is set to 30 days.
> 
> Make sure that the expiration period is longer than the expected maximal time period during which retries can happen.
> 
> See [Define ID Mapping](define-id-mapping-2367101.md).

Purchase order items for the category software are sent to a different receiver. We assume that this receiver isn't idempotent. In this case, duplicate handling needs to be implemented within the integration flow.

For this multicast branch, we implement duplicate handling using an *Idempotent Process Call* step. The idempotent process call helps you to detect and remove the duplicates.

The *Pattern Quality Of Service - Scenario 04b* integration flow illustrates this multicast scenario.

![](images/Pattern_Quality_Of_Service_ee747f1.png)

At sender side, the scenario uses the SOAP \(SAP RM\) sender adapter with message protocol SAP Reliable Messaging. This setting ensures that the sender can pass on a protocol-specific message ID to the integration flow. Cloud Integration saves the ID in the header `SapMessageIdEx`. See [Configure the SOAP \(SAP RM\) Sender Adapter](configure-the-soap-sap-rm-sender-adapter-6962234.md).

In a parallel multicast flow step, the message is sent to multiple routes where it's processed in parallel. Each route implements a content filter pattern \(for more information on this pattern, see also [Content Filter](content-filter-6fd4a86.md)\).

The first route removes all items except for flat screens using the following setting in the filter flow step \(*Processing* tab\):

**First Route**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

*XPath Expression* 

</td>
<td valign="top">

`ns0:PurchaseOrder/Items/Item[./Category/text()='Flat screens']` 

</td>
</tr>
<tr>
<td valign="top">

*Value Type* 

</td>
<td valign="top">

`Nodelist` 

</td>
</tr>
</table>

The second route removes all items except for notebooks using the following setting in the filter flow step \(*Processing* tab\):

**Second Route**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

*XPath Expression* 

</td>
<td valign="top">

`ns0:PurchaseOrder/Items/Item[./Category/text()='Notebooks']` 

</td>
</tr>
<tr>
<td valign="top">

*Value Type* 

</td>
<td valign="top">

`Nodelist` 

</td>
</tr>
</table>

Both routes send the filtered messages to the same receiver. So, we add an ID Mapping step to define a unique ID that is required for the duplicate handling within the receiver system.

The *ID Mapping* step of the first route is defined in the following way:

**First Route: ID Mapping**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

*Source Message ID* 

</td>
<td valign="top">

`${header.SapMessageIdEx}` 

</td>
</tr>
<tr>
<td valign="top">

*Target Header Name* 

</td>
<td valign="top">

`SapMessageIdEx` 

</td>
</tr>
<tr>
<td valign="top">

*Context* 

</td>
<td valign="top">

`Branch_1` 

</td>
</tr>
<tr>
<td valign="top">

*Visibility* 

</td>
<td valign="top">

`Integration Flow` 

</td>
</tr>
<tr>
<td valign="top">

*Expiration Period \(in d\)* 

</td>
<td valign="top">

`30` 

</td>
</tr>
</table>

The *ID Mapping* step of the second route is defined in the following way:

**Second Route: ID Mapping**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

*Source Message ID* 

</td>
<td valign="top">

`${header.SapMessageIdEx}` 

</td>
</tr>
<tr>
<td valign="top">

*Target Header Name* 

</td>
<td valign="top">

`SapMessageIdEx` 

</td>
</tr>
<tr>
<td valign="top">

*Context* 

</td>
<td valign="top">

`Branch_2` 

</td>
</tr>
<tr>
<td valign="top">

*Visibility* 

</td>
<td valign="top">

`Integration Flow` 

</td>
</tr>
<tr>
<td valign="top">

*Expiration Period \(in d\)* 

</td>
<td valign="top">

`30` 

</td>
</tr>
</table>

At receiver side, the scenario uses the SOAP \(SAP RM\) receiver adapter. On the *Processing* tab of the adapter, the *SAP RM Message ID Determination* property is set to `Reuse`. This setting ensures that Cloud Integration uses the value of the header `SapMessageIdEx` to set the SAP RM Message ID that is then passed to the receiver system. See [Configure the SOAP \(SAP RM\) Receiver Adapter](configure-the-soap-sap-rm-receiver-adapter-8366495.md).

The third route removes all items except for software using the following setting in the filter flow step \(*Processing*\):

**Third Route**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

*XPath Expression* 

</td>
<td valign="top">

`ns0:PurchaseOrder/Items/Item[./Category/text()='Software']` 

</td>
</tr>
<tr>
<td valign="top">

*Value Type* 

</td>
<td valign="top">

`Nodelist` 

</td>
</tr>
</table>

This route goes to a different receiver that uses the SOAP adapter with SOAP 1.x message protocol. See [Configure the SOAP \(SOAP 1.x\) Receiver Adapter](configure-the-soap-soap-1-x-receiver-adapter-57f7b34.md).

> ### Note:  
> The *Generic Receiver* is designed in such a way that when a message is sent to its SOAP 1.x endpoint, duplicates aren't discarded.

The actual request reply step with the SOAP receiver adapter is put into the *Local Integration Process: Send message to Software supplier* subprocess.

At the end of the third route, an *Idempotent Process Call* step sends the message to the local integration process using the following parameters:

**Message Parameters**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

*Message ID* 

</td>
<td valign="top">

`${header.SapMessageIdEx}` 

</td>
</tr>
<tr>
<td valign="top">

*Skip Process Call for Duplicates* 

</td>
<td valign="top">

`Selected` 

</td>
</tr>
</table>

These settings guarantee that no duplicate messages are sent to the receiver system. If the sender retries message delivery, the same ID is passed on to the idempotent local integration process. As the *Skip Process Call for Duplicates* flag is selected, the system discards the duplicate message.

To test the scenario, perform the following steps:

1.  Set up inbound Basic authentication for integration flow endpoints. See:

    -   [Basic Authentication with clientId and clientsecret for Integration Flow Processing](../40-RemoteSystems/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)

    -   [Setting Up Inbound HTTP Connections (with Basic Authentication), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/391c45cfcd0f4435952ab085283b7f7d.html "") :arrow_upper_right:


2.  Deploy an artifact *User Credentials* with the following parameters using the *Monitor* application \(*Security Material* tile under *Manage Security*\).

    **Message Parameters**


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Value
    
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
    > When you check out the integration flows *Pattern Quality Of Service – Mocked Sender* and *Pattern Quality Of Service - Scenario 04b*, you notice that certain receiver adapters refer to an artifact*User Credentials* with the name *OWN*.
    > 
    > Both integration flows operate on the same tenant and use the same user credentials for inbound requests.

3.  Deploy all three integration flows *Generic Receiver*, *Pattern Quality Of Service – Mocked Sender*, and *Pattern Quality Of Service - Scenario 04b*.

4.  In the Postman client, open the *QualityOfService* folder in the *Enterprise Integration Patterns* collection, and run the *QualityOfService – Scenario 04b* request.

    If you set the request parameter `sendDuplicates` to `true` \(in the *Params* tab of Postman\), the *Pattern Quality Of Service – Mocked Sender* integration flow sends a second message to the *Pattern Quality Of Service - Scenario 04b* integration flow with a delay of five seconds.

5.  Once the system has processed the second message successfully, check the data store *Pattern-QualityOfService* \(open the *Monitor* application and select the *Data Stores* tile under *Manage Stores*\).

    > ### Tip:  
    > You should see three entries with an entry *ID* that is identical to the mapped ID based on the message processing log and the context.

6.  Before rerunning the test, clean up the data store.

7.  Optionally, you can switch on the trace to be able to verify the overall behavior.


**Related Information**  


[Define Idempotent Process Call](define-idempotent-process-call-84c85d7.md "Execute a process call step to check if an incoming message was already processed, and skip the processing of this message.")

[Define ID Mapping](define-id-mapping-2367101.md "Map a source message ID to a target message ID.")

