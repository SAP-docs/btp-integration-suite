<!-- loio361c04fb490248279a22fe202c0d437d -->

# What's New for API Composition?





**2025**


<table>
<tr>
<th valign="top">

Technical Component

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

Lifecycle

</th>
<th valign="top">

Type

</th>
<th valign="top">

Line of Business

</th>
<th valign="top">

Modular Business Process

</th>
<th valign="top">

Product

</th>
<th valign="top">

Latest Revision

</th>
<th valign="top">

Available as of

</th>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Setting up API Composition Navigator Tryout Connectivity

</td>
<td valign="top">

In order to send live requests to your business data graphs using the *Try Out* feature in the API Composition, you must first establish connectivity between the API Composition Navigator and API Composition.

For more information, see [Setting Up API Composition Navigator Connectivity](https://help.sap.com/docs/api-composition/isuite-api-composition/api-composition-navigator-on-developer-hub?version=CLOUD#setting-up-api-composition-navigator-tryout-connectivity).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2026-07-06

</td>
<td valign="top">

2026-07-26

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

**Mandatory Destination Property**for API Composition 

</td>
<td valign="top">

To include the destinations for API Composition to create and activate business data graphs, you must add the `IntegrationCell.Include` destination property.

For more information, see [Additional SAP BTP Destination Properties](https://help.sap.com/docs/api-composition/dev-api-composition/connect-to-your-business-systems?version=CLOUD#additional-sap-btp-destination-properties).

> ### Note:  
> The `graph.ignore` destination property will no longer be available after **24 July 2026**. Please use the `IntegrationCell.Include` destination property.



</td>
<td valign="top">

Required

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2026-07-06

</td>
<td valign="top">

2026-07-26

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

**Graph** is Now **API Composition** 

</td>
<td valign="top">

We’ve refreshed the name of the **Graph** capability of API Management in SAP Integration Suite—introducing **API Composition**.

This new name better captures the true power of the capability: users can compose multiple APIs from different systems and services into a single unified, customized, and semantically connected API.

**What stays the same?**

All existing features and functionality remain unchanged. You can continue to leverage the same robust capabilities you rely on today—only now under a name that better reflects their purpose and value.

For more information, see [What Is API Composition?](what-is-api-composition-456fc54.md)

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2026-07-06

</td>
<td valign="top">

2026-07-06

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Explore Connected Entities in API Composition Navigator on SAP Developer Hub

</td>
<td valign="top">

You can now see how entities connect to each other in the API Composition Navigator on SAP Developer Hub.

The new visualization displays associations between entities, making it easy to explore and understand their relationships.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2026-05-21

</td>
<td valign="top">

2026-05-21

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Updates to API Composition Navigator on SAP Developer Hub

</td>
<td valign="top">

The following improvements are available on the API Composition Navigator on SAP Developer Hub:

-   The landing page displays more information and you can also search for business data graphs.
-   The *Business Data Graph* overview page provides additional details. It also offers direct access to metadata files.
-   The *Try Out*section now features syntax highlighting of the request URL. The `path` and `query params` appear in different colors to help you write and read complex OData queries more easily.



</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2026-02-24

</td>
<td valign="top">

2026-02-24

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Add optional OData containment entities to your business data graph

</td>
<td valign="top">

OData containment controls how contained entities appear in a business data graph. An entity is contained when a `NavigationProperty` from another entity exists in the business data graph with the annotation `ContainsTarget=True`. Using OData containment, you choose how these contained entities are accessed in the Business Data Graph API. For more information, see [OData Containment \(Optional\)](https://help.sap.com/docs/graph/graph-wip/business-data-graph-configuration-file?state=DRAFT#odata-containment-(optional)).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2025-11-19

</td>
<td valign="top">

2025-11-19

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Try out GraphQL Queries in the API Composition Navigator on the Developer Hub

</td>
<td valign="top">

You can try out GraphQL queries in the API Composition Navigator on the Developer Hub. For more information, see [API Composition Navigator on Developer Hub](api-composition-navigator-on-developer-hub-8e75d31.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2025-08-11

</td>
<td valign="top">

2025-08-11

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

New *GraphNavigator.Tryout* role

</td>
<td valign="top">

You must be assigned to the *GraphNavigator.Tryout* role to make requests to business data graphs on the API Composition Navigator on the Developer Hub. For more information, see:

-   [Define Users for Graph](https://help.sap.com/docs/graph/graph/initial-setup?version=PROD#3.-define-users-for-graph)
-   [API Composition Navigator on Developer Hub](api-composition-navigator-on-developer-hub-8e75d31.md)



</td>
<td valign="top">

Required

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2025-07-29

</td>
<td valign="top">

2025-07-29

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Change in getting API Composition service credentials in API consumption for client applications

</td>
<td valign="top">

The service plan for enabling client applications has changed. You no longer use the *api* service plan under *SAP Graph*.

The new service plan is *integration-flow* under the *Process Integration Runtime* service. In order to use this plan, you need to set up the authentication by creating a *Process Integration Runtime* instance.

> ### Note:  
> Your subaccount in SAP BTP must be in the Cloud Foundry environment and Cloud Foundry-enabled.

> ### Note:  
> The API Composition *api* service plan will no longer be available after June 30th, 2025.

For more information, see:

-   [Configure Entitlement for Graph](https://help.sap.com/docs/graph/graph/initial-setup?version=PROD#1-configure-entitlement-for-graph)
-   [Authentication](https://help.sap.com/docs/integration-suite/sap-integration-suite/authentication-fa6eec4f9ffc45aa89f8a2155b855ca4)



</td>
<td valign="top">

Required

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Changed

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2025-05-20

</td>
<td valign="top">

2025-05-20

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Enabling client applications to access API Composition business data graph

</td>
<td valign="top">

Client applications must know certain secrets, known as API Composition service credentials in order to be able to consume Business Data Graph APIs. There is a new way of getting these secrets. See [Enabling Client Applications](https://help.sap.com/docs/graph/graph-wip/enabling-client-applications).

> ### Note:  
> By June 30th, 2025, no new instance of API Composition with the *api* service plan can be created. If you are still using the *api* service plan from Graph, we recommend you now use *integration-flow* plan in the *Process Integration Runtime* service. For more information, see [Configure Entitlement for Graph](https://help.sap.com/docs/graph/graph/initial-setup?version=PROD#1-configure-entitlement-for-graph).



</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2025-05-20

</td>
<td valign="top">

2025-05-20

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API Composition supports OpenAPI-specific REST services for business data graphs

</td>
<td valign="top">

You can use OpenAPI-specific REST services in addition to OData services as data sources for business data graphs. This allows you to construct a unified API across different API protocols for diverse enterprise landscapes.

> ### Note:  
> API Composition does not yet fully support optional parameters in imported REST operations. All parameters by default are required for these operations.

For more information, see:

-   [REST Services](rest-services-3fa3dc3.md)
-   [REST Services as Data Sources](rest-services-as-data-sources-83b14c2.md)



</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2025-04-08

</td>
<td valign="top">

2025-04-08

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Modify Business Data Graph in JSON format

</td>
<td valign="top">

You can edit your business data graph in JSON format on the UI.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Changed

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2025-02-25

</td>
<td valign="top">

2025-02-25

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Improved visualization of actions and functions

</td>
<td valign="top">

The visualization of actions and functions in the API Composition Navigator have been enhanced. For more information, see [Actions and Functions](actions-and-functions-3572dfb.md).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2025-01-21

</td>
<td valign="top">

2025-01-21

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Business Data Graph Editor

</td>
<td valign="top">

You can edit your business data graph directly in API Composition on Integration Suite.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2024-11-18

</td>
<td valign="top">

2024-11-18

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

New API Composition Guest user role for read-only access

</td>
<td valign="top">

You can enable users to have read-only access to API Composition and the API Composition Configuration API by assigning the API Composition guest role to one or more users. For more information, see:

-   [Enabling Guest Users](https://help.sap.com/docs/graph/graph/enabling-users?version=PROD)

-   [Define Users for Graph](https://help.sap.com/docs/graph/graph/initial-setup?version=PROD#3.-define-users-for-graph)




</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2024-10-07

</td>
<td valign="top">

2024-10-07

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

New features on API Composition UI for business data graph configuration

</td>
<td valign="top">

API Composition now displays the details of a business data graph on SAP Integration Suite. This includes listing all entities with their configured locating rules exposed by a business data graph. Listing all entities was previously only available on the API Composition Navigator in SAP API Business Hub Enterprise.

In addition, the details of the cues and key mappings are displayed if they are available for your business data graph.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2024-07-02

</td>
<td valign="top">

2024-07-02

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Add comments to API Composition documentation using GitHub

</td>
<td valign="top">

Customer feedback has always been important to us. We love hearing from you because it gives us insight into how you use our products and if our documentation is helping you achieve your goals.

Now, with the introduction of the Open Documentation Initiative, we offer a unique collaboration channel that enables you to actively participate, provide feedback, and even make edits to our documentation via GitHub, ensuring that we address your specific needs.

We look forward to hearing from you. For more information on how to collaborate, see [Collaborate with Us – Open Documentation Initiative for Graph](https://community.sap.com/t5/welcome-corner-blog-posts/collaborate-with-us-open-documentation-initiative-for-sap-integration-suite/ba-p/13565566).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2024-07-02

</td>
<td valign="top">

2024-07-02

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API Composition documentation available in SAP Integration Suite documentation

</td>
<td valign="top">

API Composition documentation is now available in the following sections of the SAP Integration Suite documentation:

-   [Capabilities of SAP Integration Suite](https://help.sap.com/docs/integration-suite/sap-integration-suite/capabilities)

-   [Design](https://help.sap.com/docs/integration-suite/sap-integration-suite/design)

-   [Monitoring and Troubleshooting for Graph](https://help.sap.com/docs/integration-suite/sap-integration-suite/monitoring-and-troubleshooting)




</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2024-07-02

</td>
<td valign="top">

2024-07-02

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Model Extensions and Custom Entity Modeling is supported

</td>
<td valign="top">

Extending and customizing business data graphs with model extensions is now available on the Model Extensions tab in API Composition. For more information, see the tutorial: [API Composition with Graph: Customizing your Business Data Graphs with Model Extensions](https://community.sap.com/t5/technology-blogs-by-sap/api-composition-with-graph-customizing-your-business-data-graphs-with-model/ba-p/13639447).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2024-03-18

</td>
<td valign="top">

2024-03-18

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Manage Business Data Graphs using API Composition Configuration API

</td>
<td valign="top">

The API Composition Configuration API simplifies the process of managing your business data graphs automatically. Whether you need to create, update, or delete business data graphs, this API provides an automated option to achieve these tasks.

The primary focus is to enable a seamless integration of business data graph management with your existing CI/CD pipelines.

For more information, see:

-   [Configure Entitlement for Graph](https://help.sap.com/docs/graph/graph/initial-setup?version=PROD#1.-configure-entitlement-for-graph)

-   [Manage Business Data Graphs using API Composition Configuration API](manage-business-data-graphs-using-api-composition-configuration-api-655bf12.md)




</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2024-03-05

</td>
<td valign="top">

2024-03-05

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

New domains available for API Composition 

</td>
<td valign="top">

The API Composition capability is now available under the common super-domain `a.integration.cloud.sap` to which each tenant has a dedicated subdomain assigned. The API Composition API is available at`https://<tenant-subdomain>.a.integration.cloud.sap/graph/api`. The tenant subdomain is retrieved from the API Composition UI or by creating service bindings and services keys in your SAP BTP subaccount.

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2023-08-22

</td>
<td valign="top">

2023-08-22

</td>
</tr>
<tr>
<td valign="top">

API Composition 

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

API Composition, a capability of API Management, part of the SAP Integration Suite

</td>
<td valign="top">

API Composition is a new and innovative capability of API Management within SAP Integration Suite. Extending traditional API Management, API Composition enables you to expose all your business data in the form of a semantically connected data graph, accessed via a single unified and powerful API. With API Composition you have:

-   Out-of-the-box connected data graphs for all major SAP apps with custom model extensions that support unified OData v4 and GraphQL

-   Graphical user interface in SAP Integration Suite, including a configuration wizard and API Composition Navigator in SAP Business Accelerator Hub

-   API Composition support for SAP Build


For more information, see [What Is API Composition?](what-is-api-composition-456fc54.md)

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Intelligent Technologies

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Capability of API Management within SAP Integration Suite

</td>
<td valign="top">

2023-07-10

</td>
<td valign="top">

2023-07-10

</td>
</tr>
</table>

**Related Information**  


[What Is API Composition?](what-is-api-composition-456fc54.md "")

