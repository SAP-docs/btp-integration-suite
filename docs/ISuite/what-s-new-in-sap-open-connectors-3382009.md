<!-- loio3382009202ab4b7d924feaef48209d4f -->

# What's New in SAP Open Connectors





**Core Components, 2020**


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

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Changed Authentication for Open Connectors SharePoint Connector

</td>
<td valign="top">

The Open Connectors SharePoint Connector authentication based on Microsoft Access Control Service \(ACS\) will stop functioning after April 2, 2026 as Microsoft is retiring Microsoft ACS. All SharePoint connections currently using ACS-based authentication are affected.

To avoid service disruption, we recommend migrating within the SharePoint Connector from ACS authentication to Microsoft Entra ID / Microsoft Graph, which is the approach recommended by Microsoft and supported moving forward.

See SAP Note [3714006](https://me.sap.com/notes/3714006).

</td>
<td valign="top">

Recommended

</td>
<td valign="top">

Deprecated

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">

2026-02-16

</td>
<td valign="top">

2026-04-02

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Rate Limits on Formula Executions

</td>
<td valign="top">

The number of parallel formula executions that can be triggered by a user per minute has been set to 100 execution requests per user per minute.

See: [Introduction to Formulas](https://help.openconnectors.ext.hana.ondemand.com/home/introduction-formulas) 

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

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">

2023-07-19

</td>
<td valign="top">

2023-07-12

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Quickbooks Enterprise

</td>
<td valign="top">

The /reset-session API will allow you to terminate the active session and start a new session to proactively manage transactions and memory issues in the QBD SDK.

</td>
<td valign="top">

Info only

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-09-23

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Cloud Elements

</td>
<td valign="top">

-   You can access the traditional thread pool executor for async producer queue.

-   You can now avoid longer duration on query execution with added connection properties for fast failover of AWS RDS.

-   You can observe reduced number of queries in Data base as the cache object dictionary is now at element instance level.

-   You can now store the data for 48-hours only.

-   You can invoke multiple database calls to hydrate to roles by user id based roles, count this is an insufficient implementation. You can access optimized RoleDaoImpl implementation without redundant calls.




</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-09-23

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Netsuite

</td>
<td valign="top">

You can observed the updated GET/ping results to initialize first and later the call servertime.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-09-23

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Ultipro

</td>
<td valign="top">

You will now see updated error message for POST and PATCH requests for new-hires and pending-hires resources and find 'id' as required field in patch/\{id\} for pending-hires.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-09-23

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Microsoft Office 365

</td>
<td valign="top">

You can now Add photo/attachment upload endpoint for contacts.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-09-23

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

ADP Vantage

</td>
<td valign="top">

You can access the newly added ADP Vantage element with employees get and getById resource. You can also access bulk downloads for employees endpoint.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-09-23

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Dropbox

</td>
<td valign="top">

You can no longer find redundant calls that populate missing configurations in the Initialisation phase.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-09-23

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Google Docs

</td>
<td valign="top">

You can now access a new element with authentication and ping endpoints. You will find the ping endpoint replaced by platform implementation once objects are added.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-09-23

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Sage 200

</td>
<td valign="top">

You can now experience updated OAuth authentication endpoints. The authentication process was updated in February 2021, the current authentication method used is depreciated and no longer available.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-09-23

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Dropbox/Dropbox Business

</td>
<td valign="top">

You can now create an element instance more quickly.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-08-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Microsoft Dynamics CRM REST

</td>
<td valign="top">

You can now use additional API calls and resources.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-08-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Microsoft Dynamics CRM REST

</td>
<td valign="top">

You can now access additional metadata for multiple endpoints.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-08-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Microsoft Dynamics CRM REST

</td>
<td valign="top">

You can now access polling for objects without modified and `createdon` dateFields.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-08-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Microsoft Office 365

</td>
<td valign="top">

You can now upload a contact photo via the element.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-08-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Netsuite ERP

</td>
<td valign="top">

You can now use additional API calls and resources.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

.

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-08-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Platform

</td>
<td valign="top">

You can now automatically convert long integers to strings when values exceed Javascript's maximum safe integer size.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-08-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Platform

</td>
<td valign="top">

You can now only view polling records from the past 48 hours.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-08-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Sage 200 Accounting

</td>
<td valign="top">

You can now authenticate an element instance using Sage's updated authentication credentials.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-08-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Salesforce Sales Cloud

</td>
<td valign="top">

You can now utilize correct datatypes for all fields when calling `GET /metadata`.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-08-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Ultipro/Microsoft Dynamics Business Cloud Central

</td>
<td valign="top">

You can now receive more consistent error messaging for `POST/` and `PATCH` calls to `new-hires` and `pending-hires`.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-08-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Bulk

</td>
<td valign="top">

You can now see the status of all jobs in the bulk UI.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-06-26

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Increase in timeout

</td>
<td valign="top">

You can access the GET /ledger-details resource with an extented 5 minute timeout.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-29

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Removed Access

</td>
<td valign="top">

You can no longer access the deprecated GET /accounts endpoint.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-29

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Authentication Types

</td>
<td valign="top">

You can now authenticate using either OAuth2 or basic authentication.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-29

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Profile information search

</td>
<td valign="top">

You can now retrieve your own profile information using the 'GET /users/:emailOrId' API, regardless of your account privileges.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-29

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Cloud for customer version update

</td>
<td valign="top">

You can now use the latest version of the Cloud for Customer OData API \(c4codataapi\) using the element. The preceding version of the API \(c4codata\) is deprecated and unavailable.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-29

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Access update

</td>
<td valign="top">

You can now access the POST and PATCH /AR-Adjustments legacy endpoints.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-29

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Updated Swagger documention

</td>
<td valign="top">

You can now view and interact with updated swagger documentation.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-29

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Mapping resource to user object

</td>
<td valign="top">

You can now map common resources to the 'users' object in the UI.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-29

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Error on GET /audit-logs fixed

</td>
<td valign="top">

You can now receive comprehensive responses from the 'GET /audit-logs' call.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Configuration update

</td>
<td valign="top">

You can now configure polling events.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Call a resource without an issue

</td>
<td valign="top">

You can now call these resources without issue:

-   POST​/channels

-   GET​/channels

-   GET​/channels​/\{channelId\}

-   GET​/channels​/\{channelId\}​/history

-   POST​/channels​/\{channelId\}​/user

-   DELETE​/channels​/\{channelId\}​/user​/\{userId\}

-   POST​/messages

-   GET​/messages

-   GET​/messages​/\{messageThreadId\}

-   DELETE​/messages​/\{messageThreadId\}




</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Endpoint fields update

</td>
<td valign="top">

You can now use dot or comma notation for endpoint fields that support it.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Instance Authentication

</td>
<td valign="top">

You can now properly authenticate instances in the UI.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Fixed GET /resources

</td>
<td valign="top">

You can now specify account-specific resources to retrieve when calling 'GET /resources'.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Access update

</td>
<td valign="top">

You can now access the Tax Details service with objectId 468.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Common resources will be shared even after migrating environments

</td>
<td valign="top">

Your shared common resources will now stay shared after being migrated between environments.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Discovery resources

</td>
<td valign="top">

You can now use bulk for discovery resources.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Authetication error message alerts fixed

</td>
<td valign="top">

You can now receive accurate error messaging on authentication and authorization failures.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Temporary credentials for instance creation

</td>
<td valign="top">

You can now provision an instance using temporary credentials.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Lists endpoints added to Sharepoint connector

</td>
<td valign="top">

You can now access the sub-sites/lists endpoints:

-   POST /sites/lists

-   GET /sites/lists

-   PATCH /sites/lists/\{id\}

-   GET ​/sites​/lists​/\{id\}

-   DELETE /sites/lists/\{id\}

-   POST /sites/lists/\{id\}/items

-   GET /sites/lists/\{id\}/items

-   PATCH /sites/lists/\{id\}/items/\{itemId\}

-   GET /sites/lists/\{id\}/items/\{itemId\}

-   DELETE /sites/lists/\{id\}/items/\{itemId\}




</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Updated Descriptions

</td>
<td valign="top">

You can now view updated descriptions in the element's swagger API documentation.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Formula execution steps

</td>
<td valign="top">

You can now see the formula execution's steps while the execution is pending.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Canceled details available on the Formula Execution page

</td>
<td valign="top">

You can now view details of a given canceled formula execution on the Formula Executions page.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-05-01

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Concurrent formula executions

</td>
<td valign="top">

You can now enable or disable concurrent formula executions.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

New users via social logins

</td>
<td valign="top">

You can now automatically create a Github or Google social login when creating a new user; if the user does not exist, they will now be created.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Common resource library

</td>
<td valign="top">

You can now view very large common resource libraries more easily.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Import formulas with multiple triggers

</td>
<td valign="top">

You can now import formulas that use multiple triggers \(though only one trigger can be active at a time\).

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

User email verification via API

</td>
<td valign="top">

You can now complete the email verification process for users via the API.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Timeout increase

</td>
<td valign="top">

You can now use an increased timeout for calls made to the ledger-details endpoint to 180 seconds.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

GET /contacts events update

</td>
<td valign="top">

You can now use polling events on the GET /contacts endpoint.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Object metadata updates

</td>
<td valign="top">

You can now use both the 'reply\_time\_in\_minutes.business' and 'reply\_time\_in\_minutes.calendar' fields with the 'ticket\_metrics' object metadata call.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Deprecated APIs for the Slack connector

</td>
<td valign="top">

You can no longer access certain deprecated Slack APIs; see their documentation \(https://api.slack.com/changelog/2020-01-deprecating-antecedents-to-the-conversations-api\) for more information about the deprecations.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Connector updates

</td>
<td valign="top">

You can now utilize these updates to the connector:

-   returning a proper response for empty contacts

-   events-related instance improvements

-   expanded responses to the GET /objects endpoint




</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Usage update on x-searchable-operators

</td>
<td valign="top">

You can now use x-searchable-operators as comma-separated strings for model searchables; you can include them in Connector Builder's 'Models' tab of any available resource.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Increased timeout

</td>
<td valign="top">

You can now use an extended timeout when calling 'GET /ledger-details'.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Improved API documentation

</td>
<td valign="top">

You can now access enhanced documentation for our platform APIs.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Update on Bullhorn connector

</td>
<td valign="top">

You can now used dot notation with the 'Notes' endpoint when using the 'where' query.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Xero v2 connector update

</td>
<td valign="top">

You can now use the 'where' clause with 'GET /sales-quotes' and 'GET /purchase-orders' calls.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Shopify connector update

</td>
<td valign="top">

You can now call 'customers/\{id\}/abandoned-checkouts' without issue.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Quickbooks Online connector error codes

</td>
<td valign="top">

You can now receive more consistent error codes.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

NetSuite ERP connector

</td>
<td valign="top">

You can now call the 'advanced-searches' resource.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Sort Contact

</td>
<td valign="top">

You can now sort 'GET /contacts' calls by created date.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Bulk support

</td>
<td valign="top">

You can now use all supported bulk functionality.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Updated Excel

</td>
<td valign="top">

You can now upload Excel files that contain empty rows.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Fixed authentication issues

</td>
<td valign="top">

You can now validate connector authentication.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Files connector

</td>
<td valign="top">

You can now properly populate the 'fileName' and 'fileType' fields in responses.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

BoxV2 connector

</td>
<td valign="top">

You can now call 'GET /ping' without issue.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Update on Netsuite Finance connector

</td>
<td valign="top">

You can now use these resources:

-   'discount-items'

-   'contacts

-   ''

-   'sales-quotes'

-   'item-fulfillments'

-   'cash-sales'

-   'purchase-requisitions'

-   'item-receipts'




</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Update on Netsuite ERP connector

</td>
<td valign="top">

You can now use the 'purchase-requisitions' and 'discount-items' resources.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-04-09

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Add transformations from common resource overview

</td>
<td valign="top">

You can now add a transformation to a common resource directly from the common resource's overview page.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-03-06

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Tango Card x-searchables

</td>
<td valign="top">

You can now use x-searchables with the Tango Card connector.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-03-06

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Microsoft Dynamics CRM x-searchables

</td>
<td valign="top">

You can now use x-searchables with the Microsoft Dynamics CRM connector.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-03-06

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Empty arrays omitted

</td>
<td valign="top">

You can now call all usage-checking APIs without returning erroneously empty arrays.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-03-06

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Microsoft Dynamics HR on public catalog

</td>
<td valign="top">

You can now use the Microsoft Dynamics HR connector from the public connectors catalog.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-03-06

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Shopify x-searchables

</td>
<td valign="top">

You can now use x-searchables with the Shopify connector.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-03-06

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Pardot x-searchables

</td>
<td valign="top">

You can now use x-searchables with the Pardot by Salesforce connector.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-03-06

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Added field on BigQuery coneector

</td>
<td valign="top">

You will now see the 'vendorType' field included in responses to 'GET /objects/\{objectName\}/metadata' calls.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-03-06

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Feature update on Freshbooks Cloud Accounting connector

</td>
<td valign="top">

You can now use the 'sales-quotes' object, as well as bulk upload and download jobs for these resources:

-   'customers'

-   'expenses'

-   'invoices'

-   'items'

-   'payments'

-   'taxes'

-   'vendors'




</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-03-06

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

BigQuery connector documentation

</td>
<td valign="top">

You can now utilize updated functionality per vendor-side updates.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-03-06

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

ServiceNow OAuth connector update

</td>
<td valign="top">

You can now call 'GET /objects/\{objectName\}/metadata' properly.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

New /dimensions endpoint for the Intacct v3 connector

</td>
<td valign="top">

You can now use the /dimensions endpoint with the Intacct v3 connector.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Expanded Xero connector authentication options

</td>
<td valign="top">

You can now authenticate the Xero connector with or without the tenant ID or tenant name fields, so long as the associated Xero account has only one organization.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Fixed POST /contacts functionality for the Microsoft Office 365 connector

</td>
<td valign="top">

You can now make the POST /contacts call with the Microsoft Office 365 connector to generate an updated event instead of a created event.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Enhancements to the Coupa connector

</td>
<td valign="top">

You can now use the Coupa connector's user-groups resource, as well as these endpoints:

-   contracts/\{id\}/attachments

-   contracts/\{id\}/attachments/\{attachmentId\}/files

-   contracts/\{id\}/legal-files




</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Updated common resource models

</td>
<td valign="top">

You can now use the id field in the array of a common resource.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

New sample cURLs for Pardot connector authentication types

</td>
<td valign="top">

You can now view different example cURLs for the Pardot connector's respective authentication types.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

X-searchables for the Netsuite ERP connector, Netsuite Finance connector, Quickbooks Enterprise connector, and Sage Intacct connector

</td>
<td valign="top">

You can now use x-searchables with the Netsuite ERP connector, Netsuite Finance connector, Quickbooks Enterprise connector, and Sage Intacct connector.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Enhanced authentication options for the Amazon S3 connector

</td>
<td valign="top">

You can now authenticate the Amazon S3 connector using the x-amz-security-token parameter. See Amazon's documentation \(https://docs.aws.amazon.com/AmazonS3/latest/userguide/MakingRequests.html\) for more information about using temporary security credentials.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Webhook support for some Xero connector objects

</td>
<td valign="top">

You can now configure webhooks for the Xero connector's /contacts and /invoices objects.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Data integration for the Manage Environments UI

</td>
<td valign="top">

You can now view a list of artifacts with dependencies when exporting environment content, providing a comprehensive view of dependent artifacts missing from the output.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Enhancements to Files connector

</td>
<td valign="top">

You can now use new features of the Files connector, including:

-   updates to the sample payload

-   new default request/response payloads

-   updated models on the PUT /metadata call




</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Retiring the SAP Cloud Platform brand

</td>
<td valign="top">

The SAP Cloud Platform brand is retired. The cloud platform is part of SAP Business Technology Platform \(SAP BTP\), and categorized into SAP Integration Suite and SAP Extension Suite. We are in the process of changing all our documentation, enablement materials, and tools related to SAP Open Connectors accordingly.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2021-02-13

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Update Xerov2 Connector Authentication Requirements

</td>
<td valign="top">

You no longer need the xero.tenant.id parameter to authenticate the Xerov2 connector; you can now provide either the xero.tenant.id or xero.tenant.name parameters.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-11-18

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Add Resource to Coupa Connector

</td>
<td valign="top">

You can now makes calls to the /invoices endpoint in the Coupa connector.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-11-18

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Add 'GET /events/\{id\} API' to ChargeBee Connector

</td>
<td valign="top">

You can now use the 'GET /events/\{id\}' API with the ChargeBee connector.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-28

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Add New Resources to Sugar Market Connector

</td>
<td valign="top">

You can now make calls to the following resources of the Sugar Market connector:

-   '/accounts'

-   '/alerts'

-   '/contacts'

-   '/opportunities'




</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-28

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Add 'GET/GETById /incident-metrics' API to Zendesk Connector

</td>
<td valign="top">

You can now use the 'GET/GETById /incident-metrics' API with the Zendesk connector.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-28

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Add '/ping' Resource to Click Field Service Edge Connector

</td>
<td valign="top">

You can now use the '/ping' resource with the Click Field Service Edge connector.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-21

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Add New Resources to Microsoft Dynamics Business Central Cloud Connector

</td>
<td valign="top">

You can now make calls to the following resources of the Microsoft Dynamics Business Central Cloud connector:

-   '/purchase-return-orders'

-   '/transfer-orders'

-   '/inventory-ledger-entries'

-   '/journal-lines'

-   '/incoming-payments'

-   '/contacts'

-   '/sales-quotes'

-   '/shipments'

-   '/sale-returns'

-   '/purchase-quotes'

-   '/purchase-invoices'




</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-21

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Allow Sub-Org and Account Org Admins to create Common Object at Org Level

</td>
<td valign="top">

Sub-Org and Account Org admins can now create common object transformations at the Organization level.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Add Metadata to ServiceNow/ServiceNow OAuth Connector Responses

</td>
<td valign="top">

You can now see all available metadata fields in any responses to the ServiceNow and ServiceNow OAuth connectors.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Update Models for the '/items' Endpoint of the ServiceNow/ServiceNow OAuth Connectors

</td>
<td valign="top">

You can now use all available models for the '/items' endpoint of the ServiceNow/ServiceNow OAuth connectors.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-14

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Implement Increased Password Policy Standards

</td>
<td valign="top">

For security reasons, all user passwords must now follow a newly enhanced security standard.

See: [Manage Security Settings](https://help.openconnectors.ext.hana.ondemand.com/home/manage-security-settings#configure-passwords).

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-05

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Fix Ping for Snowflake Connector

</td>
<td valign="top">

You can now receive standardized responses from the Snowflake connector's '/ping' endpoint.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-05

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Add Trial Balances to the Intacct Connector

</td>
<td valign="top">

You can now use the trial balances resource \('GET /trial-balances'\) of the Sage Intacct connector.

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-05

</td>
</tr>
<tr>
<td valign="top">

Open Connectors

</td>
<td valign="top">

-   Neo
-   Cloud Foundry



</td>
<td valign="top">

Release Notes

</td>
<td valign="top">

For Release Notes related to SAP Open Connectors prior to October 2020, see: [What's new with SAP Open Connectors?](https://help.openconnectors.ext.hana.ondemand.com/home/whats-new) 

</td>
<td valign="top">

 

</td>
<td valign="top">



</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Business Technology Platform

</td>
<td valign="top">



</td>
<td valign="top">

2020-10-01

</td>
</tr>
</table>

