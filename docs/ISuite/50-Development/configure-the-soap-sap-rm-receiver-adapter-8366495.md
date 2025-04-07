<!-- loio8366495128624ec895f239888ef1e3ec -->

# Configure the SOAP \(SAP RM\) Receiver Adapter

Exchanges messages with a receiver system based on the SOAP communication protocol and SAP Reliable Messaging \(SAP RM\) as the message protocol. SAP RM is a simplified communication protocol for asynchronous Web service communication that does not require the use of Web Service Reliable Messaging standards.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

You have the option to set SOAP headers using Groovy script \(for example, using the Script step\).

Supported Header \(Receiver Adapter\):

-   SOAPAction Header

    This header is part of the Web service specification.


Once you have created a receiver channel and selected the SOAP \(SAP RM\) receiver adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

Select the *Connection* tab and provide values in the fields as follows.

**Connection**


<table>
<tr>
<th valign="top">

Parameters

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Address* 

</td>
<td valign="top">

Endpoint address at which the ESB posts the outgoing message, for example http://<host\>:<port\>/payment.

You can dynamically configure the address field of the SOAP \(SAP RM\) Adapter.

When you specify the address field of the adapter as $\{header.a\} or $\{property.a\}, at runtime the value of header a or exchange property \(as contained in the incoming message\) will be written into the Camel header CamelDestinationOverrideUrl and will be used in runtime to send the message to.

Also in case the CamelDestinationOverrideUrl header has been set by another process step \(for example, a Content Modifier\), its value will be overwritten.

The endpoint URL that is actually used at runtime is displayed in the message processing log \(MPL\) in the message monitoring application \(MPL property `RealDestinationUrl`\). Note that you can manually configure the endpoint URL using the *Address* attribute of the adapter. However, there are several ways to dynamically override the value of this attribute \(for example, by using the Camel header `CamelHttpUri`\).

</td>
</tr>
<tr>
<td valign="top">

*URL to WSDL*

</td>
<td valign="top">

URL to the WSDL defining the WS provider endpoint \(of the receiver\). You can specify the WSDL by selecting a source to browse for a WSDL either from an On-Premise ES Repository or your local workspace.

In the *Resources* view, you can upload an individual WSDL file or an archive file \(file ending with `.zip`\) that contains multiple WSDLs or XSDs, or both. For example, you can upload a WSDL that contains an imported XSD referenced by an `xsd:import` statement. This means that if you want to upload a WSDL and dependent resources, you need to add the parent file along with its dependencies in a single archive \(`.zip` file\).

