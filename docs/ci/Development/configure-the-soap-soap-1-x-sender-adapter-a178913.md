<!-- loioa178913a4d3245ab9bff2a0edcc331d5 -->

# Configure the SOAP \(SOAP 1.x\) Sender Adapter

The SOAP \(SOAP 1.x\) sender adapter enables a SAP BTP tenant to exchange messages with a sender system that supports Simple Object Access Protocol \(SOAP\) 1.1 and 1.2.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](../IntegrationSettings/runtime-profiles-8007daa.md).
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
> Note that messages that contain RPC-style bindings aren't supported by the SOAP sender channel. Also WSDL files using RPC-style bindings aren'tnot supported. Use document-style payloads and WSDL files.
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

*Service Definition* 

</td>
<td valign="top">

The service definition consists of a service, an endpoint, and the exchange pattern. For one-way services, you can additionally specify the runtime behavior.

You can select the following options:

-   *Manual*: Set this option to use the service definition provided by the system and define the message exchange pattern manually. The default service definition provides a generic message format.

-   *WSDL*: Set this option to use a service definition from a WSDL provided in the adapter configuration. This will also include the message formats.

    > ### Caution:  
    > Policies contained in the WSDL aren't considered, that is, the configuration of WSS and other policies must be done via the adapter configuration.


> ### Note:  
> You access the WSDL via *Operations View* \> *Manage Integration Content*.



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

*Message Exchange Pattern*

\(only if *Service Definition*: *Manual* is selected\)

</td>
<td valign="top">

Specifies the kind of messages that are processed by the adapter.

-   *Request-Reply*: When selected, the adapter processes both request and response \(synchronous message exchange\).

    > ### Tip:  
    > When using this option, the response code can accidentally be overwritten by a called receiver. Assume that, for example the integration flow contains an SOAP sender adapter \(with a *Request-Reply* pattern\) and an HTTP receiver adapter. Let's furthermore assume that the HTTP receiver returns an HTTP response code 202 \(as it has accepted the call\). In this case, the SOAP sender adapter returns in the reply also HTTP response code 202 instead of 200 \(OK\). To overcome this situation, you've to remove the header `CamelHttpResponseCode` before the message reply is sent back to the sender.

-   *One-Way*

    When selected, the message is processed asynchronously. Use this option if in your scenario the sender just needs to initiate the request without being interested in getting to know if the request is processed successfully.




</td>
</tr>
<tr>
<td valign="top">

*URL to WSDL*

\(only if as *Service Definition* the option *WSDL* is selected\)

</td>
<td valign="top">

URL pointing to the WSDL defining the WS provider endpoint \(of the receiver\).

> ### Note:  
> With this parameter, you specify the WSDL that describes the service provided by SAP Cloud Integration for the sender system.

To select the WSDL from a source, you've the following options:

-   Select a WSDL from your file system.

-   Select a WSDL from your integration flow resources \(see [Manage Resources of an Integration Flow](manage-resources-of-an-integration-flow-b5968b2.md)\).

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

You can download the WSDL from the Web UI *Monitor* section by selecting the deployed integration flow \(under *Manage Integration Content*\). Under Endpoints, below the integration flow endpoint address, you find download options \(*WSDL* or *WSDL without policies*\).

The WSDL download doesn't work for WSDLs with external references because these WSDLs can't be parsed.

