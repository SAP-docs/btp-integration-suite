<!-- loioc3c81a80b354477da7bda75b1a3ee026 -->

# Consume an MCP Server Using a Technical User Token

When an AI application connects to an MCP server using a technical user, all requests are executed using the permissions associated with the technical user. To invoke the MCP server, obtain an OAuth access token using the technical user's client credentials.

Before you configure the AI application, obtain the required OAuth credentials by using one of the following methods:

-   **Using Developer Hub**: When accessing APIs or MCP servers secured with an authentication policy through the Developer Hub, the system generates a client ID and client secret. Use these credentials to obtain an OAuth token, which is required to call the API or the MCP server. For more information, see [Invoke an API or an MCP Server Artifact by Obtaining Credentials via Developer Hub](invoke-an-api-or-an-mcp-server-artifact-by-obtaining-credentials-via-developer-hub-e79810f.md).
-   **Using Process Integration Runtime**: After deploying the artifact, you can invoke the API or the MCP server endpoint using a REST client. For more information, see [Invoke an API or an MCP Server Artifact by Obtaining Credentials through Process Integration Runtime](invoke-an-api-or-an-mcp-server-artifact-by-obtaining-credentials-through-process-integrat-b63baa2.md).

