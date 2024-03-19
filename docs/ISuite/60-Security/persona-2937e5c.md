<!-- loio2937e5ca6ef448cfb21451a2461cc2a6 -->

# Persona

When you perform user management tasks using SAP BTP cockpit, you find a set of predefined roles that you can assign to users of the account. According to the main tasks associated with integration projects, these roles are associated to certain persona relevant for an integration project.

Personas cover the different tasks associated with an integration project. To assign roles that are application-based, see [Configuring User Access](../configuring-user-access-2c6214a.md).

> ### Note:  
> This topic contains also information that is related to SAP BTP, Neo environment. Note that SAP Integration Suite is available only in the SAP BTP, Cloud Foundry environment, not in the Neo environment. However, many customers know SAP Cloud Integration as standalone service. The additional information should help those customers to relate the Neo-related information they know to the information relevant in the context of SAP Integration Suite.

**Authorization Groups**


<table>
<tr>
<th valign="top">

Persona

</th>
<th valign="top">

Authorization Group \(Neo\)

</th>
<th valign="top">

Role Collection \(Cloud Foundry\)

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

AuthGroup.ReadOnly

</td>
<td valign="top">

PI\_Read\_Only

</td>
<td valign="top">

Enables you to connect to a tenant and to monitor messages.

This authorization group enables you to access \(read-only\) artifacts in the Monitoring area, as well as to download integration flow artifacts and WSDL.

This includes tasks like:

-   Discover and copy pre-shipped standard packages

-   Monitor integration flows and the status of integration artifacts

-   Read the message payload and attachments

-   View packages and their artifacts in *Design* workspace

-   View data store entries, access policies, B2B partner profiles and agreements, and design time artifact locks




</td>
</tr>
<tr>
<td valign="top">

Business expert

</td>
<td valign="top">

AuthGroup.BusinessExpert

</td>
<td valign="top">

PI\_Business\_Expert

</td>
<td valign="top">

Enables a business expert to perform business tasks like, for example, examining the payload.

This includes tasks like:

-   Discover and copy pre-shipped standard packages

-   Monitor integration flows and the status of integration artifacts

-   Read the message payload and attachments

-   View packages and their artifacts in *Design* workspace

-   View data store entries, access policies, and design time artifact locks

-   Inspect usage of integration resources

-   Edit B2B partner profiles and contact persons, trace configuration, log levels, and archiving configuration




</td>
</tr>
<tr>
<td valign="top">

Integration developer

</td>
<td valign="top">

AuthGroup.IntegrationDeveloper

</td>
<td valign="top">

PI\_Integration\_Developer

</td>
<td valign="top">

Enables an integration developer to discover, design, and deploy integration artifacts.

This includes tasks like:

-   Execute the tasks of *PI\_Read\_Only* and *PI\_Business\_Expert* role collections.

-   Create, edit, import, export, delete package with its artifacts.

-   Deploy/undeploy integration artifacts




</td>
</tr>
<tr>
<td valign="top">

Tenant administrator

</td>
<td valign="top">

AuthGroup.Administrator

</td>
<td valign="top">

PI\_Administrator

</td>
<td valign="top">

Enables the administrator of the tenant cluster \(also referred to as the *tenant administrator*\) to connect to a cluster and to perform administrative tasks on the cluster.

This includes tasks like:

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

AuthGroup.TenantPartnerDirectoryConfigurator

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


[Tasks and Permissions](tasks-and-permissions-556d557.md "")

