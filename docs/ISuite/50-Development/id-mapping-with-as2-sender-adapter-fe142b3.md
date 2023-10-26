<!-- loiofe142b3582b548eeb68ad8dca9ebe7fd -->

# ID Mapping \(with AS2 Sender Adapter\)

If the receiver adapter isn't offering the option to map an ID, use the *ID Mapping* integration flow step to map a source message ID to a target message ID. The ID mapping generates a unique ID for the combination of a source message ID and a context. When processing the ID mapping step with a dedicated combination of parameter settings the first time, Cloud Integration stores the generated ID temporarily in the tenant database. When executed with the same combination again, the ID mapping provides the same previously generated ID.

> ### Note:  
> To avoid database overflows, the ID mapping stores the generated ID with a limited lifetime. You can customize the corresponding parameter*Expiration Period* when designing the *ID Mapping* step. To be more specific: The expiration period, that is: the number of days after which the system deletes the stored ID mapping. The default setting is 30 days.
> 
> Make sure that the expiration period is longer than the expected maximal time period during which retries can happen.
> 
> See: [Define ID Mapping](define-id-mapping-2367101.md)

In this example, a partner sends a bulk purchase order in an EDIFACT ORDERS message format to Cloud Integration using the AS2 protocol. Using the EDI Splitter, Cloud Integration splits the bulk message into multiple messages, each containing a single purchase order. The EDIFACT messages are converted into an XML representation and afterwards mapped to the message format that the Web service can consume.

The AS2 protocol provides a unique ID for the incoming message. However its format differs from the ID format required by the target Web service. Furthermore: Using the EDI Splitter, Cloud Integration produces multiple EDIFACT messages using the same ID. However, the duplicate check at receiver side requires a unique ID for each split item.

The *Pattern Quality Of Service - Scenario 04a* integration flow illustrates this B2B scenario.

![](images/Example_B2B_Scenario_with_AS2_Sender_Adapter_and_ID_Mapper_b26c59b.png)

The integration flow performs the following steps:

1.  An AS2 adapter receives a protocol-specific message ID of the format XXXX@XXXX. Cloud Integration stores the ID in the header `AS2MessageID` \(see [Configure the AS2 Sender Adapter](configure-the-as2-sender-adapter-5d7ee17.md)\).

2.  An *EDI Splitter* step splits the EDIFACT bulk message into multiple messages.

    The parameters of this step are configured in the following way \(*EDIFACT* tab\):


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
    
    *Source Encoding*
    
    </td>
    <td valign="top">
    
    *UTF-8*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Validate Message*
    
    </td>
    <td valign="top">
    
    Deselected
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Create Acknowledgement*
    
    </td>
    <td valign="top">
    
    *Required*

    > ### Note:  
    > Based on this setting, 2 messages are passed on to the next integration flow step: the split messages and an acknowledgement.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Interchange Number*
    
    </td>
    <td valign="top">
    
    *Use From EDI Message*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *CONTRL Message Version*
    
    </td>
    <td valign="top">
    
    *Version D, Release 3*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Include UNA Segment*
    
    </td>
    <td valign="top">
    
    Deselected
    
    </td>
    </tr>
    </table>
    
3.  A *Router* step is required to return the acknowledgment to the sender. In this example, the acknowledgment is an EDIFACT CONTRL message.

    The default branch processes the actual order messages.

    The condition for the acknowledgment route is defined by the following expression \(*Expression Type* set to *Non-XML*\):

    `${header.EDI_ACKNOWLEDGEMENT} = 'true'`

4.  In an *EDI to XML Converter* step parses the single EDIFACT ORDERS message and maps it to EDI XML format.

5.  The Content Modifier *Set unique ID* defines the unique ID for each split EDIFACT message based on:

    -   The AS2 message ID provided by the sender system

    -   The EDI message control number

        This number is unique for each single purchase order in the EDIFACT bulk message.


    Check out the *Exchange Property* tab to verify the following settings:


    <table>
    <tr>
    <th valign="top">

    Name
    
    </th>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Data Type
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *SplitAS2MessageID*
    
    </td>
    <td valign="top">
    
    *Expression*
    
    </td>
    <td valign="top">
    
    `java.lang.String`
    
    </td>
    <td valign="top">
    
    `${header.AS2MessageID}_${header.EDI_Message_Control_Number}` 
    
    </td>
    </tr>
    </table>
    
    Based on this setting, the Content Modifier defines a new property. Its value is a concatenation of the AS2 message ID provided by the sender system and the EDI message control number.

