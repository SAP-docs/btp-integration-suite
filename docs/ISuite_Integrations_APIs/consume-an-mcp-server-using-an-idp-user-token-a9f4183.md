<!-- loioa9f4183e6b384fffb462c47a714c1dbf -->

# Consume an MCP Server Using an IdP User Token

Connect an AI application to an MCP server using the authenticated user's identity. In this authentication model, the AI application obtains an OAuth access token for the signed-in user from the identity provider \(IdP\), and requests to the MCP server are executed with that user's permissions.



## Configuration Workflow

To consume an MCP server from an AI application, you must configure both the AI application and the authentication mechanism used to secure the MCP server. The exact configuration steps depend on the authentication mechanism configured in the MCP server's [Authentication](authentication-fa6eec4.md) policy.

Configuring an AI application to consume an MCP server involves the following steps. The subsequent sections describe each step in detail.

****


<table>
<tr>
<th valign="top">

 

</th>
<th valign="top">

Description

</th>
<th valign="top">

See

</th>
</tr>
<tr>
<td valign="top">

Identify the authentication mechanism

</td>
<td valign="top">

Determine whether the MCP server is secured using Internal Authentication \(XSUAA\) or an external identity provider. The configured authentication mechanism determines how OAuth client credentials are obtained.

</td>
<td valign="top">

-   [Configure MCP Server Access Using Internal Authentication \(XSUAA\)](configure-mcp-server-access-using-internal-authentication-xsuaa-dc283ab.md)
-   [Configure MCP Server Access Using an External Identity Provider](configure-mcp-server-access-using-an-external-identity-provider-fbea412.md)



</td>
</tr>
<tr>
<td valign="top">

Verify the prerequisites

</td>
<td valign="top">

Ensure that your user account, roles, and application permissions are configured according to the selected authentication mechanism.

</td>
<td valign="top">

Prerequisites \(under the selected authentication mechanism\)

</td>
</tr>
<tr>
<td valign="top">

Obtain OAuth client credentials

</td>
<td valign="top">

Generate or obtain the client ID and client secret required by the AI application. The supported methods depend on the configured authentication mechanism.

</td>
<td valign="top">

-   [Configure MCP Server Access Using Internal Authentication \(XSUAA\)](configure-mcp-server-access-using-internal-authentication-xsuaa-dc283ab.md)
-   [Configure MCP Server Access Using an External Identity Provider](configure-mcp-server-access-using-an-external-identity-provider-fbea412.md)



</td>
</tr>
<tr>
<td valign="top">

Configure the AI application

</td>
<td valign="top">

Configure the AI application with the MCP server endpoint and the OAuth client credentials.

</td>
<td valign="top">

[Establish the Connection Between the AI Application and the MCP Server](establish-the-connection-between-the-ai-application-and-the-mcp-server-49b8447.md) 

</td>
</tr>
<tr>
<td valign="top">

Authenticate and connect

</td>
<td valign="top">

During the first connection, the AI application prompts you to authenticate. After successful authentication, the application can discover and invoke the tools exposed by the MCP server.

</td>
<td valign="top">

[Establish the Connection Between the AI Application and the MCP Server](establish-the-connection-between-the-ai-application-and-the-mcp-server-49b8447.md) 

</td>
</tr>
<tr>
<td valign="top">

Review known limitations

</td>
<td valign="top">

Some identity providers require additional configuration because of differences in OAuth implementation.

</td>
<td valign="top">

[Establish the Connection Between the AI Application and the MCP Server](establish-the-connection-between-the-ai-application-and-the-mcp-server-49b8447.md) 

</td>
</tr>
</table>

**Related Information**  


[Establish the Connection Between the AI Application and the MCP Server](establish-the-connection-between-the-ai-application-and-the-mcp-server-49b8447.md "After obtaining the required OAuth client credentials, configure your AI application to connect to the MCP server. The exact procedure depends on the AI application. For example, in Claude Desktop, you add the MCP server as a connector and provide the required connection details.")