For more information on how to work with WSDL resources, refer to the following blog: [Cloud Integration – Usage of WSDLs in the SOAP Adapter](https://blogs.sap.com/2018/06/28/cloud-integration-usage-of-wsdls-in-the-soap-adapter/)

</td>
</tr>
<tr>
<td valign="top">

*Service* 

\(only if as *Service Definition* the option *WSDL* is selected\)

</td>
<td valign="top">

Name of the selected service contained in the referenced WSDL.

</td>
</tr>
<tr>
<td valign="top">

*Endpoint* 

\(only if as *Service Definition* the option *WSDL* is selected\)

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
<tr>
<td valign="top">

*Authorization* 

</td>
<td valign="top">

Specifies the authorization option for the sender.

> ### Note:  
> The option *client certificate* is not recommended. Instead, it is recommended to use the more secure option *role-based authorization with certificate-to-user mapping*.

You can select one of the following options:

-   *Client Certificate*: Sender authorization is checked on the tenant by evaluating the subject/issuer distinguished name \(DN\) of the certificate \(sent together with the inbound request\). You can use this option together with the following authentication option: *Client-certificate authentication \(without certificate-to-user mapping\)*.

-   *User Role*: Sender authorization is checked based on roles defined on the tenant for the user associated with the inbound request. You can use this option together with the following authentication options:

    -   *Basic authentication* \(using the credentials of the user\)

        The authorizations for the user are checked based on user-to-role assignments defined on the tenant.

    -   *Client-certificate authentication and certificate-to-user mapping*

        The authorizations for the user derived from the certificate-to-user mapping are checked based on user-to-role assignments defined on the tenant.



Depending on your choice, you can also specify one of the following properties:

-   *Client Certificate*

    Allows you to select one or more client certificates \(based on which the inbound authorization is checked\).

    Choose *Add* to add a new certificate for inbound authorization for the selected adapter. You can then select a certificate stored locally on your computer. You can also delete certificates from the list.

    For each certificate, the following attributes are displayed: *Subject DN* \(information used to authorize the sender\) and *Issuer DN* \(information about the certificate authority that issues the certificate\).

-   *User Role*

    Allows you to select a role based on which the inbound authorization is checked.

    Choose *Select* to get a list of all available roles.

    The role *ESBMessaging.send* is provided by default. It is a predefined role provided by SAP that authorizes a sender system to process messages on a tenant. However, using SAP BTP Cockpit, you can also define *custom roles* for the runtime node as well. When you choose *Select*, a selection of all custom roles defined that way is offered.

    > ### Note:  
    > Note the following:
    > 
    > -   You can also type in a role name. This has the same result as selecting the role from the value help: Whether the inbound request is authenticated depends on the correct user-to-role assignment defined in SAP BTP Cockpit.
    > 
    > -   When you externalize the user role, the value help for roles is offered in the integration flow configuration as well.
    > 
    > -   If you have selected a product profile for SAP Process Orchestration, the value help will only show the default role *ESBMessaging.send*.




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

    The security settings are manually to be configured \(see below listed attributes\).

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

You can also enter `${header.headername}` or`${property.propertyname}`to read the name dynamically from a header or exchange property.

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

*Signature Algorithm* 

</td>
<td valign="top">

Specify a signature algorithm to be applied when signing the response message.

Possible values:

-   SHA1 \(default value\)

-   SHA256

-   SHA512




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

[Defining Permissions for Senders to Process Messages on a Runtime Node](../Operations/defining-permissions-for-senders-to-process-messages-on-a-runtime-node-24585cc.md "")

[Setting Up Principal Propagation \(Example Scenario\)](../ConnectionSetup/setting-up-principal-propagation-example-scenario-34eff84.md "Use principal propagation to forward the principal (identity of a user) across several connections in a complex system landscape.")

[https://blogs.sap.com/2018/01/25/cloud-integration-soap-adapter-web-service-security/](https://blogs.sap.com/2018/01/25/cloud-integration-soap-adapter-web-service-security/)

[https://blogs.sap.com/2018/01/24/cloud-integration-wss-between-cloud-integration-and-sap-po-soap-adapter/](https://blogs.sap.com/2018/01/24/cloud-integration-wss-between-cloud-integration-and-sap-po-soap-adapter/)

[WS-Security Configuration for the Sender SOAP 1.x Adapter](ws-security-configuration-for-the-sender-soap-1-x-adapter-e53bb5c.md "")

[Setting Up Inbound HTTP Connections \(Integration Flow Processing\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-integration-flow-processing-neo-environment-778c7e7.md "You can use various sender adapters (for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter) to connect the tenant to a sender system so that the sender can send messages to Cloud Integration over the HTTP protocol.")

