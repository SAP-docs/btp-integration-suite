<!-- loio8f8feea244e2450485b4dee84692778b -->

# IDoc Receiver Handles Duplicates

The following assumptions apply for the design of this scenario:

-   It implements the communication between exactly 1 sender and 1 receiver.

-   The message protocol contains a unique ID such as a message ID.

-   The sender supports message retry. It's assumed that the message ID remains the same for all retries.

-   The IDoc receiver adapter is used to exchange Intermediate Document \(IDoc\) messages with the receiver.


> ### Note:  
> The IDoc runtime in the backend is able to detect and ignore duplicate messages, hence is idempotent, if the following prerequisites are fulfilled:
> 
> -   IDoc Content Type equals Application/x-sap.doc
> 
> -   Header `SapMessageId` remains the same for each message retry.
> 
> 
> You can anticipate the following situations:
> 
> -   The call fails at first place, and therefore the sender retries until the message is successfully delivered.
> 
> -   The system has delivered the message successfully, however, the positive acknowledgment from the receiver got lost in between. As a result, the sender assumes that the call failed and therefore resends the message. This behavior results in duplicate messages arriving at the receiver side. Since the receiver is idempotent, the system discards the duplicate message.



<a name="loio8f8feea244e2450485b4dee84692778b__section_uct_kx2_2yb"/>

## Involved Integration Flows

To simulate the communication of sender and receiver systems through Cloud Integration for the different scenarios, the integration package comes with multiple integration flows. To learn more about how these integration flows interact with each other during the processing of a scenario, see [Interaction of the Involved Integration Flows](interaction-of-the-involved-integration-flows-44be68d.md).



<a name="loio8f8feea244e2450485b4dee84692778b__section_tdm_sx2_2yb"/>

## Example Scenario

The Pattern Quality Of Service - Scenario 01a integration flow maps a web service to an IDoc. As IDoc message type, we simply use FLIGHTBOOKING\_CREATEFROMDAT from the flight booking demo that you may setup in your SAP ECC or SAP S/4HANA system.

![](images/Example_Scenario_a6000b5.png)

The scenario contains a SOAP \(SAP RM\) sender adapter with SAP Reliable Messaging message protocol. This setting ensures that the sender can pass on a protocol-specific message ID to the integration flow. Cloud Integration saves the ID in the header` SapMessageIdEx`. See [Configure the SOAP \(SAP RM\) Sender Adapter](configure-the-soap-sap-rm-sender-adapter-6962234.md).

On the receiver side, the scenario uses an IDoc receiver adapter. The IDoc receiver adapter passes on the header `SapMessageId` to the backend which is used to detect duplicates.

See [Configure the IDoc Receiver Adapter](configure-the-idoc-receiver-adapter-018aa88.md).

So, we need to ensure that the header `SapMessageId` is set with the unique ID `SapMessageIdEx` sent by the sender adapter. If the sender retries the message delivery, the same ID is passed on to the IDoc receiver. In this case, we ensure that duplicate messages are discarded.

On the *Processing* tab of the IDoc receiver adapter, specify the following settings:


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

`${header.SapMessageIdEx}`

</td>
</tr>
</table>

To make it easy for you to set up and run the scenario, the integration package contains the predefined integration flow *Pattern Quality Of Service – Mocked Sender*. This integration flow simulates different sender system situations. In the present case, the sender system is able to resend messages keeping the same message ID.

Furthermore, the *Generic Receiver* integration flow has been extended to mock different kind of receiver systems. In general, the *Generic Receiver* integration flow creates a data store entry for each receiver call. To support the present scenario, the *Integration Process: Idempotent receiver using IDoc protocol* integration process with IDoc sender adapter has been added. The *Entry ID* of the *Data Store Write* step is defined by the value of the header `SapMessageId`. To verify this setting, check out the *Set context and id* content modifier of this integration process. As a result, each duplicate message overwrites the existing entry with the same payload instead of adding additional data store entries. Therefore, overall, the scenario is idempotent.

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
    > When you check out the integration flows *Pattern Quality Of Service – Mocked Sender* and *Pattern Quality Of Service - Scenario 01a*, you notice that the receiver adapters refer to a *User Credentials* artifact with the name *OWN*.

    Both integration flows operate on the same tenant and use the same user credentials for inbound requests.

3.  Deploy all 3 integration flows *Generic Receiver*, *Pattern Quality Of Service – Mocked Sender*, and *Pattern Quality Of Service - Scenario 01a*.
4.  In the Postman client, open the *QualityOfService* folder in the *Enterprise Integration Patterns* collection, and run the *QualityOfService – Scenario 01a* request.

    If you set the request parameter `sendDuplicates to true` \(in the *Params* tab of Postman\), the *Pattern Quality Of Service – Mocked Sender* integration flow sends a second message to the *Pattern Quality Of Service - Scenario 01a* integration flow with a delay of 5 seconds.

5.  Once the system has processed the second message successfully, check the data store *Pattern-QualityOfService* \(open the *Monitor* application and select the *Data Stores* tile under *Manage Stores*\).

    > ### Tip:  
    > You see only 1 entry with an entry *ID* that is identical to the message id of the *Pattern Quality Of Service – Mocked Sender* integration flow processing.

6.  Before rerunning the test, clean up the data store.

7.  Optionally, you can switch on the trace to be able to verify the overall behavior.

