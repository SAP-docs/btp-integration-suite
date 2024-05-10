<!-- loio57f7b34b9b86438d9cb760c5c541f88c -->

# Configure the SOAP \(SOAP 1.x\) Receiver Adapter

The SOAP \(SOAP 1.x\) receiver adapter enables a SAP BTP tenant to exchange messages with a receiver system that supports Simple Object Access Protocol \(SOAP\) 1.1.

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




> ### Caution:  
> Usage of Different WSDL Binding Styles:
> 
> Note that messages that contain RPC-style bindings can only be processed by the SOAP receiver channel if no WSDL file is provided \(that is, if you leave the *URL to WSDL* field empty\). We recommend that you use document-style payloads. If several XML parts are returned by the receiver system in the RPC response, only the first part is processed by SAP Cloud Integration. The other parts are ignored.
> 
> A WSDL binding describes how the service is bound to a message protocol. For the processing of SOAP messages, you can choose from the following binding types:
> 
> -   RPC/encoded \(not recommended in WS Basic Profile Version 1.0\)
> 
> -   RPC/literal
> 
> -   Document/encoded \(not recommended in WS Basic Profile Version 1.0\)
> 
> -   Document/literal
> 
> 
> RPC stands for *Remote Procedure Call*. For more information on these options and the meaning of *literal* and *encoded*, see: [http://www.w3.org/TR/2001/NOTE-wsdl-20010315](http://www.w3.org/TR/2001/NOTE-wsdl-20010315).



Once you have created a receiver channel and selected the SOAP \(SOAP 1.x\) receiver Adapter, you can configure the following attributes. See: [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

Select the *General* tab and provide values in the fields as follows.

**General**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Enter the name of the channel.

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows.

**Connection**


<table>
<tr>
<th valign="top">

Parameter

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

Endpoint address at which Cloud Integration posts the outgoing message, for example, `http://<host>:<port>/payment`.

You can dynamically configure the address field of the SOAP \(SOAP 1.x\) adapter.

If you specify the address field of the adapter as `${header.a}` or `${property.a}`, the value of a header or an exchange property \(from the incoming message\) is written into Camel header `CamelDestinationOverrideUrl` at runtime. This value will be used as the address to send the message to.

Also, if the CamelDestinationOverrideUrl header has been set by another process step \(for example, a Content Modifier\), its value is overwritten.

The endpoint URL that is used at runtime is displayed in the message processing log \(MPL\) in the message monitoring application \(MPL property `RealDestinationUrl`\). Note that you can manually configure the endpoint URL using the *Address* attribute of the adapter. However, there are several ways to dynamically override the value of this attribute \(for example, by using the Camel header `CamelDestinationOverrideUrl`\).

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

The type of proxy that you are using to connect to the target system:

-   Select *Internet* if you are connecting to a cloud system.

-   Select *On-Premise* if you are connecting to an on-premise system.

    > ### Note:  
    > If you select the *On-Premise* option, the following restrictions apply to other parameter values:
    > 
    > -   Use HTTP instead of HTTPS when specifying the virtual system url in the *Address* field.
    > 
    > -   Do not use the option *Client Certificate* for the *Authentication* parameter, as it leads to errors when performing consistency checks or during deployment.

    > ### Note:  
    > If you select the *On-Premise* option and use the SAP Cloud Connector to connect to your on-premise system, the *Address* field of the adapter references a virtual address, which has to be configured in the SAP Cloud Connector settings.

-   If you select *Manual*, you can manually specify *Proxy Host* and *Proxy Port* \(using the corresponding entry fields\).

    This option is only available if you have chosen a *Process Orchestration* product profile.




</td>
</tr>
<tr>
<td valign="top">

*URL to WSDL* 

</td>
<td valign="top">

URL pointing to the WSDL defining the WS provider endpoint \(of the receiver\).

To select the WSDL from a source, you have the following options:

-   Select a WSDL from your file system.

-   Select a WSDL from your integration flow resources \(see: [Manage Resources](manage-resources-b5968b2.md)\).

    In the *Resources* view, you can upload an individual WSDL file or an archive file \(file ending with `.zip`\) that contains multiple WSDLs or XSDs, or both. For example, you can upload a WSDL that contains an imported XSD referenced by an `xsd:import` statement. This means that if you want to upload a WSDL and dependent resources, you need to add the parent file along with its dependencies in a single archive \(`.zip` file\).


> ### Note:  
> -   If you’ve configured SAP Cloud Connector with the SOAP receiver adapter, you cannot access WSDL via Cloud Connector.
> 
> -   If you specify a WSDL, you also have to specify the name of the selected service and the name of the port selected for this service. These fields must have a namespace prefix.
> 
>     Expected format: `<namespace>:<service_name>`
> 
>     Example: `p1:MyService`
> 
> -   Don't use WSDLs with blanks:
> 
>     It is not recommended to use blanks in WSDL names or directories. This can lead to runtime issues.

For more information on how to work with WSDL resources, see the following blog: [Cloud Integration – Usage of WSDLs in the SOAP Adapter](https://blogs.sap.com/2018/06/28/cloud-integration-usage-of-wsdls-in-the-soap-adapter/)

</td>
</tr>
<tr>
<td valign="top">

*Service Name* 

</td>
<td valign="top">

Name of the selected service contained in the referenced WSDL

</td>
</tr>
<tr>
<td valign="top">

*Endpoint*

</td>
<td valign="top">

Name of the selected endpoint of  a selected service \(that you provide in the *Service Name* field\) contained in the referenced WSDL.

> ### Note:  
> Using the same port names across receivers isn't supported in older versions of the receiver adapters. To use the same port names, you need to create a copy of the WSDL and use it.



</td>
</tr>
<tr>
<td valign="top">

*Operation Name*

</td>
<td valign="top">

Name of the operation of a selected service \(that you provide in the *Service Name* field\) contained in the referenced WSDL.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name* \(only available if you have selected *Basic* or *OAuth 2.0 SAML Bearer Assertion Grant* for the *Authentication* parameter\)

</td>
<td valign="top">

Name of the *User Credentials* artifact that contains the credentials for basic authentication or OAuth 2.0 SAML Bearer Assertion Grant.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias* \(only available if you have selected *Client Certificate* for the *Authentication* parameter\)

</td>
<td valign="top">

Specifies an alias to indicate a specific key pair to be used for the authentication step.

You can dynamically configure the *Private Key Alias* parameter by specifying either a header or a property name in one of the following ways: `${header.headername}` or `${property.propertyname}`.

In some cases this feature can have a negative impact on performance.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)*

</td>
<td valign="top">

Specifies the time \(in milliseconds\) that the client waits for a response before the connection is interrupted.

The default value is 60000 milliseconds \(1 minute\).

Note that the timeout setting has no influence on the Transmission Control Protocol \(TCP\) timeout if the receiver or any additional component interconnected between the Cloud Integration tenant and the receiver has a lower timeout. For example, consider that you have configured a receiver channel timeout of 10 minutes and there is another component involved with a timeout of 5 minutes. If nothing is transferred for a period of time, the connection will be closed after the fifth minute. In HTTP communication spanning multiple components \(for example, from a sender, through the load balancer, to a Cloud Integration tenant, and from there to a receiver\), the actual timeout period is influenced by each of the timeout settings of the individual components that are interconnected between the sender and receiver \(to be more exact, of those components that can control the TCP session\). The component or device with the lowest number set for the idle session timeout will determine the timeout that will be used.

</td>
</tr>
<tr>
<td valign="top">

*Keep-Alive*

</td>
<td valign="top">

Select to signal to the server that the client wants to leave the connection open even after the initial request/response sequence.

> ### Note:  
> Once established, the connection is left open until either server or client closes the connection. If Keep-Alive is not selected, the connection is closed automatically after each request/response sequence.



</td>
</tr>
<tr>
<td valign="top">

*Compress Message*

</td>
<td valign="top">

Enables the WS endpoint to send compressed request messages to the WS Provider and to indicate to the WS Provider that it can handle compressed response messages.

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
> You can use this header, for example, to analyze the message processing run \(when level Trace has been enabled for monitoring\). Furthermore, you can use this header to define error handling steps after the integration flow has called the SOAP receiver.

> ### Caution:  
> It is recommended that you model the integration flow in such a way that header `CamelHttpResponseCode` is deleted after is has been evaluated. The reason is that this header can have an impact on the communication with a sender system in case one of the following sender adapters are used in the same integration flow: SOAP 1.x, XI, IDoc, SOAP SAP RM. This is because in such a case the value of header `CamelHttpResponseCode` also determines the response code used in the connection with the sender system. This is in most cases not the desired behavior.
> 
> As a specific situation note that in case the value of header `CamelHttpResponseCode` is set to 202, the system interprets this value in such a way that messages are processed according to a one-way operation. In such a case, even if the sender adapter normally supports a request-reply pattern \(like, for example, the SOAP SAP RM adapter\), SAP Cloud Integration does not send back a response to the sender.
> 
> Furthermore, note that in case the SOAP 1.x receiver channel uses a WSDL with a one-way operation, header `CamelHttpResponseCode` is not set \(even if feature *Return HTTP Response Code as Header* is activated\).



</td>
</tr>
<tr>
<td valign="top">

*Clean Up Request Headers*

</td>
<td valign="top">

Select this option to clean up the adapter-specific headers after the receiver call.

</td>
</tr>
</table>



Select the *WS-Security* tab and provide values in the fields as follows.

Select the *WS-Security* tab and provide values in the fields as follows.

**WS-Security**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*WS-Security Configuration*

</td>
<td valign="top">

Specifies how WS-Security settings are to be configured.

-   *Via Manual Configuration in Channel*

    The security settings are to be configured manually \(see the attributes listed next\).

-   *Based on Policies in WSDL*

    The security settings are specified as part of the receiver endpoint \(within the endpoint WSDL\) in elements as defined by the WS-Policy standard.

-   *None*

    No WS-Security is applied for the message exchange.




</td>
</tr>
<tr>
<td valign="top">

*Username Token*

</td>
<td valign="top">

Specifies how the user name token is to be configured. Select this option to authenticate at message level based on a user ID and a password \(transported within a SOAP message\).

If you have selected *Via Manual Configuration in Channel*, you have the following options:

-   *Plain Text Password*

    The password is transferred in plain text \(HTTPS encrypted\).

-   *Hashed Password*

    Cryptographic hash function is applied to the password.

-   *None*

    No user name token is applied.


If you have selected the option *Plain Text Password* or *Hashed Password*, enter the *Credential Name*, that is, the alias that was assigned to the authorized user and password during tenant deployment.

> ### Note:  
> It depends on additional adapter settings how the token is treated during runtime \(in particular, whether the token is encrypted or not\).
> 
> If the security settings are defined by the endpoint WSDL \(if you have selected *Based on Policies in WSDL*\), the token is treated according to what is defined within the WSDL.
> 
> If the security settings are defined manually \(if you have selected *Via Manual Configuration in Channel*\), the token is treated according to the selected *WS-Security Type*:
> 
> -   *Sign Message* selected: The token is not encrypted.
> 
> -   *Sign and Encrypt Message* selected: The token is encrypted.



</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(only if the option *Based on Policies in WSDL* or *Via Manual Configuration in Channel* is selected\)

</td>
<td valign="top">

Alias that was assigned to the authorized user and password during tenant deployment.

</td>
</tr>
<tr>
<td valign="top">

*WS-Security Type*

\(only if the option *Via Manual Configuration in Channel* is selected\)

</td>
<td valign="top">

Specifies the combination of message protection methods that are to be applied. There are the following options:

-   *Sign Message*

    Tenant signs the payload.

-   *Sign and Encrypt Message*

    Tenant signs and encrypts the payload.

-   *None*

    No WS-Security type is applied.




</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias for Signing*

</td>
<td valign="top">

Specify an alias for the tenant private key that is to be used to sign the message.

The tenant private key is used to sign the request message \(that is sent to the WS provider \(receiver\)\). The tenant private key has to be part of the tenant keystore.

More information: [WS-Security Configuration for the Receiver SOAP 1.x Adapter](ws-security-configuration-for-the-receiver-soap-1-x-adapter-e9f42bf.md)

</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias for Encryption*

\(only if the option *Sign and Encrypt Message* is selected\)

</td>
<td valign="top">

Specify an alias for the public key that is to be used to encrypt the message.

The receiver \(WS provider\) public key is used to encrypt the request message \(that is sent to the receiver\). This key has to be part of the tenant keystore.

More information: [WS-Security Configuration for the Receiver SOAP 1.x Adapter](ws-security-configuration-for-the-receiver-soap-1-x-adapter-e9f42bf.md)

</td>
</tr>
<tr>
<td valign="top">

*Set Time Stamp* 

</td>
<td valign="top">

Select this option to send a time stamp along with the message.

If a Request-Response pattern is configured, a time stamp is expected in the response message.

</td>
</tr>
<tr>
<td valign="top">

*Receiver is Basic Security Profile Compliant*

</td>
<td valign="top">

Leave this option selected if the receiver system complies with the basic security profile \(as assumed to be the case for most systems\). Deselect this option if the receiver system does not support this security profile.



</td>
</tr>
<tr>
<td valign="top">

*Layout*

\(only if the option *Via Manual Configuration in Channel* is selected\)

</td>
<td valign="top">

-   *Strict*

    Items are added to the security header following numbered layout rules according to a general principle of 'declare before use'.

-   *Lax*

    Items are added to the security header in any order that conforms to WSS: SOAP Message Security.




</td>
</tr>
<tr>
<td valign="top">

*Algorithm Suite Assertion*

\(only if the option *Via Manual Configuration in Channel* is selected\)

</td>
<td valign="top">

Specifies which algorithms are used by the WS consumer.

</td>
</tr>
<tr>
<td valign="top">

*Initiator Token*

\(only if the option *Via Manual Configuration in Channel* is selected\)

</td>
<td valign="top">

These entries define policies for the WS consumer:

-   *Include Strategy*

    Value *Always to Recipient* ensures that the WS consumer sends the certificate along with the message.

-   *X509 Token Assertion*

    Defines the format of the certificate being sent by the WS consumer along with the message.

    -   *Require Issuer Serial Reference*

    -   *Require Key Identifier Reference*

    -   *Require Thumbprint Reference*

    -   *Wss X509 V3 Token 10*





</td>
</tr>
<tr>
<td valign="top">

*Recipient Token*

\(only if the option *Via Manual Configuration in Channel* is selected\)

</td>
<td valign="top">

These entries define policies for the WS consumer:

-   *Include Strategy*

    Value *Always to Initiator* adds the certificate to the response message.


-   *X509 Token Assertion*

Defines the format of the certificate being sent by the WS consumer along with the message.

-   *Require Issuer Serial Reference*

-   *Require Key Identifier Reference*

-   *Require Thumbprint Reference*

-   *Wss X509 V3 Token 10*




</td>
</tr>
</table>

See [WS-Security Configuration for the Receiver SOAP 1.x Adapter](ws-security-configuration-for-the-receiver-soap-1-x-adapter-e9f42bf.md) for more information.

**Related Information**  


[Setting Up Principal Propagation \(Example Scenario\)](../40-RemoteSystems/setting-up-principal-propagation-example-scenario-34eff84.md "Use principal propagation to forward the principal (identity of a user) across several connections in a complex system landscape.")

[https://blogs.sap.com/2018/01/25/cloud-integration-soap-adapter-web-service-security/](https://blogs.sap.com/2018/01/25/cloud-integration-soap-adapter-web-service-security/)

[https://blogs.sap.com/2018/01/24/cloud-integration-wss-between-cloud-integration-and-sap-po-soap-adapter/](https://blogs.sap.com/2018/01/24/cloud-integration-wss-between-cloud-integration-and-sap-po-soap-adapter/)

[WS-Security Configuration for the Receiver SOAP 1.x Adapter](ws-security-configuration-for-the-receiver-soap-1-x-adapter-e9f42bf.md "")

[OAuth 2.0](../40-RemoteSystems/oauth-2-0-3823134.md#loio382313443b8d4453b0fd536b82b9e15d "OAuth 2.0 allows a user to grant a client access to a protected resource (hosted by a resource server). The user typically restricts the access of the client and doesn't allow full access.")