6.  The *ID Mapping* step is defined in the following way:


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
    
    *Source Message ID*
    
    </td>
    <td valign="top">
    
    `${property.SplitAS2MessageID}` 

    This value is defined using the property defined in the previous Content Modifier.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Target Header Name*
    
    </td>
    <td valign="top">
    
    `SapMessageIdEx` 

    You can specify any name. However, using this header has an advantage considering the fact that a SOAP SAP RM receiver channel is used in this integration flow.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Context*
    
    </td>
    <td valign="top">
    
    `IDMapperContext_01` 

    You define a unique context for each *ID Mapping* step within your integration flow. If you need any additional *ID Mapping* \(providing a different target ID\), you can use a different context. In this scenario, there's 1 single *ID Mapping* step only. Therefore, the *Context* name doesn’t really matter.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Visibility*
    
    </td>
    <td valign="top">
    
    *Integration Flow* 

    The generated IDs are unique within the same integration flow model. If your *ID Mapping* is to be used across different integration flows, you need to select *Global*.
    
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
    
7.  At receiver side, the scenario uses the SOAP \(SAP RM\) receiver adapter. On the *Processing* tab of the adapter, the *SAP RM Message ID Determination* property is set to *Reuse*. This setting ensures that Cloud Integration uses the value of header `SapMessageIdEx` to set the `SAP RM Message ID`. The latter is then passed on to the receiver system. See [Configure the SOAP \(SAP RM\) Receiver Adapter](configure-the-soap-sap-rm-receiver-adapter-8366495.md).

    You remember that the `SapMessageIdEx` header contains the generated ID according to the configuration in the *ID Mapper* 


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
    > When you check out the integration flows *Pattern Quality Of Service – Mocked Sender* and *Pattern Quality Of Service - Scenario 04*, you notice that the receiver adapters refer to a *User Credentials* artifact with the name *OWN*.
    > 
    > Both integration flows operate on the same tenant and use the same user credentials for inbound requests.

3.  Deploy all 3 integration flows *Generic Receiver*, *Pattern Quality Of Service – Mocked Sender*, and *Pattern Quality Of Service - Scenario 04a*.

4.  In the Postman client, open the *QualityOfService* folder in the *Enterprise Integration Patterns* collection, and run the *QualityOfService – Scenario 04a* request.

    If you set the request parameter `sendDuplicates` to `true` \(in the *Params* tab of Postman\), the *Pattern Quality Of Service – Mocked Sender* integration flow sends a second message to the *Pattern Quality Of Service - Scenario 04a* integration flow with a delay of 5 seconds.

5.  Once the system has processed the second message successfully, check the data store *Pattern-QualityOfService* \(open the *Monitor* application and select the *Data Stores* tile under *Manage Stores*\).

    > ### Tip:  
    > Since the sample bulk EDIFACT ORDERS message contains 2 orders, you see 2 entries with entry ID identical to the generated message IDs.

6.  Before rerunning the test, clean up the data store.

7.  Optionally, you can switch on the trace to be able to verify the overall behavior.


**Related Information**  


[Configure the AS2 Sender Adapter](configure-the-as2-sender-adapter-5d7ee17.md "")

[Configure the SOAP \(SAP RM\) Receiver Adapter](configure-the-soap-sap-rm-receiver-adapter-8366495.md "Exchanges messages with a receiver system based on the SOAP communication protocol and SAP Reliable Messaging (SAP RM) as the message protocol. SAP RM is a simplified communication protocol for asynchronous Web service communication that does not require the use of Web Service Reliable Messaging standards.")

[Define ID Mapping](define-id-mapping-2367101.md "Map a source message ID to a target message ID.")

