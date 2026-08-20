<!-- loiodd58b69c81214fa3a6ba506fd62035bd -->

# **Establish the Connection Between the Agent and the MCP Server**

Model Context Protocol \(MCP\) standardizes how an agent discovers and invokes tools and resources exposed by enterprise systems through MCP servers.

After the MCP server is successfully deployed and its runtime status changes to *Started*, agents can connect to the MCP server to discover and invoke the tools it exposes. To securely access the MCP server, the agent must first authenticate using the authentication mechanism configured in the Authentication policy in the MCP server. The supported authentication mechanisms include SAP BTP Authorization and Trust Management \(XSUAA\) and external identity providers. See, [Authentication](authentication-fa6eec4.md) and [Authorization](authorization-6658409.md) policy. Only after successful authentication can the agent invoke the available tools.

After obtaining the required OAuth client credentials, configure your AI application to connect to the MCP server. The exact procedure depends on the AI application. For example, in **Claude Desktop**, you add the MCP server as a connector and provide the required connection details.


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

MCP Server URL

</td>
<td valign="top">

The endpoint URL of the MCP server.

</td>
</tr>
<tr>
<td valign="top">

Client ID

</td>
<td valign="top">

The OAuth client ID obtained from the configured authentication mechanism.

</td>
</tr>
<tr>
<td valign="top">

Client Secret

</td>
<td valign="top">

The OAuth client secret. This field is optional if PKCE is enabled.

</td>
</tr>
</table>

You can access MCP Servers in the following two ways:

-   **Accessing an MCP server Using a Technical User Token**

    In this authentication model, the agent accesses the MCP server by using the identity of a technical user or service account. All tool invocations are performed using the permissions assigned to the technical user, regardless of the end user interacting with the agent.

    This model is intended for machine-to-machine communication, autonomous AI agents, background jobs, and other automated scenarios where requests don't need to be executed on behalf of an individual user. For more information, see [Accessing an MCP Server Using a Technical User Token](accessing-an-mcp-server-using-a-technical-user-token-c3c81a8.md).

-   **Accessing an MCP Server Using an IdP User Token**

    In this authentication model, the agent accesses the MCP server on behalf of an authenticated user. Tool invocations are authorized using the identity and permissions of the signed-in user, enabling user-specific access control and auditing.

    This model is intended for interactive agents, such as enterprise copilots and AI assistants, where requests must be executed using the authenticated user's identity. For more information, see [Accessing an MCP Server Using an IdP User Token](accessing-an-mcp-server-using-an-idp-user-token-a9f4183.md).


