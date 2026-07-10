<!-- loio9db32d01c7df41bc8a8bdd088f1d98e5 -->

# Discover and Publish MCP Servers from SAP Integration Suite

As an admin, you can publish MCP \(Model Context Protocol\) servers from SAP Integration Suite business systems by bundling them into products.



## Context

Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Flaunchpad.support.sap.com%2F%23%2Fnotes%2F2903776).

To make these MCP servers available for consumption, they must be bundled into products with descriptive metadata and published to the Developer Hub catalog.

MCP servers within SAP Integration Suite business systems expose capabilities such as creating sales orders, managing accounting activities, or performing availability checks. To make these MCP servers discoverable and consumable by developers and AI agents through the Developer Hub catalog, you must bundle them into a product and publish it.



## Procedure

1.  Log in to *Developer Hub*.

2.  Navigate to the *Admin Center* \> *Manage* \> *Content*.

    A list of all business systems is displayed.

3.  Select *Integration Suite* business system to discover the MCP servers within that business system:

4.  Choose the *MCP Servers* tab.

    A list of all MCP servers within the business system is displayed.

5.  Select the MCP server and then choose *Create Product*.

    `The` *Create Product* dialog opens.

    Provide all required product information:

    -   Name\*: Enter a user-friendly product name \(e.g., Sales Order Integration\).

    -   ID\*: Enter a unique identifier using a consistent format \(e.g., Sales\_Order\_Integration\).

    -   Short Description: Add a concise summary of the product.

    -   Description: Use the rich text editor to add a detailed explanation, including purpose, key capabilities, and systems involved.


6.  Verify the *Selected MCP Servers* listed at the bottom.

    Remove any server by clicking the *x* if needed.

7.  Choose *Save as Draft* to save without publishing, or choose *Publish* to make the product available on Developer Hub; use *Cancel* to discard your changes.

    Once a product containing MCP servers is published, it becomes available in the Developer Hub catalog for consumption. To consume the MCP servers, see [Subscribe to Products to Make MCP Servers Agent-Ready](subscribe-to-products-to-make-mcp-servers-agent-ready-2df6934.md). Once subscribed, AI agents can connect to the MCP servers and leverage their exposed tools and capabilities to perform intelligent, tool-based interactions such as creating sales orders, running availability checks, or managing business processes.


