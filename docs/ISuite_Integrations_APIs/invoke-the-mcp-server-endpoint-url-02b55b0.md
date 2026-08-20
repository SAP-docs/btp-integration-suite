<!-- loio02b55b0acd68448d9d7ee5b29aaa2707 -->

# Invoke the MCP Server Endpoint URL

To access a deployed MCP server, you need to invoke their endpoint URLs using supported authentication methods.

To invoke an MCP server artifact, you can obtain credentials in the following two ways:

-   **Via Developer Hub**

    When accessing MCP servers secured with an authentication policy through the Developer Hub, the system generates a client ID and client secret. Use these credentials to obtain an OAuth token, which is required to call the MCP server. For more information, see [Invoke an MCP Server Artifact by Obtaining Credentials via Developer Hub](invoke-an-mcp-server-artifact-by-obtaining-credentials-via-developer-hub-bffa481.md).

-   **Via Process Integration Runtime**

    After deploying the artifact, you can invoke the MCP server endpoint using a REST client. For more information, see [Invoke an MCP Server Artifact by Obtaining Credentials through Process Integration Runtime](invoke-an-mcp-server-artifact-by-obtaining-credentials-through-process-integration-runtim-f3c6e2e.md).

    > ### Note:  
    > Using credentials obtained via the Process Integration Runtime is considered an anti-pattern. We strongly recommend using credentials obtained through the Developer Hub instead.


