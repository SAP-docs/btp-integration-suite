<!-- loio40b31a0a760f42ef9e329ef881fcaa5d -->

# Create an MCP Server from an API Proxy

Create a Model Context Protocol \(MCP\) server from an existing API proxy to expose its operations as MCP tools for AI agents. Perform this task when you have an API proxy deployed on the classic API Management runtime that you want to make accessible to MCP-compatible clients.



## Prerequisites

Before you begin, ensure the following:

-   Activate API Management capability. See, [Activate and Configure the API Management Capability](activate-and-configure-the-api-management-capability-f6eb433.md).

-   Activate Integration Cell runtime. See, [Activate Integration Cell](activate-integration-cell-1a627da.md).

-   Assign the *PI\_Integration\_Developer* role collection to yourself.

-   Create a content package. See, [Creating an Integration Package](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-integration-package?version=CLOUD).

-   The API proxy you want to expose is deployed on the Classic API Management runtime.



## Context

You can create an MCP server directly from an existing API proxy deployed on the classic API Management runtime. The system uses the API proxy as the source and allows you to select which of its operations are exposed as MCP tools. The resulting MCP server provides a governed, AI-accessible endpoint for MCP-compatible clients such as AI agents.



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an MCP server artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *MCP Server*.

    The *Add MCP Server* dialog opens.

5.  In the *Select Source* step, select *API* as the source type and choose *Next*.

    This option enables you to create an MCP server from an API managed within SAP Integration Suite.

6.  In the *Provide MCP Details* step, choose the browser icon in the *Select API* field, to open the *Select an API* dialog.

7.  From the *Runtime* dropdown, select *Classic API Management*, and search for or browse the list of available API proxies, select the API proxy you want to expose, and choose *Add*.

    The dialog closes and the selected API proxy appears in the *API* field on the *Provide MCP Details* screen.

8.  Fill in the required fields on the *Provide MCP Details* screen.

    > ### Note:  
    > Only OData or REST APIs are supported as sources for an MCP server.

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
    
9.  Once all details are completed, choose *Next* to proceed to create tools.

10. In *Select Tools*, select the API resource you want to expose as MCP tools.

    Check the checkbox next to each API resource you want to include.

    > ### Note:  
    > Each MCP server supports up to 30 tools.

11. Select the operations you want to expose as MCP tools and choose *Add*.

    Only the operations you select here are discoverable and invocable by MCP-compatible clients.

    The MCP server is created and opens in edit mode, where you can review and further configure its settings.




## Results

The MCP server artifact is created from the selected API proxy and opens in edit mode. You can now configure policies and authentication settings before deploying the MCP server to make it accessible to MCP-compatible clients.



## Next Steps

After adding the MCP server, you can further configure and manage it as needed. For information, see  <?sap-ot O2O class="- topic/xref " href="49953c37362c438fbdc8d8831f000e29.xml" text="" desc="" xtrc="xref:4" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiod8a6092f89b24b5e8531d35c034be3aa_en-US/src/content/localization/en-us/40b31a0a760f42ef9e329ef881fcaa5d.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .

