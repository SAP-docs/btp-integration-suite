<!-- loio572e7fd920394801a9074d2fcbec159b -->

# How Model Context Protocol \(MCP\) Server Enables AI Integration

The MCP server enables AI agents to interact with enterprise systems through a structured process.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

APIs are exposed via the MCP gateway with proper metadata, policies, tools and resources with clear inputs and descriptions for AI agents to consume. Optionally, back-end data sources like files or databases can also be connected, if exposed via HTTP API. Finally, AI agents can interpret prompts, invoke the right tools, and securely access real-time data.



## MCP Server as a First-Class Artifact on SAP Integration Suite



### **What does "first-class artifact" mean?**

In SAP Integration Suite's Integration Cell runtime, artifacts are self-contained units with independent lifecycles, versioning, deployment, and monitoring. Elevating the MCP server to first-class artifact status means it operates as a standalone entity rather than a subordinate component—enabling independent design, deployment, and lifecycle management equivalent to API or integration flow artifacts.

-   It appears as its own artifact type in the design workspace
-   It can be independently deployed to the Integration Cell runtime
-   It has its own deployment status, version history, and operational visibility
-   It is governed under the same transport and lifecycle mechanisms as other SAP Integration Suite artifacts



### **What can be exposed as an MCP Server?**

An MCP Server on Integration Cell bridges AI agents and your integration ecosystem. It can expose:

-   **Managed APIs** — REST, OData, and SOAP APIs within SAP Integration Suite \(including SAP and third-party backends, plus optional HTTP-connected data sources\)
-   **External HTTP endpoints**— Any publicly accessible HTTP service, regardless of origin
-   **SAP RFCs** — Native RFC function modules, allowing agents to invoke ABAP business logic directly



<a name="loio572e7fd920394801a9074d2fcbec159b__section_op4_3pk_kgc"/>

## Overview of the Process


<table>
<tr>
<th valign="top">

Steps

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

1. Create an MCP server

</td>
<td valign="top">

You can create an MCP server by choosing one of the following sources and providing the corresponding details:

-   API artifact deployed in Integration Suite. See, [Create an MCP Server from an API Artifact](create-an-mcp-server-from-an-api-artifact-9f18140.md)
-   HTTP endpoint with an OpenAPI specification. See, [Create an MCP Server from an HTTP Endpoint](create-an-mcp-server-from-an-http-endpoint-b59f141.md)
-   RFC-based backend \(for example, SAP S/4HANA or SAP ECC\). See, [Create an MCP Server by Referring to an RFC-Based Backend](create-an-mcp-server-by-referring-to-an-rfc-based-backend-cbb8b78.md)



</td>
</tr>
<tr>
<td valign="top">

2. Govern and manage the MCP server

</td>
<td valign="top">

After creating the MCP server, you can edit it to manage its configuration, including *Source*, *Tools*, *Resources*, *Prompts* and *Policies*.

</td>
</tr>
<tr>
<td valign="top">

3. Deploy the MCP server.

</td>
<td valign="top">

After configuring your MCP server, deploy it on Integration Cell runtime to make it active. See, [Deploy an Artifact](deploy-an-artifact-b70e7ec.md).

</td>
</tr>
<tr>
<td valign="top">

4. Discover and Publish the MCP server in Developer Hub

</td>
<td valign="top">

Next, navigate to Developer Hub to discover the deployed MCP server from SAP Integration Suite business system. For the detailed steps, see [Discover and Publish MCP Servers from SAP Integration Suite](discover-and-publish-mcp-servers-from-sap-integration-suite-9db32d0.md).

</td>
</tr>
<tr>
<td valign="top">

5. Subscribe to the MCP Server Product

</td>
<td valign="top">

To securely invoke the MCP server, subscribe to the MCP product in Developer Hub. See, [Subscribe to Products to Make MCP Servers Agent-Ready](subscribe-to-products-to-make-mcp-servers-agent-ready-2df6934.md).

</td>
</tr>
<tr>
<td valign="top">

6. Analyze MCP Server Consumption and Performance

</td>
<td valign="top">

After you deploy an MCP server, use the *Analyze* section to review its usage and performance.

The Analytics dashboard provides easy-to-use reporting tools that help you analyze the usage and performance of MCP servers. The analytical data is spread across various report pages, namely Overview, Health, and Usage. Each page provides information about key MCP server metrics, such as AI agent calls, MCP server calls, errors, response times, AI agent activity by target type, and more.

For more information, see [Analyze APIs and MCP Servers](analyze-apis-and-mcp-servers-da4af34.md).

</td>
</tr>
</table>

