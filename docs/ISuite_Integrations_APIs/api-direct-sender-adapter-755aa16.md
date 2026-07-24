<!-- loio755aa1690faf49f1b9e1d6a5a1ee64a2 -->

# API Direct Sender Adapter

Configure the API Direct sender adapter to enable internal invocation of a reusable API by calling API artifacts. The adapter exposes the reusable API internally within Integration Suite without creating an external HTTP endpoint.



The API Direct sender adapter is automatically added when you create a reusable API artifact. It receives requests from calling API artifacts and passes them to the policy model, where configured policies such as authentication, authorization, validation, and transformation are applied before the request is forwarded to the configured receiver adapter. Because communication occurs internally within Integration Suite, the interaction is optimized for low latency while maintaining end-to-end traceability through shared correlation IDs.



## How the API Direct Sender Adapter Works

When a calling API artifact invokes a reusable API artifact, the API Direct sender adapter:

-   Receives requests from the calling API artifact.
-   Provides an internal entry point without exposing an external HTTP endpoint.
-   Passes the request to the policy model for processing.
-   Forwards the processed request to the configured receiver adapter.

The following table describes the properties available for configuring the API Direct sender adapter.

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

Specifies a unique name for the API Direct sender adapter.

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

APIDirect

</td>
<td valign="top">

Displays the adapter type. This value is automatically set to **APIDirect** and cannot be changed.

</td>
</tr>
<tr>
<td valign="top">

Connection

</td>
<td valign="top">

Address

</td>
<td valign="top">

User-defined

</td>
<td valign="top">

Specifies the internal base path used by calling API artifacts to invoke the reusable API artifact. The address must be unique within the tenant.

</td>
</tr>
</table>

