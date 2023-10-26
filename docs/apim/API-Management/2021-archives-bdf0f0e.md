<!-- loiobdf0f0e12ff04183a553b2544ca4db71 -->

# 2021 Archives



**2021**


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Capability

</th>
<th valign="top">

Environment

</th>
<th valign="top">

Title

</th>
<th valign="top">

Description

</th>
<th valign="top">

Action

</th>
<th valign="top">

Type

</th>
<th valign="top">

Available as of

</th>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Monitor the Health of Custom Domain Virtual Host Certificates

</td>
<td valign="top">

You can use SAP Cloud Application Lifecycle Management \(ALM\) application for monitoring the health of API Management certificates. For more information, see [Monitor the Health of Custom Domain Virtual Host Certificates Using SAP Cloud ALM](monitor-the-health-of-custom-domain-virtual-host-certificates-using-sap-cloud-alm-7bd9d9f.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-12-12

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Update to the Client SDK

</td>
<td valign="top">

You can now apply policy template to an existing API proxy. For more information, refer to the Client SDK version 1.4.0 in [API Services](api-services-007d50f.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-09-29

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Applications table on My Workspace

</td>
<td valign="top">

The *My Workspace* section in API Business Hub Enterprise has been revamped to provide better performance. The Cost Incurred column has been removed from the Applications table. You can view the cost incurred details in the *Cost* section. For more information,see [Create an Application \[Classic Design\]](APIM-Development/create-an-application-classic-design-7b4e71b.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-09-29

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

SAP Analytics Cloud for API Management

</td>
<td valign="top">

You can use the API Management Reporting Dashboard on SAP Analytics Cloud to monitor API usage and performance through various API metrics and KPIs. For more information see,[SAP Analytics Cloud for API Management](APIM-Development/sap-analytics-cloud-for-api-management-fb3648a.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-08-31

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Overriding the default update operation for API Proxy of Type ODATA

</td>
<td valign="top">

When discovering an API from the on-premise SAP Gateway system via OData API Provider, for the entities that are defined as "sap:updatable" in the backend service, you can choose the update operation \("PUT" and "PATCH"\) for OData V2 and OData V4 respectively. For more information, see [Overriding the Default Update Operation for API Proxy of Type OData](APIM-Development/overriding-the-default-update-operation-for-api-proxy-of-type-odata-4a12c59.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-08-31

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Product Transport

</td>
<td valign="top">

When transport is triggered for a Product, all the entities of the Product get transported along with the Product. For more information, see [Transporting a Product from Source to Destination](APIM-Development/transporting-a-product-from-source-to-destination-3a4cdd2.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-08-09

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API Designer

</td>
<td valign="top">

For a given Resource, you can use the API Designer to detect and correct the errors in swagger definition, and save the changes. For more information, see the note in step 14 in [Create an API](APIM-Development/create-an-api-c0842d5.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-08-09

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Save and Deploy API Proxy

</td>
<td valign="top">

Saving is a design time activity; at this stage, multiple aspects of the proxy might change. Until all the changes made to the proxy are considered and are finally saved, the proxy should not be deployed.

Action: Previously, editing and then saving the changes in an already deployed API, would deploy the changes in runtime. Now, after saving the changes you've made to the API proxy, you have to choose *Deploy* for the latest changes to reflect in runtime. For more information, see [Edit an API Proxy](APIM-Development/edit-an-api-proxy-a64b952.md).

Notes:

-   API proxies always get imported to the destination API portal in the deployed state. For more information, see [Transporting an API Proxy from Source to Destination](APIM-Development/transporting-an-api-proxy-from-source-to-destination-2fe1aa2.md). Additionally, APIs attached to the Product get imported to the destination API portal in the deployed state. For more information, see [Transporting a Product from Source to Destination](APIM-Development/transporting-a-product-from-source-to-destination-3a4cdd2.md).

-   When an API proxy is transported or exported individually or as a part of a Product, by default, it gets imported to the target in the deployed state. For more information, see [Import an API](APIM-Development/import-an-api-9342a93.md).

-   If you try to publish a Product that has an API with saved changes attached to it, you get a warning message that there are changes in the APIs that aren't deployed yet. Similarly, you'll receive a warning message if you try to publish a Product which has multiple APIs attached to it, and few of these APIs have changes that are saved but not deployed. For more information, refer the note in step 9 in [Create a Product](APIM-Development/create-a-product-d769622.md).




</td>
<td valign="top">

Required

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-08-09

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Auditing and Logging Information

</td>
<td valign="top">

Here you can find a list of the security events that are logged by TECHNICAL COMPONENT. For more information, see [Auditing and Logging Information for API Management](auditing-and-logging-information-for-api-management-77024b3.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-08-09

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   


</td>
<td valign="top">

API Business Hub Enterprise

</td>
<td valign="top">

Ypu can now update the credentials used to establish a connection between the API portal and the API Business Hub Enterprise for a submitted request and an approved request.

Action: To update the credentials, see [Updating the Connection Request Credentials for a Submitted Request \[Classic Design\]](APIM-Initial-Setup/updating-the-connection-request-credentials-for-a-submitted-request-classic-des-eb84854.md) and [Updating the Connection Request Credentials for an Approved Request \[Classic Design\]](APIM-Initial-Setup/updating-the-connection-request-credentials-for-an-approved-request-classic-des-b583b7a.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-07-09

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Migrating API Management Subscription Created Using the Starter Plan Service Instance

</td>
<td valign="top">

You can now to migrate the design-time components that you have in the Neo environment, which was previously set up using Starter Plan instance, to the Cloud Foundry environment, keeping the runtime components as is.

Action: To migrate the design-time components from Neo to Cloud Foundry, see [Migrating API Management Subscription Created Using the Starter Plan Service Instance](APIM-Migration/migrating-api-management-subscription-created-using-the-starter-plan-service-instan-9778a36.md) 

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-07-06

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Custom Domain Configuration for API Portal or API Business Hub Enterprise Subscription

</td>
<td valign="top">

To complete the process of configuring a custom domain for the API Portal or the API Business Hub Enterprise application using the Custom Domain Service in the SAP BTP Cloud Foundry environment, you need to contact the SAP API Management operations team. For more information, see [Custom Domain Configuration for API Portal or API business hub enterprise Subscription](APIM-Initial-Setup/custom-domain-configuration-for-api-portal-or-api-business-hub-enterprise-subsc-c4e67a9.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-06-25

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Update to the Client SDK

</td>
<td valign="top">

You can now export policy templates from the API portal.

Action: For more information on how to export the policy templates, refer to the Client SDK version 1.3.0 in [API Services](api-services-007d50f.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-06-14

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Generate client ID and secret from API Portal UI

</td>
<td valign="top">

You can now generate the credentials from the API Portal to establish the connection with centralized API Business Hub Enterprise.

Action: See the Next Steps section in [Set Up API Portal Application](APIM-Initial-Setup/set-up-api-portal-application-29c281b.md). See the Prerequisites section and the Note in the Results section in [Create a Connection Request for the Centralized API business hub enterprise \[Classic Design\]](APIM-Initial-Setup/create-a-connection-request-for-the-centralized-api-business-hub-enterprise-cla-02f7877.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-06-14

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Configuring Load Balancing for API Proxy from API Portal.

</td>
<td valign="top">

You can now configure the load balancer to distribute the load efficiently across multiple API providers. For more information, see [Configuring Load Balancing](APIM-Development/configuring-load-balancing-503a3aa.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-06-14

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Region specific NAT IP addresses

</td>
<td valign="top">

To get region specific NAT IP addresses \(egress, IPs for request from API Management\), raise a support ticket. For more information, see [Region-Specific IP Addresses Available for API Management Cloud Foundry Environment](APIM-Initial-Setup/region-specific-ip-addresses-available-for-api-management-cloud-foundry-environ-585d639.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

Changed

</td>
<td valign="top">

2021-06-14

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Converting Externally Managed APIs to Internally Managed APIs

</td>
<td valign="top">

You can convert an external API, whose lifecycle isn’t be managed by SAP API Management to an internal API so that management capabilities can be enabled for that API.

Action:To convert an external API to an internal API, see [Converting Externally Managed APIs to Internally Managed APIs](APIM-Development/converting-externally-managed-apis-to-internally-managed-apis-1fc41ac.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-05-13

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

Updating the Connection Request Credentials

</td>
<td valign="top">

There can be instances where you have to update the credentials that you've used to establish a connection between the API portal and the API Business Hub Enterprise. For more information, see [Updating the Connection Request Credentials for a Submitted Request \[Classic Design\]](APIM-Initial-Setup/updating-the-connection-request-credentials-for-a-submitted-request-classic-des-eb84854.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-04-12

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

Perform Additional Tasks in API Designer

</td>
<td valign="top">

To download the API swagger specifications, choose Download and select JSON or YAML format. For more information, see [Perform Additional Tasks in API Designer](APIM-Development/perform-additional-tasks-in-api-designer-a92cf80.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-04-12

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

Transporting API Providers, Certificates, and Key Value Maps

</td>
<td valign="top">

You can now trigger the transport of API Provider, Key Store Certificate, Trust Store, and Key Value Maps individually.

Action: To trigger the transport of API Provider, Key Store Certificate, Trust Store, and Key Value Maps individually, see[Triggering Content Transport Using SAP Cloud Transport Management Service](APIM-Development/triggering-content-transport-using-sap-cloud-transport-management-service-cc36fab.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-04-12

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

Update to the Client SDK

</td>
<td valign="top">

Two new commands to create API Proxies either by providing parameter information or by uploading JSON files have been added. For more information, see [API Services](api-services-007d50f.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-03-16

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

Content Transport Using Cloud Transport Management Service

</td>
<td valign="top">

You can now use the SAP Cloud Transport Management service for exporting, importing, and shipping the API Management content from the Development or Test environment to Production environment.

Action: To transport API Management content from the Development or Test environment to Production environment, see [Transport APIs and Its Related Artifacts](APIM-Development/transport-apis-and-its-related-artifacts-eb83118.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-03-16

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

Configuring HealthMonitor and Load Balancer for API Proxy using .Zip

</td>
<td valign="top">

Configure health monitor and the load balancer to put the active target server in rotation and to distribute the load efficiently across multiple servers. For more information, see [Load Balancing Across API Providers](APIM-Development/load-balancing-across-api-providers-7ac0c09.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-03-16

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

UI changes in the SAP BTP Cockpit

</td>
<td valign="top">

A new path has been added on the UI to subscribe to the application plan for API portal and API Business Hub Enterprise. For more information, refer to the step 3 in the following topics: [Set Up API Portal Application](APIM-Initial-Setup/set-up-api-portal-application-29c281b.md) [Set Up API business hub enterprise Application Using the Standalone Tile](APIM-Initial-Setup/set-up-api-business-hub-enterprise-application-using-the-standalone-tile-80c0519.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

Changed

</td>
<td valign="top">

2021-02-15

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

API Business Hub Enterprise

</td>
<td valign="top">

You can now maintain a centralized API catalog in one API Business Hub Enterprise that accepts contents like API proxies, API products, and so on, from multiple API portals.

Action: You can select multiple products published from the same portal but you can't select products published from different portals. For more information, see [Centralized API business hub enterprise \[Classic Design\]](APIM-Initial-Setup/centralized-api-business-hub-enterprise-classic-design-33b706f.md) and [Create an Application \[Classic Design\]](APIM-Development/create-an-application-classic-design-7b4e71b.md).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-02-15

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

Integration Suite

</td>
<td valign="top">

Cloud Foundry

</td>
<td valign="top">

Discover REST and SOAP APIs

</td>
<td valign="top">

Discover REST and SOAP APIs along with OData APIs while creating a proxy for Integration flow. For more information, see [Creating an API from SAP Cloud Integration API Provider](APIM-Development/creating-an-api-from-sap-cloud-integration-api-provider-aefbd74.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

New

</td>
<td valign="top">

2021-01-18

</td>
</tr>
</table>

**Related Information**  


[2022 Archives](2022-archives-7eaa63d.md "")

[2020 Archives](2020-archives-085f4e9.md "")

