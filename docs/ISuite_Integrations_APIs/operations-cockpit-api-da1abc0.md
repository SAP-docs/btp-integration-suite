<!-- loioda1abc0c46514798bea0d283f0fb418a -->

# Operations Cockpit API

The Operations Cockpit API lets you monitor your Edge Integration Cell systems using a public Odata API.



## Overview



The functionalities from the Edge Integration Cell Operations Cockpit are available through an OData API. You can access your Edge Integration Cell data through a local API even during offline mode when the Operations Cockpit user interface is unavailable. You can retrieve information such as component status, pods, event logs, metrics, and runtime parameters.

You can access the Operations Cockpit API and check its basic operations at the following path: `/api/eic/v1/`.

The Operations Cockpit API uses the OData version 4 specification. The technical protocol is Open Data Protocol \(OData\). This allows you to use standard HTTP methods such as GET to call the API.



## Permissions

Before you use the Operations Cockpit API, make sure you follow these prerequisites:

-   You have access to an OData client.

-   You use any of these authentication methods:

    -   Certificate-based authentication . You need to use a public and a private key for a TLS connection. See [Client Certificate Authentication for API Clients](https://help.sap.com/docs/integration-suite/sap-integration-suite/client-certificate-authentication-for-api-clients?locale=en-US&state=DRAFT&version=DEV) for more details.

    -   ClientId/clientsecret authentication. Use OAuth client credentials for authentication. See  <?sap-ot O2O class="- topic/xref " href="db55f0d917754e999954c2796b11b114.xml" text="" desc="" xtrc="xref:2" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiod8a6092f89b24b5e8531d35c034be3aa_en-US/src/content/localization/en-us/da1abc0c46514798bea0d283f0fb418a.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?>  for more details.


-   You have the required authorizations to operate Edge Integration Cell. For more details, see [Initial Setup | SAP Help Portal](https://help.sap.com/docs/integration-suite/sap-integration-suite/initial-setup-edge?version=CLOUD).




## Resources

The following Edge Integration Cell resources are accessible through the Operations Cockpit API.

****


<table>
<tr>
<th valign="top">

Resource

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Component Monitor

</td>
<td valign="top">

Access system components, their status, pods, event logs, metrics, and runtime parameters. Use querying, filtering, and actions to manage components and their configurations.

You can also restart components with this API.

For more information, see [Component Monitor](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/component-monitor?version=CLOUD).

</td>
</tr>
</table>



## Entities

The Operations Cockpit API contains the following entities:

****


<table>
<tr>
<th valign="top">

Entity Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Component

</td>
<td valign="top">

The Component entity represents system components in Edge Integration Cell. It includes information about component status, pod lists, and runtime parameters.

</td>
</tr>
<tr>
<td valign="top">

Pod

</td>
<td valign="top">

The Pod entity includes information about pod status, event logs, and metrics.

</td>
</tr>
<tr>
<td valign="top">

PodMetric

</td>
<td valign="top">

Pod metrics are key-value pairs which provide selected metrics from Prometheus. Pod metrics are available only for some components.

</td>
</tr>
<tr>
<td valign="top">

PodEvent

</td>
<td valign="top">

Pod events are logs from Kubernetes that relate to specific pods. They provide details about actions affecting a pod, such as when it starts or when errors occur. Pod events usually have a short lifespan and remain available only for a limited time. You can use pod events to troubleshoot issues with pods.

</td>
</tr>
<tr>
<td valign="top">

RuntimeParameter

</td>
<td valign="top">

Components define a set of runtime parameters that you can change to adjust component configurations.

</td>
</tr>
</table>

