<!-- loio7010b58f57494a71a6a02c475a3548e8 -->

# User Roles in API Management

Use role collections to group together different roles that can be assigned to API Portal and Developer Hub users.

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

Use this role to access the API portal user interface \(UI\) and services, manage the API proxies by adding additional policies, and create products. You can also use this role to manage APIs using the API Designer.

</td>
</tr>
<tr>
<td valign="top">

`APIPortal.Service.CatalogIntegratio`n

</td>
<td valign="top">

You need this role assigned to you because the client credentials, which are necessary for establishing a connection between the Integration Suite API Management tenant and Developer Hub, are generated for this role.

</td>
</tr>
<tr>
<td valign="top">

`APIManagement.Selfservice.Administrator`

</td>
<td valign="top">

Use this role during the onboarding of API portal and to get access to its settings page.

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

**Developer Hub Roles**


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

Use this role during the onboarding of Developer Hub and to get access to it.

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

-   Publish content to the Developer Hub.
-   Establish a connection from the API portal to the Developer Hub.



</td>
</tr>
<tr>
<td valign="top">

`AuthGroup.API.ApplicationDeveloper`

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
<tr>
<td valign="top">

`AuthGroup.APIPortalRegistration`

</td>
<td valign="top">

This role is necessary for creating a connection request between the Integration Suite API Management tenant and the Developer Hub. It's also used to update the connection request credentials.

</td>
</tr>
</table>

**Related Information**  


[Configuring Additional Virtual Host in Cloud Foundry Environment](configuring-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "A virtual host allows you to host multiple domain names on the API Management capability within Integration Suite.")

[Region-Specific IP Addresses Available for API Management Cloud Foundry Environment](region-specific-ip-addresses-available-for-api-management-cloud-foundry-environment-683a97c.md "API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.")

[Cancel API Management Service Subscription](cancel-api-management-service-subscription-df6df2b.md "You can deactivate your API Management capability from Integration Suite to disable your account from the API Management service.")

[Setting Up API Management with SAP Cloud Identity Services](setting-up-api-management-with-sap-cloud-identity-services-1e88d9c.md "SAP Cloud Platform allows customers to connect their SAP Cloud Identity Services with the BTP offerings.")

