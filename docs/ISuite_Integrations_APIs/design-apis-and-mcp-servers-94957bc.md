<!-- loio94957bc87247462ebdfd65e72512122a -->

# Design APIs and MCP Servers

SAP Integration Suite enables you to design and manage API artifacts and MCP Server artifacts as part of your integration landscape.

-   **API artifacts** allow you to expose backend services through managed API endpoints with built-in security, traffic management, and lifecycle governance.
-   **MCP server artifacts** enable you to expose enterprise capabilities and data through the Model Context Protocol \(MCP\), making them accessible to AI-powered applications and agents.

    > ### Note:  
    > Availability of the MCP Server depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).


From the *Design* page, you can either select an existing content package or create a new one. SAP Integration Suite allows you to assemble integration contents into packages so that integration developers can use these packages in their integration scenarios. See, [Creating an Integration Package](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-integration-package?version=CLOUD).

Within an integration package, you can create API artifacts and MCP Server artifacts and define their behavior by configuring resources, endpoints, and policies.



## Supported Runtimes

1.  *Integration Cell* is a managed, cloud-native runtime for deploying and running APIs and MCP Servers on SAP-managed infrastructure.
2.  *Edge Integration Cell* is a customer-managed, cloud-native runtime for deploying and running APIs in private cloud or on-premise environments.



## Deployment Support

-   *API artifacts* can be deployed to either the *Integration Cell* runtime or *Edge Integration Cell* runtime.
-   *MCP server artifacts* can be deployed to the *Integration Cell* runtime.

Both runtimes provide a consistent API management experience with support for secure execution, traffic management, and lifecycle governance while allowing you to choose the deployment model that best fits your architectural and operational requirements.

