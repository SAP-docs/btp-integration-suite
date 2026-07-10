<!-- loiodd401ec8e7bc48e595243c9aa9ffb746 -->

# Virtual Hosts in Integration Cell

Virtual hosts enable you to expose API and MCP server artifacts through dedicated host names under the default domain provided by SAP. Using multiple virtual hosts helps organize these artifacts across environments and tenants, while providing improved routing and host name isolation.

As an API administrator with the *PI\_Administrator* role collection assigned, you can configure and manage virtual hosts for your Integration Cell runtime.

-   **Deploy API and MCP Server Artifacts to a Virtual Host**- When creating or deploying an API or an MCP server, you can choose the virtual host where it should be exposed.
-   **New API and MCP Server Artifacts**- For new artifacts, the default virtual host is automatically selected during creation.
-   **Existing API and MCP Server Artifacts**- For existing artifacts, the currently assigned virtual host is displayed:

    -   In the *Overview* section during edit
    -   During deployment actions

    Only one virtual host can be assigned to an API or an MCP server artifact at a time.

-   **Routing Behavior**- Incoming requests are routed to the appropriate endpoint based on the `Host` header associated with the configured virtual host.

    > ### Note:  
    > If a request is received for an unassigned virtual host, Integration Cell returns a configurable `4xx` response. By default, the response code is `404`.




## Supported Tasks

You can perform the following virtual host management tasks:

-   [Configuring Additional Virtual Host](configuring-additional-virtual-host-26c7416.md)
-   [View and Edit Virtual Host for API Artifacts](view-and-edit-virtual-host-for-api-artifacts-a87d799.md) 
-   [Delete an Eligible Virtual Host](delete-an-eligible-virtual-host-102257d.md) 
-   Assign virtual hosts to APIs. See,[Create an API Artifact Using a Target URL or an OpenAPI Specification](create-an-api-artifact-using-a-target-url-or-an-openapi-specification-914f57e.md).
-   View virtual host deployment details and status.

