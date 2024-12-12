<!-- loioa178913a4d3245ab9bff2a0edcc331d5 -->

# Configure the SOAP \(SOAP 1.x\) Sender Adapter

The SOAP \(SOAP 1.x\) sender adapter enables a SAP BTP tenant to exchange messages with a sender system that supports Simple Object Access Protocol \(SOAP\) 1.1 and 1.2.

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





You've the option to set SOAP headers using Groovy script \(for example, using the Script step\).

Supported Header \(Sender Adapter\):

-   SapAuthenticatedUserName

    Contains the user name of the client that calls the integration flow.




> ### Caution:  
> Usage of Different WSDL Binding Styles:
> 
> Note that messages that contain RPC-style bindings aren't supported by the SOAP sender channel. Also WSDL files using RPC-style bindings aren't supported. Use document-style payloads and WSDL files.
> 
> A WSDL binding describes how the service is bound to a message protocol. For the processing of SOAP messages, you can choose from the following binding types:
> 
> -   Document/encoded \(not recommended in WS Basic Profile Version 1.0\)
> 
> -   Document/literal
> 
> 
> RPC stands for *Remote Procedure Call*. For more information on these options and the meaning of *literal* and *encoded*, see [http://www.w3.org/TR/2001/NOTE-wsdl-20010315](http://www.w3.org/TR/2001/NOTE-wsdl-20010315).



Once you've created a sender channel and selected the SOAP \(SOAP 1.x\) sender Adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

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

Relative endpoint address on which the integration runtime expects incoming requests, for example, `/HCM/GetEmployeeDetails`.

> ### Note:  
> When you specify the endpoint address `/path`, a sender can also call the integration flow through the endpoint address `/path/<any string>` \(for example, `/path/test/`\).
> 
> Be aware of the following related implication: When you in addition deploy an integration flow with endpoint address `/path/test/`, a sender using the `/path/test` endpoint address will now call the newly deployed integration flow with the endpoint address `/path/test/`. When you now undeploy the integration flow with endpoint address `/path/test`, the sender again calls the integration flow with endpoint address `/path` \(original behavior\). Therefore, be careful *reusing* paths of services. It is better using completely separated endpoints for services.



</td>
</tr>
<tr>
<td valign="top">

*Use WS-Addressing* 

</td>
<td valign="top">

Select this option to accept addressing information from message information headers \(provided by the sender\) during runtime.

</td>
</tr>
<tr>
<td valign="top">

*URL to WSDL* 

</td>
<td valign="top">

URL pointing to the WSDL defining the WS provider endpoint \(of the receiver\).

> ### Note:  
> With this parameter, you specify the WSDL that describes the service provided by SAP Cloud Integration for the sender system.

To select the WSDL from a source, you've the following options:

-   Select a WSDL from your file system.

-   Select a WSDL from your integration flow resources \(see [Manage Resources](manage-resources-b5968b2.md)\).

    In the *Resources* view, you can upload an individual WSDL file or an archive file \(file ending with `.zip`\) that contains multiple WSDLs or XSDs, or both. For example, you can upload a WSDL that contains an imported XSD referenced by an `xsd:import` statement. This means that if you want to upload a WSDL and dependent resources, you need to add the parent file along with its dependencies in a single archive \(`.zip` file\).

    In particular, when uploading a WSDL resource to your integration flow, you can use the ES Repository as source.


> ### Note:  
> -   If you specify a WSDL, you also have to specify the name of the selected service and the name of the port selected for this service. These fields must have a namespace prefix.
> 
>     Expected format: `<namespace>:<service_name>`
> 
>     Example: `p1:MyService`
> 
> -   Don't use WSDLs with blanks.
> 
>     We recommend that you don't use blanks in WSDL names or directories, as this can lead to runtime issues.

You can download the WSDL from the Web UI *Monitor* section by selecting the deployed integration flow \(under *Manage Integration Content*\). Under Endpoints, after the integration flow endpoint address, you find download options \(*WSDL* or *WSDL without policies*\).

The WSDL download doesn't work for WSDLs with external references because these WSDLs can't be parsed.

For more information on how to work with WSDL resources, refer to the following blog: [Cloud Integration – Usage of WSDLs in the SOAP Adapter](https://blogs.sap.com/2018/06/28/cloud-integration-usage-of-wsdls-in-the-soap-adapter/)

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

Name of the selected endpoint of  a selected service \(that you provide in the Service Name field\) contained in the referenced WSDL.

</td>
</tr>
<tr>
<td valign="top">

*Processing Settings*

\(only relevant for the one-way exchange pattern\)

</td>
<td valign="top">

-   *WS Standard*: Message is executed with WS standard processing mechanism. Errors aren't returned to the consumer.
-   *Robust*: WSDL provider invokes service synchronously and the processing errors are returned to the consumer.



</td>
</tr>
</table>



> ### Caution:  
> SOAP attachments with the same content-ID aren't supported.
> 
> If there are duplicate attachments \(with the same content-ID\), the adapter generates unique content-ID's by attaching a GUID to the original content-ID of the duplicates.
> 
> If the content-ID isn't set, the adapter generates a new one by generating a GUID.
> 
> Example:
> 
> Incoming message contains the following attachments:
> 
> -   myAttachment
> 
> -   myAttachment
> 
> -   myAttachmentUnique
> 
> -   \(blank\)
> 
> 
> Result after processing of the message by SOAP sender adapter:
> 
> -   myAttachment\_c242875-z7c6-9764-99yx-8652879786d
> 
> -   myAttachment\_c25201a5-f7c6-4113-88bc-617289fd676c
> 
> -   myAttachmentUnique
> 
> -   a52c9658-90c9-11ed-a1eb-0242ac120002



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

Specifies the way how WS-Security settings are to be configured.

-   *Via Manual Configuration in Channel*

    The security settings are manually to be configured \(see listed attributes next\).

-   *None*

    No WS-Security is applied for message exchange.

    If you select this option, no further WS-Security-relevant settings can be applied.




</td>
</tr>
<tr>
<td valign="top">

*WS-Security Type*

</td>
<td valign="top">

Specifies the combination of message protection methods that are to be applied. There are the following options:

-   *Verify Message and Sign Response \(default\)*

    A signed payload is expected by the tenant, and the signature has to be verified. For Request-Reply messages, the response is signed.

-   *Verify and Decrypt Message and Sign and Encrypt Response*

    A signed and encrypted payload is expected by the tenant. The signature has to be verified and the payload has to be decrypted. For Request-Reply messages, the response is signed and encrypted.


More information: [WS-Security Configuration for the Sender SOAP 1.x Adapter](ws-security-configuration-for-the-sender-soap-1-x-adapter-e53bb5c.md)

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias for Response Signing*

</td>
<td valign="top">

Specify an alias for the private key that is to be used to sign the response message.

The tenant private key is used to sign the response message \(that is sent back to the sender/WS consumer\). The tenant private key has to be part of the tenant keystore.

</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias for Response Encryption*

\(only if for *WS-Security Type* the option *Verify and Decrypt Message and Sign and Encrypt Message* is selected\)

</td>
<td valign="top">

Specify an alias for the public key that is to be used to encrypt the response message \(that is sent back to the sender/WS consumer\)..

The sender public key is used to sign the response message. This key has to be part of the tenant keystore.

</td>
</tr>
<tr>
<td valign="top">

*Signing Order* 

\(only if for *WS-Security Type* the option *Verify and Decrypt Message and Sign and Encrypt Message* is selected\)

</td>
<td valign="top">

Defines the order in which signing and encryption must be applied. There are the following options:

-   *Sign Before Encryption* \(default\)
-   *Encrypt before Signing*



</td>
</tr>
<tr>
<td valign="top">

*Algorithm Suite Assertion*

</td>
<td valign="top">

Specifies which algorithms are to be used by the WS consumer.

</td>
</tr>
<tr>
<td valign="top">

*Save Incoming Signed Message*

</td>
<td valign="top">

Select this option if the incoming signed \(and encrypted\) message is to be stored.

</td>
</tr>
<tr>
<td valign="top">

*Check Time Stamp*

</td>
<td valign="top">

Select this option, if the sender \(WS consumer\) sends a time stamp along with the message.

In case a request-response pattern is configured, a time stamp is added to the response message.

</td>
</tr>
<tr>
<td valign="top">

*Sender is Basic Security Profile Compliant*

</td>
<td valign="top">

As default setting, select this option.

This option should be selected in case the sender system supports a dedicated security level that is described by the Basic Security Profile \(as assumed to be the case for most systems\). Only in case the sender system doesn't support this security profile, deselect this option.

</td>
</tr>
<tr>
<td valign="top">

*Initiator Token*

</td>
<td valign="top">

-   *Include Strategy*

    Preset value *Always to Recipient* ensures that the WS consumer sends the certificate along with the message.

-   *X509 Token Assertion*

    Defines the format of the certificate being sent by the WS consumer along with the message.




</td>
</tr>
<tr>
<td valign="top">

*Recipient Token*

</td>
<td valign="top">

*Include Strategy*

There are the following options:

-   *Never*

-   *Always to Initiator* 

    If selected, adds the certificate to the response message.




</td>
</tr>
</table>

See [WS-Security Configuration for the Sender SOAP 1.x Adapter](ws-security-configuration-for-the-sender-soap-1-x-adapter-e53bb5c.md) for more information.

Select the *Conditions* tab and provide values in the fields as follows.

**Conditions**


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

Maximum Message Size

</td>
<td valign="top">

This parameter allows you to configure a maximum size for inbound messages \(smallest value for a size limit is 1 MB\). All inbound messages that exceed the specified size \(per integration flow and on the runtime node where the integration flow is deployed\) are blocked.

To configure the maximum message size, you can specify the following parameters:

-   Body Size

-   Attachment Size


If a message is rejected because it exceeds the configured limit, the sender receives an error message.

</td>
</tr>
</table>

**Related Information**  


[https://www.oasis-open.org/committees/tc\_home.php?wg\_abbrev=wss](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=wss)

[Defining Permissions for Senders to Process Messages on a Runtime Node](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/24585cc503334e6c917ef383efb5558a.html "") :arrow_upper_right:

[Setting Up Principal Propagation \(Example Scenario\)](../40-RemoteSystems/setting-up-principal-propagation-example-scenario-34eff84.md "Use principal propagation to forward the principal (identity of a user) across several connections in a complex system landscape.")

[https://blogs.sap.com/2018/01/25/cloud-integration-soap-adapter-web-service-security/](https://blogs.sap.com/2018/01/25/cloud-integration-soap-adapter-web-service-security/)

[https://blogs.sap.com/2018/01/24/cloud-integration-wss-between-cloud-integration-and-sap-po-soap-adapter/](https://blogs.sap.com/2018/01/24/cloud-integration-wss-between-cloud-integration-and-sap-po-soap-adapter/)

[WS-Security Configuration for the Sender SOAP 1.x Adapter](ws-security-configuration-for-the-sender-soap-1-x-adapter-e53bb5c.md "")

[Setting Up Inbound HTTP Connections (Integration Flow Processing), Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/778c7e7835ff46408aafe0d499720dc7.html "You can use various sender adapters (for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter) to connect the tenant to a sender system so that the sender can send messages to Cloud Integration over the HTTP protocol.") :arrow_upper_right:

