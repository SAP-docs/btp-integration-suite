<!-- loio7051f883696e49428f64fc4af055df25 -->

# Network and Communication Security for Edge Integration Cell

Edge Integration Cell only uses encrypted communication. Internal communication is secured using mutual Transport Layer Security \(mTLS\), enabled via Istio, following a zero-trust paradigm. For more information, see [Security](https://istio.io/latest/docs/concepts/security/).

For all communication flows listed in the table below, except for Content Deployment, `*.hana.ondemand.com` is used as the standard endpoint. For Content Deployment, which is used by the Edge Deploy Controller, specific domains are used depending on the deployment environment.

BTP on Azure:

-   `*.blob.storage.azure.net`

-   `*.blob.core.windows.net` \(previously used as the BTP Object Store Service Endpoint URL\)


BTP on AWS:

-   `*.amazonaws.com`

BTP on GCP:

-   `*.storage.googleapis.com`

BTP on SAP Cloud Infrastructure:

-   `*.osaas.hana.ondemand.com`

The following table provides an overview of communication flows between a cloud and an edge environment.

****


<table>
<tr>
<th valign="top">

Flow

</th>
<th valign="top">

In/Out

</th>
<th valign="top">

Protocol

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Content Deployment

</td>
<td valign="top">

Out

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Synchronizes content from SAP BTP Object Store. Used by Edge Deploy Controller.

</td>
</tr>
<tr>
<td valign="top">

Security Material

</td>
<td valign="top">

Out

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Synchronizes security material from SAP BTP Credential Store. Used by Edge Security Artifact Controller.

</td>
</tr>
<tr>
<td valign="top">

System Internal Events

</td>
<td valign="top">

Out

</td>
<td valign="top">

Websocket

</td>
<td valign="top">

Exchanges system-internal events to SAP Integration Suite. Used by the Edge Event Controller.

</td>
</tr>
<tr>
<td valign="top">

Application Monitoring

</td>
<td valign="top">

In

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Processes monitoring and operations API calls from SAP Integration Suite via Cloud Connector. Used by API Application.

</td>
</tr>
<tr>
<td valign="top">

Configuration Service

</td>
<td valign="top">

Out

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Reads configuration from SAP Integration Suite Configuration Service. Used by Policy Engine, Worker.

</td>
</tr>
<tr>
<td valign="top">

XSUAA

</td>
<td valign="top">

Out

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Handles authentication and authorization via SAP BTP Authorization and Trust Management Service \(XSUAA\).

</td>
</tr>
<tr>
<td valign="top">

Destination Service

</td>
<td valign="top">

Out

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Synchronizes destinations from SAP BTP Destination Service. Used by Destination Service Data Maintainer.

</td>
</tr>
<tr>
<td valign="top">

Audit Log Service

</td>
<td valign="top">

Out

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Synchronizes audit logs with SAP BTP Audit Log Service. Used by Auditlog Agent.

</td>
</tr>
</table>

For more information, see [Network and Communication Security](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/91e43a0f8ef44b8e8f543f544d646f30.html).

