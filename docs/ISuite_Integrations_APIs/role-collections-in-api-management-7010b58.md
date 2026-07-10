<!-- loio7010b58f57494a71a6a02c475a3548e8 -->

# Role Collections in API Management

Use role collections to group together different roles that can be assigned to API management users. In API Management, a role collection is a grouping mechanism that allows you to manage and assign multiple roles to users more efficiently.

The table below outlines the role collections used in SAP Integration Suite API Management tenant:


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

APIManagement.Selfservice.Administrator

</td>
<td valign="top">

This role is used during the on-boarding process of the SAP Integration Suite API Management tenant, granting access to the portal's settings page.

</td>
</tr>
<tr>
<td valign="top">

APIPortal.Administrator

</td>
<td valign="top">

This role provides access to the API portal user interface \(UI\) and services. It allows you to manage API proxies by adding additional policies, create products, and manage APIs through the API Designer.

</td>
</tr>
<tr>
<td valign="top">

APIPortal.Configurator

</td>
<td valign="top">

This role allows you to view and edit entities such as API providers, certificates, and rate plans.

</td>
</tr>
<tr>
<td valign="top">

APIPortal.Developer

</td>
<td valign="top">

This role allows you to view and edit entities such as API proxies, policy templates and products with read-only access to all other entities.

</td>
</tr>
<tr>
<td valign="top">

APIPortal.Tester

</td>
<td valign="top">

This role allows you to test and debug API proxies.

</td>
</tr>
<tr>
<td valign="top">

APIPortal.Guest

</td>
<td valign="top">

Use this role to access the API portal in read-only mode. You can view all APIs, policies, API providers, and analytics, but can’t edit them.

</td>
</tr>
</table>

> ### Note:  
> The **APIPortal.Service.CatalogIntegration** and **AuthGroup.ContentAuthor** role collections are intended solely for internal communication between API Portal \(both the standalone service and API Management within SAP Integration Suite\) and Developer Hub. These internal role collections must not be added to any custom role collection or assigned to users.

The role collections **APIPortalAdministrator, APIPortal.Configurator, APIPortal.Developer, and APIPortal.Tester** enable enhanced governance and a clearer separation of responsibilities within API Management. By assigning roles based on specific job functions, you can improve both security and operational efficiency. For a detailed breakdown of the permissions and responsibilities associated with each role, see [Comprehensive Breakdown of Role Collections in API Management](comprehensive-breakdown-of-role-collections-in-api-management-f3049e2.md).



The table below outlines the role collections used in Developer Hub:

****


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

AuthGroup.SelfService.Admin

</td>
<td valign="top">

Use this role during the onboarding of Developer Hub and to get access to it.

To onboard the Developer Hub web page, the AuthGroup.SelfService.Admin role must me assigned to you. This is an one time activity.

> ### Note:  
> Please be aware that the *Authgroup.API.Admin* role is required for onboarding into Developer Hub. This role will be automatically assigned to your scope once you have been assigned the *AuthGroup.SelfService.Admin* role. After the onboarding process is completed, it is necessary for an *Authgroup.API.Admin* to assign the AuthGroup.Content.Admin role to a user in order to access and discover the APIs from different business systems in Developer Hub.

For Developer Hub to appear in the product switcher on Integration Suite, assign the *AuthGroup.SelfService.Admin* role to yourself.

</td>
</tr>
<tr>
<td valign="top">

AuthGroup.API.Admin

</td>
<td valign="top">

Use this role to:

-   Manage an application developer’s access to Developer Hub by either accepting or rejecting an application developer’s request. In addition, you can revoke the access of an existing application developer.
-   Manage roles for a user by adding new roles or removing existing roles.

-   On-behalf of an application developer, admin can also perform the following tasks:
    -   Create, update, and delete applications.
    -   Create custom attributes for applications.
    -   Provide app key and secret, while creating or updating an application.




</td>
</tr>
<tr>
<td valign="top">

AuthGroup.API.ApplicationDeveloper

</td>
<td valign="top">

Use this role to:

-   Access Developer Hub.
-   Create, update, and delete applications.
-   View analytics information on application usage, performance, and error count.
-   View and download bills for subscribed applications.



</td>
</tr>
<tr>
<td valign="top">

AuthGroup.Content.Admin

</td>
<td valign="top">

Use this role to:

-   Create and update categories.



</td>
</tr>
<tr>
<td valign="top">

AuthGroup.Site.Admin

</td>
<td valign="top">

Use this role to:

-   Configure updates.
-   Perform portal changes like uploading logo, changing the name and description, and changing the footer links.



</td>
</tr>
<tr>
<td valign="top">

AuthGroup.APIPortalRegistration

</td>
<td valign="top">

This role is required to create a connection request between multiple API portals and a centralized Developer Hub. It is also used to update the credentials associated with the connection request.

</td>
</tr>
</table>

