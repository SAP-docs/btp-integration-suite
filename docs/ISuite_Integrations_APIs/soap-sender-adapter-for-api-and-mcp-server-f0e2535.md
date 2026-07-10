<!-- loiof0e2535f4b244ded8f42523a71debc9f -->

# SOAP Sender Adapter for API and MCP Server

The SOAP sender adapter receives incoming SOAP requests and acts as the entry point for a SOAP API artifact. It exposes the SOAP endpoint through which client applications invoke the API artifact and forwards incoming requests to the policy model for processing.



The SOAP sender adapter is automatically added when you create an API artifact with the **SOAP** service type. After receiving a request, the adapter passes it to the policy model, where configured policies such as authentication, authorization, IP filtering, quota, and threat protection are applied before the request is forwarded to the SOAP receiver adapter.

The adapter configuration identifies the sender channel and the adapter type. Connection and message-level security settings for communication with the backend SOAP service are configured on the SOAP receiver adapter.



## How the SOAP Sender Adapter Works

When a client invokes a SOAP API artifact:

-   The SOAP sender adapter receives the incoming SOAP request.
-   The request is forwarded to the policy model.
-   The configured policies process the request.
-   The SOAP receiver adapter invokes the target SOAP service.
-   The response is returned through the policy model to the client.



## Configuration Properties

The following table describes the properties available for configuring the SOAP sender adapter.

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

Specifies a unique name for the SOAP sender adapter.

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

SOAP \(Read-only\)

</td>
<td valign="top">

Displays the adapter type. This value is automatically set to **SOAP** and cannot be changed.

</td>
</tr>
</table>

