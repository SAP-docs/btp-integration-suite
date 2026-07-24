<!-- loiodd58b69c81214fa3a6ba506fd62035bd -->

# Consuming MCP Servers

Model Context Protocol \(MCP\) enables AI applications to discover and invoke tools exposed by enterprise systems through MCP servers.

After an MCP server is deployed, AI applications can connect to it to discover and invoke the tools it exposes. To securely access the MCP server, the AI application must first authenticate using the authentication mechanism configured in the Authentication policy, such as SAP BTP Authorization and Trust Management \(XSUAA\) or an external identity provider. Only after successful authentication can the AI application invoke the available tools.

You can consume MCP Servers in the following two ways:

-   **Consume an MCP server Using a Technical User Token**

    In this authentication model, the AI application accesses the MCP server by using the identity of a technical user or service account. All tool invocations are performed using the permissions assigned to the technical user, regardless of the end user interacting with the AI application.

    This model is intended for machine-to-machine communication, autonomous AI agents, background jobs, and other automated scenarios where requests don't need to be executed on behalf of an individual user. For more information, see [Consume an MCP Server Using a Technical User Token](consume-an-mcp-server-using-a-technical-user-token-c3c81a8.md).

-   **Consume an MCP Server Using an IdP User Token**

    In this authentication model, the AI application accesses the MCP server on behalf of an authenticated user. Tool invocations are authorized using the identity and permissions of the signed-in user, enabling user-specific access control and auditing.

    This model is intended for interactive AI applications, such as enterprise copilots and AI assistants, where requests must be executed using the authenticated user's identity. For more information, see [Consume an MCP Server Using an IdP User Token](consume-an-mcp-server-using-an-idp-user-token-a9f4183.md).