> ### Note:  
> This adapter only supports one-way WSDLs. This means that the service definition in the WSDL must have only an `input` element, but no `output` element. A synchronous service definition \(with `input` and `output` element\) is not supported.
> 
> For more information, check out the following SAP Community blog: [Cloud Integration – Usage of WSDLs in the SOAP Adapter](https://blogs.sap.com/2018/06/28/cloud-integration-usage-of-wsdls-in-the-soap-adapter/).



</td>
</tr>
<tr>
<td valign="top">

*Service* 

</td>
<td valign="top">

Name of the selected service contained in the referenced WSDL.

</td>
</tr>
<tr>
<td valign="top">

*Endpoint*

</td>
<td valign="top">

Name of the selected port of  a selected service \(that you provide in the Service Name field\) contained in the referenced WSDL.

> ### Note:  
> Using the same port names across receivers is not supported in older versions of the receiver adapters. To use the same port names, you need to create a copy of the WSDL and use it.



</td>
</tr>
<tr>
<td valign="top">

*Operation Name*

</td>
<td valign="top">

Name of the operation of the selected service \(that you provide in the Service Name field\) contained in the referenced WSDL.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

The type of proxy that you are using to connect to the target system.

Select *Internet* if you are connecting to a cloud system.

Select *On-Premise* if you are connecting to on-premise system.

For more information, see [Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md).

</td>
</tr>
<tr>
<td valign="top">

*Location ID* \(only in case *On-Premise* is selected for *Proxy Type*\)

</td>
<td valign="top">

To connect to a Cloud Connector instance associated with your account, enter the location ID that you defined for this instance in the destination configuration on the cloud side. You can also enter `${header.headername}` or `${property.propertyname}` to dynamically read the value from a header or a property.

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

You can select one of the following authentication methods:

-   *Basic*

    SAP Cloud Integration authenticates itself against the receiver using user credentials \(user name and password\).

    It is a prerequisite that user credentials are specified in a Basic Authentication artifact and deployed on the related tenant.

-   *Client Certificate*

    SAP Cloud Integration authenticates itself against the receiver using a client certificate.

    It is a prerequisite that the required key pair is installed and added to a keystore. This keystore has to be deployed on the related tenant. The receiver side has to be configured appropriately.

-   *None*



</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias* \(only in case *Client Certificate* is selected for *Authentication*\)

</td>
<td valign="top">

Allows you to enter the private key alias name that gets the private key from the keystore and authenticates you to the receiver in an HTTPS communication.

You can also enter `${header.headername}` or `${property.propertyname}` to dynamically read the value from a header or a property.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name* \(only in case *Basic* is selected for *Authentication*\)

</td>
<td valign="top">

Name of the *User Credentials* artifact that contains the credentials for basic authentication

</td>
</tr>
<tr>
<td valign="top">

*Timeout*

</td>
<td valign="top">

Specifies the time \(in milliseconds\) that the client waits for a response before the connection is interrupted.

The default value is 60000 milliseconds \(1 minute\).

Note that the timeout setting has no influence on the Transmission Control Protocol \(TCP\) timeout if the receiver or any additional component interconnected between the Cloud Integration tenant and the receiver has a lower timeout. For example, consider that you have configured a receiver channel timeout of 10 minutes and there is another component involved with a timeout of 5 minutes. If nothing is transferred for a period of time, the connection will be closed after the fifth minute. In HTTP communication spanning multiple components \(for example, from a sender, through the load balancer, to a Cloud Integration tenant, and from there to a receiver\), the actual timeout period is influenced by each of the timeout settings of the individual components that are interconnected between the sender and receiver \(to be more exact, of those components that can control the TCP session\). The component or device with the lowest number set for the idle session timeout will determine the timeout that will be used.

</td>
</tr>
<tr>
<td valign="top">

*Compress Message*

</td>
<td valign="top">

Enables the WS endpoint to send compressed request messages to the WS provider and to indicate to the WS provider that it can handle compressed response messages.

</td>
</tr>
<tr>
<td valign="top">

*Allow Chunking*

</td>
<td valign="top">

Used for enabling HTTP chunking of data while sending messages.

> ### Note:  
> This option is enabled by default to avoid large HTTP messages. Make sure that the receiver of the message allows chunking if the *Allow Chunking* option is enabled.



</td>
</tr>
<tr>
<td valign="top">

*Return HTTP Response Code as Header*

</td>
<td valign="top">

When selected, writes the HTTP response code received in the response message from the called receiver system into the header `CamelHttpResponseCode`.

This feature is disabled by default.

> ### Note:  
> You can use this header, for example, to analyze the message processing run \(when level Trace has been enabled for monitoring\). Furthermore, you can use this header to define error handling steps after the integration flow has called the SOAP \(SAP RM\) receiver.
> 
> You cannot use the header to change the return code since the return code is defined in the adapter and cannot be changed.



</td>
</tr>
<tr>
<td valign="top">

*Clean Up Request Headers*

</td>
<td valign="top">

Select this option to clean up the adapter specific-headers after the receiver call.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.


<table>
<tr>
<th valign="top">

Parameters

</th>
<th valign="top">

Definition

</th>
</tr>
<tr>
<td valign="top">

*SAP RM Message ID Determination*

</td>
<td valign="top">

Select this option to specify how a target message ID \(referred to as SAP RM message ID\) shall be defined.

> ### Note:  
> You can use this feature to implement scenarios that guarantee end-to-end Exactly Once delivery. A receiver can use the target message ID, for example, to make sure that the receiver can process a certain message only once.
> 
> See: [Special Use Cases: SAP RM vs XI vs IDoc](special-use-cases-sap-rm-vs-xi-vs-idoc-5f7fa93.md)

You can choose among the following options:

-   *Generate* 

    Generates a new SAP RM message ID.

-   *Reuse* \(default\)

    Take over the message ID passed with the header `SapMessageIdEx`. If the header is not available in runtime, a new message ID is generated.

-   *Map*

    Maps a source message ID to the new target message ID.

    This option generates a target message ID that is uniquely associated with the source message ID specified with parameter *Source for SAP RM Message ID*. Precisely spoken, the system sets the value of header `SapMessageIdEx` to a globally unique identifier \(GUID\). This GUID identifies the target message.

    To specify the source message ID, you can use a header or a property. If no header or property is specified, the system generates a source message ID.


Note that source-to-target message ID mapping entries are deleted after 90 days. Furthermore, only the first 120 characters from the source message ID are considered by the mapping.

> ### Tip:  
> As example, let’s assume that you’ve chosen option *Map* for parameter *SAP RM Message ID Determination*, and in field *Source for SAP RM Message ID* you entered `${property.orderNo}`.
> 
> Furthermore, let’s assume that at runtime the property `orderNo` has the value `00001`. The SOAP SAP RM receiver adapter generates a unique identifier \(GUID\) for the target message ID, for example, `12a900b1-08ab-4812-x3ff-4y375b25z290`. In the scenario, the receiver system can then associate the target message ID `12a900b1-08ab-4812-x3ff-4y375b25z290` with the source message ID `00001`.
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Source Message ID
> 
> </th>
> <th valign="top">
> 
> Target Message ID
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> Property name: `orderNo`
> 
> Property value: `00001`
> 
> </td>
> <td valign="top">
> 
> Header name: `SapMessageIdEx`
> 
> Header value: `12a900b1-08ab-4812-x3ff-4y375b25z290`
> 
> </td>
> </tr>
> </table>



</td>
</tr>
<tr>
<td valign="top">

*Source for SAP RM Message ID* \(only in case *Map* is selected for *SAP RM Message ID Determination*\)

</td>
<td valign="top">

To map the source message ID to the SAP RM message ID you can enter the source message ID dynamically by using headers or properties \(`${header.headername}` or `${property.propertyname}`\).

> ### Note:  
> If no header or property is available at runtime, a new message ID is generated.



</td>
</tr>
</table>

**Related Information**  


[Read and Modify SOAP Headers](read-and-modify-soap-headers-8a2827d.md "You can use the Script step to address SOAP headers.")

[Setting Up Principal Propagation \(Example Scenario\)](../40-RemoteSystems/setting-up-principal-propagation-example-scenario-34eff84.md "Use principal propagation to forward the principal (identity of a user) across several connections in a complex system landscape.")

[https://wiki.scn.sap.com/wiki/display/ABAPConn/Plain+SOAP?original\_fqdn=wiki.sdn.sap.com](https://wiki.scn.sap.com/wiki/display/ABAPConn/Plain+SOAP?original_fqdn=wiki.sdn.sap.com)

[Defining Permissions for Senders to Process Messages on a Runtime Node](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/24585cc503334e6c917ef383efb5558a.html "") :arrow_upper_right:

[Setting Up Inbound HTTP Connections (Integration Flow Processing), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/778c7e7835ff46408aafe0d499720dc7.html "You can use various sender adapters (for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter) to connect the tenant to a sender system so that the sender can send messages to Cloud Integration over the HTTP protocol.") :arrow_upper_right:

