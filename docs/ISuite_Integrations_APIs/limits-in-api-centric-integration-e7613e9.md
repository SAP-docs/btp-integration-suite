<!-- loioe7613e9be5df4478968cb9f3c77adb41 -->

# Limits in API-Centric Integration

Review the supported limits and boundary conditions for designing, deploying, and managing API and MCP server artifacts in API-Centric Integration. Staying within these recommended limits helps ensure optimal performance, reliability, and scalability of your artifacts.



API-Centric Integration is designed to operate efficiently within the limits specified in the following tables. These limits apply to various aspects of API and MCP server design, deployment, runtime execution, and policy configuration.

Why these limits are enforced:

-   To ensure consistent performance of APIs and MCP Servers across tenants.

-   To maintain system stability and reliability under varying workloads.

-   To enable predictable runtime behavior during execution.

-   To support scalability by preventing resource over-consumption.

-   To safeguard fair resource allocation in a shared environment.

-   To safeguard fair resource allocation in a shared environment.


> ### Note:  
> These limits are enforced by the platform and cannot be modified by integration developers.

**Limits**


<table>
<tr>
<th valign="top">

Artifact Type

</th>
<th valign="top">

Category

</th>
<th valign="top">

Limit

</th>
<th valign="top">

Value

</th>
<th valign="top">

Automatically Enforced

</th>
</tr>
<tr>
<td valign="top">

MCP Server

</td>
<td valign="top">

Tool

</td>
<td valign="top">

A maximum of 15 tools can be generated and exposed per MCP Server, regardless of the source type.

</td>
<td valign="top">

15

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

MCP Server

</td>
<td valign="top">

Token

</td>
<td valign="top">

Maximum token limit for response.

</td>
<td valign="top">

200,000

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

API Artifact

</td>
<td valign="top">

JSON Threat Protection Policy

</td>
<td valign="top">

Maximum size allowed for a JSON payload is **10000 KB**.

</td>
<td valign="top">

10000 KB

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

API Artifact

</td>
<td valign="top">

XML Threat Protection Policy

</td>
<td valign="top">

Maximum size allowed for a XML payload is **10000 KB**.

</td>
<td valign="top">

10000 KB

</td>
<td valign="top">

Yes

</td>
</tr>
</table>

