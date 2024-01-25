<!-- loio7010b58f57494a71a6a02c475a3548e8 -->

# User Roles in API Management

Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.

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

**Related Information**  


[API Management, API portal as a Service](api-management-api-portal-as-a-service-e064663.md "The API Management, API portal as a service on Cloud Foundry provides different capabilities through Route Service plan, On-Premise Connectivity plan, and API Access plan.")

[API Management, API business hub enterprise as a Service](api-management-api-business-hub-enterprise-as-a-service-d59d8f9.md "The API Management, API business hub enterprise as a service on Cloud Foundry provides the API access plan.")

[Region-Specific IP Addresses Available for API Management Cloud Foundry Environment](region-specific-ip-addresses-available-for-api-management-cloud-foundry-environment-585d639.md "API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.")

[Requesting an Additional Virtual Host in Cloud Foundry Environment](requesting-an-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "Create a new virtual host or update an alias for an existing virtual host in the Cloud Foundry environment.")

[Requesting a Custom Domain for a Virtual Host](requesting-a-custom-domain-for-a-virtual-host-6b9e5a3.md "A virtual host lets you host multiple domain names on API Management capability within Integration Suite.")

[Request for a Two-Way SSL Certificate](request-for-a-two-way-ssl-certificate-9faf7ce.md "Request a two-way SSL certificate for the default domain of the virtual host of your API Management service.")

[Cancel API Management Service Subscription](cancel-api-management-service-subscription-df6df2b.md "You can deactivate your API Management capability from Integration Suite to disable your account from the API Management service.")

