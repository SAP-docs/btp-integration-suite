<!-- loio2937e5ca6ef448cfb21451a2461cc2a6 -->

# Personas for Cloud Integration

When you perform user management tasks using SAP BTP cockpit, you find a set of predefined roles that you can assign to users of the account. According to the main tasks associated with integration projects, these roles are associated to certain persona relevant for an integration project.

Personas cover the different tasks associated with an integration project. To assign roles that are application-based, see [Configuring User Access to SAP Integration Suite](../configuring-user-access-to-sap-integration-suite-2c6214a.md).

**Personas**


<table>
<tr>
<th valign="top">

Persona

</th>
<th valign="top">

Role Collection

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Read-only persona

</td>
<td valign="top">

PI\_Read\_Only

</td>
<td valign="top">

Enables you to connect to a tenant and to monitor messages.

This persona enables you to access \(read-only\) artifacts in the Monitoring area, as well as to download integration flow artifacts and WSDL.

This persona includes authorization to tasks like:

-   Monitor integration flows and the status of integration artifacts

-   View pre-shipped standard packages in the *Discover* view

-   View packages and their artifacts in *Design* workspace

-   View data store entries, access policies, B2B partner profiles and agreements, and design time artifact locks




</td>
</tr>
<tr>
<td valign="top">

Business expert

</td>
<td valign="top">

PI\_Business\_Expert

</td>
<td valign="top">

Enables a business expert to read data which might contain sensitive business content \(like message payloads or attachments\).

This persona includes authorization to tasks like:

-   Monitor integration flows and the status of integration artifacts

-   Read the message payload and attachments, design time artifact locks

-   View and edit trace configurations

-   View data store entries, variables and its content

-   Edit contact persons for company profile and trading partner profile


> ### Note:  
> This is an add-on role collection, which can be assigned in addition to other personas like *PI\_Integration\_Developer* or *PI\_Read\_Only* to enhance them with the authorization to view business content.



</td>
</tr>
<tr>
<td valign="top">

Integration developer

</td>
<td valign="top">

PI\_Integration\_Developer

</td>
<td valign="top">

Enables an integration developer to discover, design, and deploy integration artifacts.

This persona includes authorization to tasks like:

-   View and copy pre-shipped standard packages in the *Discover* view

-   Create, edit, import, export, delete package with its artifacts in the *Design* workspace.

-   Deploy/undeploy integration artifacts

-   View message processing details

-   Create company profile, partner profile, agreement templates. Create and publish trading partner agreements




</td>
</tr>
<tr>
<td valign="top">

Tenant administrator

</td>
<td valign="top">

PI\_Administrator

</td>
<td valign="top">

Enables the administrator to perform administrative tasks on the tenant.

This persona includes authorization to tasks like:

-   Handling tenant level settings like transport, connection to SAP Process Orchestration systems, manage software updates, and a few more.

-   Managing access policies to restrict user access of integration content

-   Monitoring integration flows and the status of integration artifacts

-   Deploying security content

-   Deploying integration content \(such like integration flows, for example\)

-   Deleting messages from transient data store

-   Deleting design time artifact locks




</td>
</tr>
<tr>
<td valign="top">

Partner Directory configurator

</td>
<td valign="top">

There is no predefined role collection for the Partner Directory configurator.

You need to assign the role template `AuthGroup_TenantPartnerDirectoryConfigurator` to the service instance for the related API client.

</td>
<td valign="top">

Enables the Partner Directory administrator to read and write Partner Directory content.

</td>
</tr>
</table>



<a name="loio2937e5ca6ef448cfb21451a2461cc2a6__section_fdd_gm5_p4b"/>

## Roles to Define Permissions to Call Integration Flow Endpoints

In order to enable a sender system to process messages on Cloud Integration Using HTTPS/basic authentication \(based on a user registered by an identity provider\), you need to assign the following entities to the associated user:

-   Role template `MessagingSend` 

    Using this role template, you need to define a role collection and assign the role collection to the IdP user.

    More information: [Basic Authentication of IdP User for Integration Flow Processing](../40-RemoteSystems/basic-authentication-of-idp-user-for-integration-flow-processing-5d46e56.md)


> ### Note:  
> **Note Related to Role Configuration**
> 
> Depending on the chosen inbound authorization option, you define permissions for sender systems to call integration flow endpoints in different ways:
> 
> ****
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Option
> 
> </th>
> <th valign="top">
> 
> Summary of Steps
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> Basic authentication of a user registered at an identity provider \(IdP\)
> 
> </td>
> <td valign="top">
> 
> Use SAP BTP cockpit to define a role collection that contains the predefined role template `MessagingSend` and assign the role collection to the IdP user \(under *Security* \> *Trust Configuration*\). The role template `MessagingSend` is provided by default in your subaccount to define permissions for sender systems to call integration flow endpoints for this use case.
> 
> See: [Basic Authentication of IdP User for Integration Flow Processing](../40-RemoteSystems/basic-authentication-of-idp-user-for-integration-flow-processing-5d46e56.md)
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Authentication with an OAuth client \(service instance\)
> 
> </td>
> <td valign="top">
> 
> Use the Cloud Integration *Monitor* application and select the *User Roles* tile under *Manage Security*. When doing this, you can either use the predefined role `ESBMessaging.send` or create a custom role.
> 
> Create service instance and service key using SAP BTP cockpit. During this step, you need the role specified with the *User Roles* tile.
> 
> See:
> 
> -   [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)
> 
> -   [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)
> 
> -   [Basic Authentication with clientId and clientsecret for Integration Flow Processing](../40-RemoteSystems/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)
> 
> -   [Basic Authentication with clientId and clientsecret for Integration Flow Processing](../40-RemoteSystems/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)
> -   [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)
> -   [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)
> 
> 
> 
> </td>
> </tr>
> </table>

**Related Information**  


[Tasks and Permissions for Cloud Integration](tasks-and-permissions-for-cloud-integration-556d557.md "")

