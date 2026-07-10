<!-- loio4a0ac4447cbe449caf8eda8f0533bc96 -->

# HTTPS Sender Adapter for API Artifact

The HTTPS sender adapter receives incoming client requests and acts as the entry point for an API artifact. It establishes a secure HTTPS connection between the client and the API artifact, enabling requests to enter the policy model for processing before they are forwarded to the backend service.



The HTTPS sender adapter is automatically added when you create an API artifact. It receives incoming requests and passes them to the policy model, where configured policies such as authentication, authorization, IP filtering, quota, and threat protection are applied before the request is forwarded to the target endpoint.



## How the HTTPS Sender Adapter Works

When a client sends a request to an API artifact, the HTTPS sender adapter:

-   Accepts incoming HTTPS requests.
-   Establishes a secure TLS connection with the client.
-   Passes the request to the policy model for processing.
-   Forwards the processed request to the configured receiver adapter.

The following table describes the properties available for configuring the HTTPS sender adapter.

**Configuration Properties**


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

Specifies a unique name for the HTTPS sender adapter.

</td>
</tr>
<tr>
<td valign="top">

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

Adapter Type

</td>
<td valign="top">

HTTPS

</td>
<td valign="top">

Displays the adapter type. This value is automatically set to **HTTPS** and cannot be changed.

</td>
</tr>
</table>

