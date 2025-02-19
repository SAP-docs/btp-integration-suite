<!-- loio7051f883696e49428f64fc4af055df25 -->

# Network and Communication Security for Edge Integration Cell

Edge Integration Cell only uses encrypted communication. Internal communication is secured using mutual Transport Layer Security \(mTLS\), enabled via Istio, following a zero-trust paradigm. For more information, see [Security](https://istio.io/latest/docs/concepts/security/).

For all communication flows listed in the table below, except for the Edge Deploy Controller, the domain `*.hana.ondemand.com` is used as the standard endpoint. For the Edge Deploy Controller, specific domains are used depending on the deployment environment:

BTP on Azure:

-   `*.blob.storage.azure.net`

-   `*.blob.core.windows.net` \(previously used as the BTP Object Store Service Endpoint URL\)


BTP on AWS:

-   `*.amazonaws.com`

BTP on GCP:

-   `*.storage.googleapis.com`

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

Details

</th>
</tr>
<tr>
<td valign="top">

Edge Deploy Controller

</td>
<td valign="top">

Out

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Used to synchronize content from an object store.

</td>
</tr>
<tr>
<td valign="top">

Edge Security Artifact Controller

</td>
<td valign="top">

Out

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Used to synchronize security material from a secure store.

</td>
</tr>
<tr>
<td valign="top">

Edge Event Controller

</td>
<td valign="top">

Out

</td>
<td valign="top">

Websocket

</td>
<td valign="top">

Used to transfer events.

</td>
</tr>
<tr>
<td valign="top">

Policy Engine

</td>
<td valign="top">

Out

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Used to authenticate and authorize users via XSUAA.

</td>
</tr>
<tr>
<td valign="top">

Worker

</td>
<td valign="top">

Out

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Used to read configuration from a secure store.

</td>
</tr>
<tr>
<td valign="top">

API Application

</td>
<td valign="top">

In

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Monitoring and operations API calls from the cloud.

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

Used by all components when accessing cloud services.

</td>
</tr>
</table>

For more information, see [Network and Communication Security](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/91e43a0f8ef44b8e8f543f544d646f30.html).

