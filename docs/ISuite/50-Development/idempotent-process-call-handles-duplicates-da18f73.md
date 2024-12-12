<!-- loioda18f7332adc49a6b6999cf0934822ae -->

# Idempotent Process Call Handles Duplicates

Let's assume that the receiver isn’t idempotent, and the sender adapter doesn’t have any built-in duplicate removal capability. In this case, duplicate handling needs to be implemented within the integration flow.

You can implement duplicate handling using an *Idempotent Process Call* step. The idempotent process call helps to detect and remove the duplicates.

To give an example, scenario[XI Sender Adapter Handles Duplicates](xi-sender-adapter-handles-duplicates-7c9a0fd.md) has been modified: Instead of the XI sender adapter, the scenario uses the SOAP \(SAP RM\) protocol. That way, the sender can pass on a protocol-specific message ID. However, other than the XI protocol, the SOAP adapter doesn’t discard duplicate messages already during inbound processing.

At receiver side, the scenario uses the SOAP adapter with SOAP 1.x message protocol. See [Configure the SOAP \(SOAP 1.x\) Receiver Adapter](configure-the-soap-soap-1-x-receiver-adapter-57f7b34.md).

> ### Note:  
> The *Generic Receiver* is designed in such a way that when a message is sent to its SOAP 1.x endpoint, duplicates aren't discarded.

The *Pattern Quality Of Service - Scenario 05a* integration flow illustrates this scenario.

![](images/Integration_Flow_05a_idempotant_process_call_8047f70.png)

The *Local Integration Process: Send message to receiver* subprocess sends the message to the receiver system using a request reply step with a SOAP receiver adapter.

At the end of the main integration process, an *Idempotent Process Call* step sends the message to the local integration process using the following parameters:

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

Local Integration Process

</td>
<td valign="top">

Local Integration Process: Send message to receiver

</td>
</tr>
<tr>
<td valign="top">

Message ID

</td>
<td valign="top">

$\{header.SapMessageIdEx\}

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

These settings guarantee that no duplicate messages are sent to the receiver system. If the sender retries message delivery, the same ID is passed on to the idempotent local integration process. As the *Skip Process Call for Duplicates* flag is selected, the system discards the duplicate message.

To test the scenario, perform the following steps:

1.  Set up inbound *Basic* authentication for the integration flow endpoints.

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
    > When you check out the integration flows *Pattern Quality Of Service – Mocked Sender* and *Pattern Quality Of Service - Scenario 05a*, you notice that the receiver adapters refer to a *User Credentials* artifact with name *OWN*.
    > 
    > Both integration flows operate on the same tenant and use the same user credentials for outbound requests.

3.  Deploy all 3 integration flows *Generic Receiver*, *Pattern Quality Of Service – Mocked Sender*, and *Pattern Quality Of Service - Scenario 05a*.
4.  In the Postman client, open the *QualityOfService* folder of the Postman collection that has been provided with the *Integration Flow Design Guidelines - Enterprise Integration Patterns* package. Run the *QualityOfService – Scenario 05a* request.

    If you set the request parameter `sendDuplicates` to `true` \(in the *Params* tab of Postman\), the *Pattern Quality Of Service – Mocked Sender* integration flow sends a second message to the *Pattern Quality Of Service - Scenario 05a* integration flow with a delay of 5 seconds.

5.  Once the system has processed the second message successfully, check the data store *Pattern-QualityOfService*. To do that, open the *Monitor* application and select the *Data Stores* tile under *Manage Stores*.

    > ### Tip:  
    > You see only 1 entry with an entry ID that is automatically generated by the data store write operation.

6.  Before rerunning the test, clean up the data store.
7.  Optionally, you can switch on the trace to be able to verify the overall behavior.

**Related Information**  


[Define Idempotent Process Call](define-idempotent-process-call-84c85d7.md "Execute a process call step to check if an incoming message was already processed, and skip the processing of this message.")

