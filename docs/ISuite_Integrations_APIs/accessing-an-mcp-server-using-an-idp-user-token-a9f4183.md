<!-- loioa9f4183e6b384fffb462c47a714c1dbf -->

# Accessing an MCP Server Using an IdP User Token

Connect an agent to an MCP server using the authenticated user's identity. In this authentication model, the agent obtains an OAuth access token for the signed-in user from the identity provider \(IdP\), and requests to the MCP server are executed with that user's permissions.



## Configuration Workflow

To consume an MCP server from an agent, you must configure both the agent and the authentication mechanism used to secure the MCP server. The exact configuration steps depend on the authentication mechanism configured in the MCP server's [Authentication](authentication-fa6eec4.md) policy.

Configuring an agent to consume an MCP server involves the following steps. The subsequent sections describe each step in detail.

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

Determine whether the MCP server is secured using default Authentication \(XSUAA\) or an external identity provider. The configured authentication mechanism determines how OAuth client credentials are obtained.

</td>
<td valign="top">

-   [Configure MCP Server Access Using Default Authentication \(XSUAA\)](configure-mcp-server-access-using-default-authentication-xsuaa-dc283ab.md)
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

Generate or obtain the client ID and client secret required by the agent. The supported methods depend on the configured authentication mechanism.

</td>
<td valign="top">

-   [Configure MCP Server Access Using Default Authentication \(XSUAA\)](configure-mcp-server-access-using-default-authentication-xsuaa-dc283ab.md)
-   [Configure MCP Server Access Using an External Identity Provider](configure-mcp-server-access-using-an-external-identity-provider-fbea412.md)



</td>
</tr>
<tr>
<td valign="top">

Configure the agent

</td>
<td valign="top">

Configure the agent with the MCP server endpoint and the OAuth client credentials.

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Authenticate and connect

</td>
<td valign="top">

During the first connection, the agent prompts you to authenticate. After successful authentication, the application can discover and invoke the tools exposed by the MCP server.

</td>
<td valign="top">



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



</td>
</tr>
</table>

**Related Information**  


 <?sap-ot O2O class="- topic/link " href="49b84477bba142bd90e73e008113cbf6.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiod8a6092f89b24b5e8531d35c034be3aa_en-US/src/content/localization/en-us/a9f4183e6b384fffb462c47a714c1dbf.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

