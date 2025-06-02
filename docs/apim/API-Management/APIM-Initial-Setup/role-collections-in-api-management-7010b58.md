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

APIPortal.Service.CatalogIntegration

</td>
<td valign="top">

The client credentials, which are necessary for establishing a connection between the SAP Integration Suite API Management tenant and Developer Hub, are generated for this role.

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

</td>
</tr>
<tr>
<td valign="top">

AuthGroup.API.Admin

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

AuthGroup.ContentAuthor

</td>
<td valign="top">

Use this role to:

-   Publish content to the Developer Hub.
-   Establish a connection from the API portal to the Developer Hub.



</td>
</tr>
<tr>
<td valign="top">

AuthGroup.API.ApplicationDeveloper

</td>
<td valign="top">

Use this role to:

-   Access the Developer Hub.
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

This role is necessary for creating a connection request between the SAP Integration Suite API Management tenant and the Developer Hub. It's also used to update the connection request credentials.

</td>
</tr>
</table>

