<!-- loio911ca5a620e94ab581fa159d76b3b108 -->

# Assign User Roles in API Management

Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.

As an administrator of SAP API Management in the Cloud Foundry environment, you can manitain API Portal and API business hub enterprise roles and role collections, which can be used in user management. Typically, a role collection consists of one or multiple roles. You assign roles to role collections, which are in turn assigned to users. Using the SAP BTP cockpit, you can display information about the role collections that have been maintained as well as the roles available in a role collection. Fore more information, see [Roles and Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/14a877c6e2f14832999df500ffa6e05e.html).

The following predefined roles are shipped with API Portal. These roles by default, are shared, visible, and accessible within all the accounts that have subscribed to API Portal:

**API Portal Roles**


<table>
<tr>
<th valign="top">

Role Collection



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`APIPortal.Administrator`



</td>
<td valign="top">

Use this role to access the API portal user interface \(UI\) and services, manage the API proxies by adding additional policies. You can also use this role to manage APIs using the API Designer.



</td>
</tr>
<tr>
<td valign="top">

`APIPortal.Service.CatalogIntegratio`n



</td>
<td valign="top">

Use this role to establish a connection from the API business hub enterprise to the API portal.



</td>
</tr>
<tr>
<td valign="top">

`APIManagement.Selfservice.Administrator`



</td>
<td valign="top">

Use this role during the onboarding of API Portal and to get access to its settings page.



</td>
</tr>
<tr>
<td valign="top">

`APIPortal.Guest`



</td>
<td valign="top">

Use this role to access the API portal in read-only mode. You can view all APIs, policies, API providers, and analytics, but can’t edit them.



</td>
</tr>
</table>

The following predefined roles are shipped with API business hub enterprise:

**API business hub enterprise Roles**


<table>
<tr>
<th valign="top">

Role Collection



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`AuthGroup.SelfService.Admin`



</td>
<td valign="top">

Use this role during the onboarding of API business hub enterprise and to get access to it.



</td>
</tr>
<tr>
<td valign="top">

`AuthGroup.API.Admin` 



</td>
<td valign="top">

Use this role to:

-   Manage an application developer’s access to the portal by either accepting or rejecting an application developer’s request. In addition, you can revoke the access of an existing application developer.
-   Manage roles for a user by adding new roles or removing existing roles.

-   On-behalf of an application developer, admin can also perform the following tasks:
    -   Create, update, and delete applications.
    -   Create custom attributes for applications.
    -   Provide app key and secret, while creating or updating an application.




</td>
</tr>
<tr>
<td valign="top">

`AuthGroup.ContentAuthor`



</td>
<td valign="top">

Use this role to:

-   Publish content to the API business hub enterprise.
-   Establish a connection from the API portal to the API business hub enterprise.



</td>
</tr>
<tr>
<td valign="top">

`AuthGroup.API.ApplicationDeveloper`



</td>
<td valign="top">

Use this role to:

-   Access the API business hub enterprise.
-   Create, update, and delete applications.
-   View analytics information on application usage, performance, and error count.
-   View and download bills for subscribed applications.

> ### Note:  
> The `AuthGroup.API.ApplicationDeveloper` role must not be assigned manually to a user form the SAP BTP Cockpit and this role must not be a part of any user group assignment.
> 
> This role is assigned by default to a user who onboards to the API business hub enterprise using the Self-registration process or via Add User flow.
> 
> A user must be onboarded to API business hub enterprise only via Self-registration or Add User flow. For more information on registering in API business hub enterprise, see [Register on API business hub enterprise](../APIM-Development/register-on-api-business-hub-enterprise-c85fafe.md). In the Add User flow, the API business hub enterprise admin adds a user who wants to be onboarded to API business hub enterprise. However, the user who is requesting to be onboarded must ensure that the user details provided to the admin matches the user details obtained from the response of <developer portal url\>/api/1.0/users.



</td>
</tr>
<tr>
<td valign="top">

`AuthGroup.Content.Admin` 



</td>
<td valign="top">

Use this role to:

-   Create and update categories.



</td>
</tr>
<tr>
<td valign="top">

`AuthGroup.Site.Admin` 



</td>
<td valign="top">

Use this role to:

-   Configure updates.
-   Perform portal changes like uploading logo, changing the name and description, and changing the footer links.



</td>
</tr>
</table>

For more information, see [Assign Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/9e1bf57130ef466e8017eab298b40e5e.html) and [Assigning Role Collections to Users](assigning-role-collections-to-users-80bb02e.md)

