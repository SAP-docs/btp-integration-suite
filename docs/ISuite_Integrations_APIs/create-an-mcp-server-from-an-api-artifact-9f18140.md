<!-- loio9f1814023b1843ab8679df58079b0ef1 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create an MCP Server from an API Artifact

Create an MCP Server from an existing API artifact deployed on Integration Cell in SAP Integration Suite. This allows you to expose deployed integration APIs as tools that AI agents and AI clients can discover and invoke.



## Prerequisites

-   Activate API Management capability. See, [Activate and Configure the API Management Capability](activate-and-configure-the-api-management-capability-f6eb433.md).

-   Activate Integration Cell runtime. See, [Activate Integration Cell](activate-integration-cell-1a627da.md).

-   Assign the *PI\_Integration\_Developer* role collection to yourself.

-   Create a content package. See, [Creating an Integration Package](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-integration-package?version=CLOUD).


> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> -   Only OData and REST API artifacts deployed on the Integration Cell runtime can be discovered and exposed as an MCP server.
> 
> -   The OpenAPI specification must be a version between 3.0.0 and 3.0.3. Swagger 2.0 and earlier versions are not supported.
> 
> -   Only APIs with OAuth-based authentication can be used to create an MCP server.



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an MCP server artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *MCP Server*.

    The *Create MCP Server* dialog opens.

5.  Select *API* as the source type and choose *Next*.

    This option enables you to create an MCP server from an API artifact deployed on Integration Cell.

6.  In the *Provide MCP Details* step, select the <span class="SAP-icons-V5"></span> icon next to the *API* field.

    The *Select an API* dialog opens, showing all available APIs organized by package. Search for the managed API from the list, and choose*Add*.

    Fill in all the required details as follows:


    <table>
    <tr>
    <th valign="top">

    MCP Server Details
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Enter an intuitive name. Use only alphanumeric characters and special character such as underscore "\_".
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ID
    
    </td>
    <td valign="top">
    
    APIs are identified by their IDs on the home screen. You can use space and special characters such as underscore\(\_\), period\(.\), hyphen\(-\) in an ID.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    MCP Path
    
    </td>
    <td valign="top">
    
    Enter the path prefix for the MCP server. For example, `/BusinessPartner or BusinessPartner`. This defines the proxified endpoint under which the MCP server is exposed.

    > ### Note:  
    > The base path shouldn't be left empty or set to only "/".


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Version
    
    </td>
    <td valign="top">
    
    Add a version if you want to improve, upgrade, or customize the functional behavior of an existing MCP server. Versioning allows the creation and management of multiple concurrent versions of an MCP server.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Runtime Profile
    
    </td>
    <td valign="top">
    
    The runtime node on which the MCP server will be deployed.

    > ### Note:  
    > The MCP server can be only deployed and managed over Integration Cell runtime profile.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Virtual Host
    
    </td>
    <td valign="top">
    
    You can view the *Virtual Host URL* for the selected runtime profile. The virtual host defines the public-facing hostname, which is combined with the base path to expose your MCP server.

    For example, even if your backend service is hosted at `https://internal.services.local/orders`, you can expose it externally as `https://mcpserver.yourdomain.com/v1/orders` using a virtual host.

    This helps in the proxification of the internal URL, improving security and allowing for more flexible deployment configurations.
    
    </td>
    </tr>
    </table>
    
    Once all details are completed, choose *Next* to proceed to create tools.

7.  In *Create Tools*, select the API resource you want to expose as MCP tools.

    Check the checkbox next to each API resource you want to include.

    > ### Note:  
    > Each MCP server supports up to 15 tools.

8.  Choose *Add* to finalize and create the MCP server.

9.  After selecting the required API resources and choosing *Create*, the MCP server is created and opens in the editor view.

    Choose *Edit* to update the configuration \(all fields except ID\). Use the *MCP Configuration* tab to modify *Source*, *Tools*, *Resources*, and *Prompts*, and the *Policies* tab to configure traffic management and security policies. For detailed information, see [Govern and Manage an MCP Server Created from an API Artifact](govern-and-manage-an-mcp-server-created-from-an-api-artifact-81b30d1.md).


