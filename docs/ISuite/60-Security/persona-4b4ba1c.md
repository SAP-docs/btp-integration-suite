<!-- copy4b4ba1c553474259b5be661f4ef0702c -->

# Persona

When you perform user management tasks using SAP BTP cockpit, you find a set of predefined roles that you can assign to users of the account. According to the main tasks associated with integration projects, these roles are associated to certain persona relevant for an integration project.

Personas cover the different tasks associated with an integration project. To assign roles that are application-based, see [Configuring User Access to the Application](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/ed6033b2eabe4a64a20cce1e6076bacf.html).

> ### Note:  
> This topic contains also information that is related to SAP BTP, Neo environment. Note that SAP Integration Suite is available only in the SAP BTP, Cloud Foundry environment, not in the Neo environment. However, many customers know SAP Cloud Integration as standalone service. The additional information should help those customers to relate the Neo-related information they know to the information relevant in the context of SAP Integration Suite.

> ### Note:  
> In the different environments, the personas are mapped to different objects.
> 
> -   In the Neo environment, a persona is realized by an authorization group \(beginning with the string *AuthGroup*\).
> 
> -   In the Cloud Foundry environment, a persona is realized by role collection.

<a name="copy4b4ba1c553474259b5be661f4ef0702c__table_wnh_gpy_4k"/>Authorization Groups


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

-   Monitoring integration flows and the status of integration artifacts

-   Reading the message payload and attachments




</td>
</tr>
<tr>
<td valign="top">

Administrator



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

-   Monitoring integration flows and the status of integration artifacts

-   Deploying security content

-   Deploying integration content \(such like integration flows, for example\)

-   Deleting messages from transient data store




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

Enables an integration developer to connect to a cluster using Integration Designer and to display, download, and deploy artifacts \(for example, integration flows\).

This authorization group is required to access Cloud Integration.

This includes tasks like:

-   Monitoring integration flows and the status of integration artifacts

-   Deploying integration content \(such like integration flows, for example\)




</td>
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

This authorization group enables you to access \(read-only\) artifacts in the Monotoring area, as well as to download integration flow artifacts and WSDL.



</td>
</tr>
<tr>
<td valign="top">

System developer



</td>
<td valign="top">

AuthGroup.SystemDeveloper



</td>
<td valign="top">

n.a.



</td>
<td valign="top">

Enables a system developer to perform tasks required for system support.

This includes tasks like:

-   Monitoring integration flows and the status of integration artifacts

-   Restarting subsystems of the tenant cluster

-   Software development tasks on VMs of the tenant cluster


This authorization group enables you to access \(read-only\) the Data Store viewer.

> ### Note:  
> System developer tasks are typically required in the support case by SAP experts who are supposed to perform tasks like debugging \(for example\) on the tenant cluster.



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



<a name="copy4b4ba1c553474259b5be661f4ef0702c__section_fdd_gm5_p4b"/>

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
> <a name="copy4b4ba1c553474259b5be661f4ef0702c__d503e279"/>
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Option
> 
> 
> 
> </th>
> <th valign="top">
> 
> Summary of Steps
> 
> 
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> Basic authentication of a user registered at an identity provider \(IdP\)
> 
> 
> 
> </td>
> <td valign="top">
> 
> Use SAP BTP cockpit to define a role collection that contains the predefined role template `MessagingSend` and assign the role collection to the IdP user \(under *Security* \> *Trust Configuration*\). The role template `MessagingSend` is provided by default in your subaccount to define permissions for sender systems to call integration flow endpoints for this use case.
> 
> See: [Basic Authentication of IdP User for Integration Flow Processing](../40-RemoteSystems/basic-authentication-of-idp-user-for-integration-flow-processing-5d46e56.md)
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Authentication with an OAuth client \(service instance\)
> 
> 
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
> 
> [Basic Authentication with clientId and clientsecret for Integration Flow Processing](../40-RemoteSystems/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)
> 
> [Client Certificate Authentication for Integration Flow Processing](../40-RemoteSystems/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)
> 
> [OAuth with Client Credentials Grant for Integration Flow Processing](../40-RemoteSystems/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)
> 
> 
> 
> </td>
> </tr>
> </table>

**Related Information**  


[Tasks and Permissions](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/IAT/en-US/556d5575d4b0483e85d4f3251f21d0ec.html "") :arrow_upper_right:

