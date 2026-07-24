<!-- loiofbea412ed7d14afcae5ecc5ba7f25687 -->

# Configure MCP Server Access Using an External Identity Provider

If the MCP server is secured using an external identity provider, authentication is managed outside SAP Integration Suite. The OAuth client application must be registered with the external identity provider before the AI application can connect.

Supported identity providers include SAP Cloud Identity Services \(IAS\), Okta, Auth0, and Microsoft Entra ID.



## Prerequisites

Ensure that:

-   Your user exists in the external identity provider \(such as IAS or Okta\).
-   Your user is assigned to the registered OAuth application.
-   Any required scopes or application permissions are configured.



## Register an OAuth Application

Create an OAuth application in your externally configured IdP.

While creating a new OAuth application, add the following details:

-   OAuth grant type: **Authorization Code**
-   Register the redirect URI of the AI application by adding your AI Application's redirect URI as an allowed callback URI. As an example, for Claude Desktop, the following needs to be added:

    Application: `Claude.ai`

    Redirect URI: `https://claude.ai/api/mcp/auth_callback`

-   Configure any OAuth scopes required by the MCP server's Authorization policy. For more information on the MCP server's OAuth Scope, see [Authorization](authorization-6658409.md) policy.
-   Ensure that the user is authorized to access the application.

For example, Claude Desktop uses the following redirect URI:

AI Application: `Claude Desktop`

Redirect URI: `https://claude.ai/api/mcp/auth_callback`

After the application is created, note the generated client ID and client secret. These credentials are required when configuring the AI application.



## Configure PKCE \(Optional\)

Some IdPs support **Proof Key for Code Exchange \(PKCE\)** for public clients.

When PKCE is enabled, the AI application authenticates using a code verifier and code challenge instead of a client secret.

If your identity provider supports PKCE, and you want to enforce PKCE, configure the OAuth application as described above.

For example:

-   In **SAP Cloud Identity Services \(IAS\)**, configure the application as a public client and enable PKCE.
-   In **Okta**, configure the application as a Native or SPA application, enable PKCE, and disable the client secret requirement.

When PKCE is enabled, the client secret is not required when configuring and connecting to your MCP server from the AI application.

After obtaining the required OAuth credentials, configure the AI application to connect to the MCP server. See, [Establish the Connection Between the AI Application and the MCP Server](establish-the-connection-between-the-ai-application-and-the-mcp-server-49b8447.md).

