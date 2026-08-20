<!-- loio9fb76ece3f6d4bb09330bf050034756c -->

# Invoke an MCP Server from Joule Work Desktop

After deploying an MCP Server on the Integration Cell runtime, you can add and configure it to Joule Work Desktop, making its tools available to Joule for AI-assisted task execution.

> ### Note:  
> This topic references **Joule Work Desktop**, which is part of an SAP Early Adopter Care \(EAC\) program. Products or features that are part of an EAC program are not available to users outside of this program.

**Prerequisites**

-   An MCP Server created and deployed on the Integration Cell runtime in SAP Integration Suite. See, [Creating an MCP Server](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/creating-mcp-server?version=CLOUD&ai=true) and [Deploy an MCP Server](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/deploy-mcp-server?version=CLOUD&ai=true).

-   Joule Work Desktop installed on your machine. See, [Setting Up Joule Work Desktop](https://help.sap.com/docs/JOULE_WORK_DESKTOP/682b01d8809746ccaa2d9643f59bbeb1/51d19f5196b04d1f8173e2db5239b9f8.html).

-   The user is registered in the respective authorization server \(such as SAP Identity Authentication Service\). Since Joule Work Desktop triggers, a user token fetch flow when connecting to an MCP server, the connecting user must exist in the authorization server regardless of whether they hold valid credentials. See, [Accessing an MCP Server Using an IdP User Token](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/consume-mcp-server-using-idp-user-token?version=CLOUD&ai=true).


**Procedure**

To connect Joule Work Desktop to your MCP Server, follow the steps described in [Adding a Connector](https://help.sap.com/docs/JOULE_WORK_DESKTOP/3fec5cf19c7040baa71e42a88099180e/8c11ae6508de4b9ea9bea100e106ecfd.html?locale=en-US&state=PRODUCTION&version=Current&q=MCP%20server#adding-a-connector) in the Joule Work Desktop guide. When prompted, enter the *MCP server endpoint URL* exposed by your Integration Cell runtime.

> ### Note:  
> For XSUAA authentication, both *Client ID* and *Client Secret* are required. For external authentication methods such as Okta and IAS, Client ID is required while Client Secret is optional. See, [Accessing an MCP Server Using an IdP User Token](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/consume-mcp-server-using-idp-user-token?version=CLOUD&ai=true).

**Result**

The MCP server's tools are now available in Joule Work Desktop and can be invoked by Joule during conversations. For more information on how Joule Work Desktop connects to MCP servers, see the [Joule Work Desktop documentation](https://help.sap.com/docs/JOULE_WORK_DESKTOP/682b01d8809746ccaa2d9643f59bbeb1/51d19f5196b04d1f8173e2db5239b9f8.html).

