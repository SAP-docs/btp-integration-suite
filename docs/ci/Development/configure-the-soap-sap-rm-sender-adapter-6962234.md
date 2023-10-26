<!-- loio69622346a10c4d5086a9b3e4f052337a -->

# Configure the SOAP \(SAP RM\) Sender Adapter

The SOAP \(SAP RM\) Sender Adapter exchanges messages with a sender system based on the SOAP communication protocol \(1.1. and 1.2\) and SAP Reliable Messaging \(SAP RM\) as the message protocol. SAP RM is a simplified communication protocol for asynchronous Web service communication that does not require the use of Web Service Reliable Messaging standards. A size limit for the inbound message can be configured for the sender adapter.

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

You have the option to set SOAP headers using Groovy script \(for example, using the Script step\).

Supported Header \(Sender Adapter\):

-   SapAuthenticatedUserName

    Contains the user name of the client that calls the integration flow.


Once you have created a sender channel and selected the SOAP \(SAP RM\) sender adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

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

Relative endpoint address at which the ESB listens to the incoming requests, for example, */HCM/GetEmployeeDetails*.

> ### Note:  
> When you specify the endpoint address `/path`, a sender can also call the integration flow through the endpoint address `/path/<any string>` \(for example, `/path/test/`\).
> 
> Be aware of the following related implication: When you in addition deploy an integration flow with endpoint address `/path/test/`, a sender using the `/path/test` endpoint address will now call the newly deployed integration flow with the endpoint address `/path/test/`. When you now undeploy the integration flow with endpoint address `/path/test`, the sender again calls the integration flow with endpoint address `/path` \(original behavior\). Therefore, be careful *reusing* paths of services. It is better using completely separated endpoints for services.



</td>
</tr>
<tr>
<td valign="top">

*URL to WSDL*

</td>
<td valign="top">

URL to the WSDL defining the WS provider endpoint \(of the receiver\). You can specify the WSDL by selecting a source to browse for a WSDL either from an On-Premise ES Repository or your local workspace.

Note that it is not required to point to a dedicated WSDL other than the one generated automatically for each SOAP SAP RM sender adapter. If you do not specify a WSDL, a generic one is used for the adapter. If you need to specify more details for the service, you can pick one from ES Repository.

In the *Resources* view, you can upload an individual WSDL file or an archive file \(file ending with `.zip`\) that contains multiple WSDLs or XSDs, or both. For example, you can upload a WSDL that contains an imported XSD referenced by an `xsd:import` statement. This means that if you want to upload a WSDL and dependent resources, you need to add the parent file along with its dependencies in a single archive \(`.zip` file\).

You can download the WSDL from the Web UI *Monitor* section by selecting the deployed integration flow \(under *Manage Integration Content*\). Under Endpoints, below the integration flow endpoint address, you find download options \(*WSDL* or *WSDL without policies*\).

The WSDL download doesn't work for WSDLs with external references because these WSDLs can't be parsed.

When configuring a SOAP SAP RM sender adapter, there’s no option to specify any service \(other than when configuring a SOAP SAP RM receiver adapter where you can specify service and endpoint\). If you use an uploaded WSDL, make sure that it contains exactly one service. Furthermore, consider that this adapter only supports one-way WSDLs. This means that the service definition in the WSDL must have only an `input` element, but no `output` element. A synchronous service definition \(with `input` and `output` element\) is not supported.

For more information, check out the following SAP Community blog: [Cloud Integration – Usage of WSDLs in the SOAP Adapter](https://blogs.sap.com/2018/06/28/cloud-integration-usage-of-wsdls-in-the-soap-adapter/).

</td>
</tr>
<tr>
<td valign="top">

*Processing Settings* 

</td>
<td valign="top">

This feature corresponds to an older version of this adapter. The reason why it is shown can be that you either have selected a certain product profile other than SAP Cloud Integration or \(in case you have selected SAP Cloud Integration product profile\) that you continue editing an integration flow which exists already for a certain time. If you still like to use this feature, you have the following options:

-   Standard: Message is executed with WS standard processing mechanism. Errors are not returned to the consumer.
-   Robust: WSDL provider invokes service synchronously and the processing errors are returned to the consumer.

When you use the up-to-date adapter version, the processing setting Robust is implicit activated.

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

> ### Note:  
> For Exactly-Once handling, the sender SOAP \(SAP RM\) adapter saves the protocol-specific message ID in the header SapMessageIdEx. If this header is set, SOAP \(SAP RM\) receiver use the content of this header as the message ID for outbound communication. Usually, this is the desired behavior and enables the receiver to identify any duplicates. However, if the sender system is also the receiver system, or several variants of the message are sent to the same system \(for example, in an external call or multicast\), the receiver system will incorrectly identify these messages as duplicates. In this case, the header SapMessageIdEx must be deleted \(for example, using a script\) or overwritten with a new generated message ID. This deactivates Exactly-Once processing \(that is, duplicates are no longer recognized by the protocol\).
> 
> If you want to set SOAP headers via the Camel header, the following table shows which Camel header corresponds to which SOAP header.
> 
> **Which Camel header corresponds to which SOAP header**
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> SOAP \(SAP RM\) Header
> 
> </th>
> <th valign="top">
> 
> Camel Header
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> MessageId
> 
> </td>
> <td valign="top">
> 
> SapMessageIdEx and SapMessageId
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> QualityOfService
> 
> </td>
> <td valign="top">
> 
> SapPlainSoapQoS
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> ExactlyOnce
> 
> </td>
> <td valign="top">
> 
> ExactlyOnce
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> ExactlyOnceInOrder
> 
> </td>
> <td valign="top">
> 
> ExactlyOnceInOrder
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> QueueId
> 
> </td>
> <td valign="top">
> 
> SapPlainSoapQueueId
> 
> </td>
> </tr>
> </table>

**Related Information**  


[Read and Modify SOAP Headers](read-and-modify-soap-headers-8a2827d.md "You can use the Script step to address SOAP headers.")

[Setting Up Principal Propagation \(Example Scenario\)](../ConnectionSetup/setting-up-principal-propagation-example-scenario-34eff84.md "Use principal propagation to forward the principal (identity of a user) across several connections in a complex system landscape.")

[https://wiki.scn.sap.com/wiki/display/ABAPConn/Plain+SOAP?original\_fqdn=wiki.sdn.sap.com](https://wiki.scn.sap.com/wiki/display/ABAPConn/Plain+SOAP?original_fqdn=wiki.sdn.sap.com)

[Defining Permissions for Senders to Process Messages on a Runtime Node](../Operations/defining-permissions-for-senders-to-process-messages-on-a-runtime-node-24585cc.md "")

[Setting Up Inbound HTTP Connections \(Integration Flow Processing\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-integration-flow-processing-neo-environment-778c7e7.md "You can use various sender adapters (for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter) to connect the tenant to a sender system so that the sender can send messages to Cloud Integration over the HTTP protocol.")

