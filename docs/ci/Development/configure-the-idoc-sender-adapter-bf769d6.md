<!-- loiobf769d68d95b458d87290dd2d37024b3 -->

# Configure the IDoc Sender Adapter

The IDoc sender adapter enables SAP Cloud Integration to receive Intermediate Document \(IDoc\) messages from a sender.

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

> ### Note:  
> The IDoc sender adapter cannot process composite IDoc messages \(bulk messages\).



<a name="loiobf769d68d95b458d87290dd2d37024b3__section_ef4_zd1_sgb"/>

## Supported Headers

-   SapAuthenticatedUserName

    Contains the user name of the client that calls the integration flow.


The following specific headers are set by the IDoc sender adapter and can be used in the subsequent steps of the integration flow.

-   SapIDocType

-   SapIDocTransferId

-   SapIDocDbId


More information: [Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md)



<a name="loiobf769d68d95b458d87290dd2d37024b3__section_rj4_xd1_sgb"/>

## Configuring the Adapter

Once you have created a sender channel and selected the IDoc adapter, you can configure the following attributes. To change the configurations, you need to configure a new channel.

The *General* tab shows general information such as the adapter type, its direction \(sender or receiver\), the transport protocol, and the message protocol.

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

Relative endpoint address on which Cloud Integration can be reached by incoming requests, for example, `/GetEmployeeDetails`.

> ### Note:  
> When you specify the endpoint address `/path`, a sender can also call the integration flow through the endpoint address `/path/<any string>` \(for example, `/path/test/`\).
> 
> Be aware of the following related implication: When you in addition deploy an integration flow with endpoint address `/path/test/`, a sender using the `/path/test` endpoint address will now call the newly deployed integration flow with the endpoint address `/path/test/`. When you now undeploy the integration flow with endpoint address `/path/test`, the sender again calls the integration flow with endpoint address `/path` \(original behavior\). Therefore, be careful *reusing* paths of services. It is better using completely separated endpoints for services.



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

Select the *Processing* tab and provide values in the fields as follows.

**Processing**


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

Invalid XML Character Handling

</td>
<td valign="top">

Select how to handle XML documents containing characters which are not valid in XML version 1.0/1.1. Depending on the XML version of the source message, the adapter checks the characters against the respective range allowed. Choose between the following options:

-   *Throw Error*: An error is thrown during runtime.

-   *Remove*: Invalid characters are removed.

-   *Substitute*: Invalid characters are substituted by \#.


If this configuration option is not available \(because your are using an older version, for example\), the default behavior is to throw an exception.

> ### Note:  
> A character is considered valid, if it is part of the range listed here:
> 
> -   *Character Range for XML 1.0*:
> 
>     `#x9 | #xA | #xD | [#x20-#xD7FF] | [#xE000-#xFFFD] | [#x10000-#x10FFFF]`*/\* any Unicode character, excluding the surrogate blocks, FFFE, and FFFF. \*/*
> 
>     See also: [https://www.w3.org/TR/2008/REC-xml-20081126/\#charsets](https://www.w3.org/TR/2008/REC-xml-20081126/#charsets).
> 
> -   *Character Range for XML 1.1*:
> 
>     `[#x1-#xD7FF] | [#xE000-#xFFFD] | [#x10000-#x10FFFF]` */\* any Unicode character, excluding the surrogate blocks, FFFE, and FFFF. \*/*
> 
>     See also: [https://www.w3.org/TR/2006/REC-xml11-20060816/\#charsets](https://www.w3.org/TR/2006/REC-xml11-20060816/#charsets).
> 
>     Restricted characters will be escaped automatically when *Remove* or *Substitute* is used: `[#x1-#x8] | [#xB-#xC] | [#xE-#x1F] | [#x7F-#x84] | [#x86-#x9F]`.



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

**Related Information**  


[Defining Permissions for Senders to Process Messages on a Runtime Node](../Operations/defining-permissions-for-senders-to-process-messages-on-a-runtime-node-24585cc.md "")

[Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md "")

[Setting Up Inbound HTTP Connections \(Integration Flow Processing\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-integration-flow-processing-neo-environment-778c7e7.md "You can use various sender adapters (for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter) to connect the tenant to a sender system so that the sender can send messages to Cloud Integration over the HTTP protocol.")

