<!-- loio49b84477bba142bd90e73e008113cbf6 -->

# Establish the Connection Between the AI Application and the MCP Server

After obtaining the required OAuth client credentials, configure your AI application to connect to the MCP server. The exact procedure depends on the AI application. For example, in **Claude Desktop**, you add the MCP server as a connector and provide the required connection details.

Specify the following information:


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

**MCP Server URL**

</td>
<td valign="top">

The endpoint URL of the MCP server.

</td>
</tr>
<tr>
<td valign="top">

**Client ID**

</td>
<td valign="top">

The OAuth client ID obtained from the configured authentication mechanism.

</td>
</tr>
<tr>
<td valign="top">

**Client Secret**

</td>
<td valign="top">

The OAuth client secret. This field is optional if PKCE is enabled.

</td>
</tr>
</table>

During the first connection, the AI application redirects you to the configured identity provider to complete authentication. After successful authentication, the application can discover the tools exposed by the MCP server and invoke them on your behalf.

After saving the configuration, connect to the MCP server. During the initial connection, the AI application redirects you to the identity provider configured in the MCP server's **Authentication** policy. After successful authentication, the AI application can discover and invoke the tools exposed by the MCP server.

> **Example:** In Claude Desktop, these values are entered when adding the MCP server as a connector.

1.  > Open **Claude Desktop**.
2.  > Add a new **MCP Server** connector.
3.  > Enter the *MCP Server URL*, *Client ID*, and *Client Secret* details.
4.  > Save the configuration.
5.  > Connect to the MCP server.

> During the initial connection, Claude Desktop redirects you to the identity provider configured in the MCP server's **Authentication** policy. After successful authentication, Claude Desktop can discover and invoke the tools exposed by the MCP server.

> ### Note:  
> **Microsoft Entra ID and Auth0**: If your MCP server is configured with Microsoft Entra ID or Auth0, user propagation based on the Authorization Code grant flow is not directly supported. To work around this limitation, you can deploy a local authorization request proxy that fetches the token and connects to your MCP server using that token.

