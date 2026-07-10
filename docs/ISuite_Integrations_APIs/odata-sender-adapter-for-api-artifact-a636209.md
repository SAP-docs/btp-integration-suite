<!-- loioa6362093d82f40c993dc3eb7b0fecaaa -->

# OData Sender Adapter for API Artifact

The OData sender adapter receives incoming requests from OData clients and acts as the entry point for an OData API artifact. It exposes an OData endpoint that clients use to access the API artifact and forwards the requests to the policy model for processing.



The OData sender adapter is automatically added when you create an API artifact with the **OData** service type. After receiving a request, the adapter passes it to the policy model, where configured policies such as authentication, authorization, IP filtering, quota, and threat protection are applied before the request is forwarded to the target OData service through the receiver adapter.

The adapter configuration defines the endpoint through which clients invoke the OData API and provides the settings required to receive and process OData requests.

****


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Property

</th>
<th valign="top">

Value/Options

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

General

</td>
<td valign="top">

Name

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies a unique name for the OData sender adapter.

</td>
</tr>
<tr>
<td valign="top">

Channel Details:

Description

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies an optional description for the adapter configuration.

</td>
</tr>
<tr>
<td valign="top">

Adapter Details:

Adapter Type

</td>
<td valign="top">

OData

</td>
<td valign="top">

Displays the adapter type. This value is automatically set to **OData** and cannot be changed.

</td>
</tr>
</table>



## How the OData Sender Adapter Works

When an OData client sends a request to an API artifact, the OData sender adapter:

-   -   Accepts incoming OData requests.
-   Passes the requests to the policy model for processing.
-   Forwards the processed requests to the configured OData receiver adapter.
-   Returns the backend response to the client.


