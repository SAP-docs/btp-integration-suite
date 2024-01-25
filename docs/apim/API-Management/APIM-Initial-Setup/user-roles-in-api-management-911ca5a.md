<!-- loio911ca5a620e94ab581fa159d76b3b108 -->

# User Roles in API Management

Similar to other capabilities of the SAP Integration Suite, the API Management capability defines a set of technical roles that grant specific permissions to users. Users can be assigned roles through SAP BTP's role collection concept. While users have the option to create their own role collections, a set of predefined role collections is automatically created when the API Management capability is provisioned.

Please refer to the table below for a list of tasks and the corresponding role collections.


<table>
<tr>
<th valign="top">

Persona

</th>
<th valign="top">

Tasks

</th>
<th valign="top">

Predefined Role Collections

</th>
<th valign="top">

Reference

</th>
</tr>
<tr>
<td valign="top">

Global Account Administrator

</td>
<td valign="top">

Create subaccounts in your global account.

Create service instance for API Management and Integration Suite.

Configure role collections and provide user access to role collections

</td>
<td valign="top">

Subaccount Administrator

</td>
<td valign="top">

[Create a Subaccount](https://help.sap.com/docs/btp/sap-business-technology-platform/create-subaccount?q=entitlements) 

</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Integration Suite Administrator

</td>
<td valign="top">

Subscribe to Integration Suite.

</td>
<td valign="top">

Integration\_Provisioner

</td>
<td valign="top">

[Subscribing and Configuring Initial Access to Integration Suite](https://help.sap.com/docs/integration-suite/sap-integration-suite/subscribing-to-integration-suite?q=centralised) 

</td>
</tr>
<tr>
<td valign="top">

Activate the API Management capabilities, the API business hub enterprise, and Graph.

</td>
<td valign="top">

Integration\_Provisioner

</td>
<td valign="top">

[Enabling API Management Capability from Integration Suite](https://help.sap.com/docs/integration-suite/sap-integration-suite/enabling-api-management-capability-from-integration-suite?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Deactivate the API Management capabilities, the API business hub enterprise, and Graph.

</td>
<td valign="top">

Integration\_Provisioner

</td>
<td valign="top">

[Deactivate the API Management Capability](https://help.sap.com/docs/integration-suite/sap-integration-suite/cancel-api-management-service-subscription?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Use the Graph Navigator in API business hub enterprise to inspect business data graphs.

</td>
<td valign="top">

GraphNavigator.Viewer

</td>
<td valign="top">

[Configuring User Access](https://help.sap.com/docs/integration-suite/sap-integration-suite/cohttps://help.sap.com/docs/integration-suite/sap-integration-suite/configuring-user-access?version=CLOUDnfiguring-user-access?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Create business data graphs

Activate business data graphs

</td>
<td valign="top">

Graph.KeyUser

</td>
<td valign="top">

[Configuring User Access](https://help.sap.com/docs/integration-suite/sap-integration-suite/cohttps://help.sap.com/docs/integration-suite/sap-integration-suite/configuring-user-access?version=CLOUDnfiguring-user-access?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

API Management Administrator

</td>
<td valign="top">

-   Access all API Management features.

-   Configure user permissions.

-   Access the Settings page to configure up the API Management.




</td>
<td valign="top">

APIManagement.Selfservice.Administrator

</td>
<td valign="top">

[Setting Up API Management Capability](https://help.sap.com/docs/integration-suite/sap-integration-suite/setting-up-api-management-service?q=centralised) 

</td>
</tr>
<tr>
<td valign="top">

Access API business hub enterprise.

</td>
<td valign="top">

AuthGroup.SelfService.Admin

</td>
<td valign="top">

[Enabling API Management Capability from Integration Suite](https://help.sap.com/docs/integration-suite/sap-integration-suite/enabling-api-management-capability-from-integration-suite?version=CLOUD)

[Setting Up API Management Capability](https://help.sap.com/docs/integration-suite/sap-integration-suite/setting-up-api-management-service?q=centralised)

</td>
</tr>
<tr>
<td valign="top">

Configure one or more virtual hosts.

</td>
<td valign="top">

-   APIManagement.Selfservice.Administrator

-   APIPortal.Administrator




</td>
<td valign="top">

[Requesting an Additional Virtual Host in Cloud Foundry Environment](https://help.sap.com/docs/integration-suite/sap-integration-suite/requesting-additional-virtual-host-in-cloud-foundry-environment?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

API Management Administrator and API business hub enterprise Administrator

</td>
<td valign="top">

Establish and test the connection between API business hub enterprise and Integration Suite API Management tenant.

</td>
<td valign="top">

-   APIPortal.Administrator

-   AuthGroup.API.Admin




</td>
<td valign="top">

[Setting Up API Management Capability](https://help.sap.com/docs/integration-suite/sap-integration-suite/setting-up-api-management-service?q=centralised) 

</td>
</tr>
<tr>
<td valign="top">

API Management Administrator and API business hub enterprise Administrator

</td>
<td valign="top">

Establish and test the connection between centralised API business hub enterprise and multiple Integration Suite API Management tenants.

</td>
<td valign="top">

-   APIPortal.Administrator

-   AuthGroup.API.Admin

-   AuthGroup.APIPortalRegistration

-   APIPortal Service.CatalogIntegration




</td>
<td valign="top">

[Create a Connection Request for the Centralized API business hub enterprise](https://help.sap.com/docs/integration-suite/sap-integration-suite/create-connection-request-for-centralized-api-business-hub-enterprise-new-design?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Guest User/API Auditor

</td>
<td valign="top">

Access the API Management capability in read-only mode. You can view all API proxies, policies, existing products, API providers, and analytics, but can’t edit them.

</td>
<td valign="top">

APIPortal.Guest

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

API Developer/Administrator

</td>
<td valign="top">

-   Discover APIs

-   Convert externally managed APIs to internally managed APIs

-   Create an API provider

-   Create API proxies

-   Configure virtual host

-   Import API specification

-   Create certificates

-   Create Key Value Maps

-   Associate policies to an API proxy

-   Deploy API proxies

-   Test API proxies using the API Test Console




</td>
<td valign="top">

APIPortal.Administrator

</td>
<td valign="top">

[Build API Proxies](https://help.sap.com/docs/integration-suite/sap-integration-suite/build-apis?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

API Developer/Administrator

</td>
<td valign="top">

-   Create products, group API proxies into products

-   Create a custom role for a product

-   Publish products to API business hub enterprise




</td>
<td valign="top">

APIPortal.Administrator

</td>
<td valign="top">

[Publish API Proxies](https://help.sap.com/docs/integration-suite/sap-integration-suite/publish-apis?version=CLOUD)

[Creating a Custom Role](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-custom-role?version=CLOUD&q=custom%20role)

</td>
</tr>
<tr>
<td valign="top">

API Developer/Administrator

</td>
<td valign="top">

Generate revenue for using the API proxies.

</td>
<td valign="top">

APIPortal.Administrator

</td>
<td valign="top">

[Monetize API Proxies](https://help.sap.com/docs/integration-suite/sap-integration-suite/monetize-apis?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

API Developer/Administrator

</td>
<td valign="top">

Analyze the API proxy usage and performance.

</td>
<td valign="top">

APIPortal.Administrator

</td>
<td valign="top">

[Analyze API Proxies](https://help.sap.com/docs/integration-suite/sap-integration-suite/analyze-apis?version=CLOUD&q=custom%20role) 

</td>
</tr>
<tr>
<td valign="top">

API Developer/Administrator

</td>
<td valign="top">

Design an API artifact

Add policy and integration steps to the API artifact.

</td>
<td valign="top">

-   APIPortal.Administrator

-   PI\_Integration\_Developer




</td>
<td valign="top">

[Add an API Artifact](https://help.sap.com/docs/integration-suite/sap-integration-suite/add-api-artifact?version=CLOUD)

[Adding Policy Steps to the API Artifact](https://help.sap.com/docs/integration-suite/sap-integration-suite/adding-policy-steps-to-api-artifact?version=CLOUD)

</td>
</tr>
<tr>
<td valign="top">

API business hub enterprise Administrator

</td>
<td valign="top">

Approve or reject the connection request between API business hub enterprise and Integration Suite API Management tenant.

</td>
<td valign="top">

AuthGroup.API.Admin

</td>
<td valign="top">

[Approve the Pending Connection Requests](https://help.sap.com/docs/integration-suite/sap-integration-suite/approve-pending-connection-requests-new-design?version=CLOUD&q=test%20connect%20APi%20business%20hub%20enterprise) 

</td>
</tr>
<tr>
<td valign="top">

API business hub enterprise Administrator

</td>
<td valign="top">

-   Access all API business hub enterprise features

-   Approve the registration request of an application developer

-   Revoke the rights of an application developer

-   Manage users and their API business hub enterprise roles

-   Manage notifications in API business hub enterprise

-   Adjust the visibility of the Graph navigator on API business hub enterprise

-   Revoke the credentials \(app key and secret\) of an application




</td>
<td valign="top">

AuthGroup.API.Admin

</td>
<td valign="top">

[Consume API Proxies](https://help.sap.com/docs/integration-suite/sap-integration-suite/consume-apis?version=CLOUD&q=test%20connect%20APi%20business%20hub%20enterprise) 

</td>
</tr>
<tr>
<td valign="top">

API business hub enterprise Administrator

</td>
<td valign="top">

Customize the visual layout of the API business hub enterprise using the Site Editor

</td>
<td valign="top">

-   AuthGroup.API.Admin

-   AuthGroup.API.Admin




</td>
<td valign="top">

[Customize the Visual Format of the API business hub enterprise](https://help.sap.com/docs/integration-suite/sap-integration-suite/customize-visual-format-of-api-business-hub-enterprise?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

API business hub enterprise Administrator

</td>
<td valign="top">

Create domain categories and add the related products into relevant categories.

</td>
<td valign="top">

-   AuthGroup.API.Admin
-   AuthGroup.Content.Admin



</td>
<td valign="top">

[Manage Domain Categories](https://help.sap.com/docs/integration-suite/sap-integration-suite/manage-domain-categories-new-design?version=CLOUD) 

</td>
</tr>
<tr>
<td valign="top">

Application Developer

</td>
<td valign="top">

-   Access the API business hub enterprise.

-   Create, update, and delete applications.

-   View analytics information on application usage, performance, and error count.

-   View and download bills for subscribed applications.




</td>
<td valign="top">

AuthGroup.API.ApplicationDeveloper

</td>
<td valign="top">

[View Applications, Costs, and Analyze Reports](https://help.sap.com/docs/integration-suite/sap-integration-suite/view-applications-costs-and-analyze-reports-new-design?version=CLOUD)

[Create an Application](https://help.sap.com/docs/integration-suite/sap-integration-suite/create-application-new-design?version=CLOUD)

</td>
</tr>
</table>

For more information, see [Assign Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/9e1bf57130ef466e8017eab298b40e5e.html) and [Assigning Role Collections to Users](assigning-role-collections-to-users-80bb02e.md)



<a name="loio911ca5a620e94ab581fa159d76b3b108__section_twl_fqz_c1c"/>

## Technical Roles for Constructing Custom Role Collections

If you want to create your own set of role collections, you can utilize the following technical roles from the provided list:


<table>
<tr>
<th valign="top">

Technical roles

</th>
<th valign="top">

Included in predefined role collection

</th>
</tr>
<tr>
<td valign="top">

-   Cloud Connector Administrator

-   Destination Administrator

-   Subaccount Admin

-   Subaccount Service Administrator

-   User

-   Role Administrator




</td>
<td valign="top">

Subaccount Administrator

</td>
</tr>
<tr>
<td valign="top">

IntegrationProvisioningAdmin

</td>
<td valign="top">

Integration\_Provisioner

</td>
</tr>
<tr>
<td valign="top">

APIPortalAdmin

</td>
<td valign="top">

APIPortal.Administrator

</td>
</tr>
<tr>
<td valign="top">

CatalogIntegration

</td>
<td valign="top">

APIPortal.Service.CatalogIntegration

</td>
</tr>
<tr>
<td valign="top">

Guest

</td>
<td valign="top">

APIPortal.Guest

</td>
</tr>
<tr>
<td valign="top">

onboardingtemplate

</td>
<td valign="top">

APIManagement.SelfService.Administrator

</td>
</tr>
<tr>
<td valign="top">

Graph\_Key\_User

</td>
<td valign="top">

Graph.KeyUser

</td>
</tr>
<tr>
<td valign="top">

APIAdmin

</td>
<td valign="top">

AuthGroup.API.Admin

</td>
</tr>
<tr>
<td valign="top">

APIPortalConnectionRequest

</td>
<td valign="top">

AuthGroup.APIPortalRegistration

</td>
</tr>
<tr>
<td valign="top">

ApplicationDeveloper

</td>
<td valign="top">

AuthGroup.API.ApplicationDeveloper

</td>
</tr>
<tr>
<td valign="top">

ContentAdmin

</td>
<td valign="top">

AuthGroup.Content.Admin

</td>
</tr>
<tr>
<td valign="top">

ContentAuthor

</td>
<td valign="top">

AuthGroup.ContentAuthor

</td>
</tr>
<tr>
<td valign="top">

SelfServiceAdmin

</td>
<td valign="top">

AuthGroup.SelfService.Admin

</td>
</tr>
<tr>
<td valign="top">

SiteAdmin

</td>
<td valign="top">

AuthGroup.Site.Admin

</td>
</tr>
<tr>
<td valign="top">

Graph\_Navigator\_Viewer

</td>
<td valign="top">

GraphNavigator.Viewer

</td>
</tr>
</table>

