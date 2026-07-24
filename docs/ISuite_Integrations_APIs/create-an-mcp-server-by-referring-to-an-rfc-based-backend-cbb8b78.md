<!-- loiocbb8b78774224845b95be5b566a870c4 -->

# Create an MCP Server by Referring to an RFC-Based Backend

Create an MCP server by connecting to an RFC-based backend system and exposing selected RFC operations as MCP tools.



## Prerequisites

-   Create a content package. See, [Creating an Integration Package](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-integration-package?version=CLOUD).

-   Activate API Management capability. See, [Activate and Configure the API Management Capability](activate-and-configure-the-api-management-capability-f6eb433.md).

-   Activate Integration Cell runtime. See, [Activate Integration Cell](activate-integration-cell-1a627da.md).

-   Assign the *PI\_Integration\_Developer* role collection to yourself.

-   Create a RFC destination for discovery and execution of RFC functions. See, [Create RFC Destinations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/create-rfc-destinations?version=Cloud)

    > ### Note:  
    > Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

    > ### Note:  
    > After completing all the steps described in *Create RFC Destinations*, scroll down to the *Labels* section before choosing *Create*. Choose *Add* and add the label *IntegrationCell.Include* with the value set to *true*.

-   You've installed and configured the Cloud Connector on your operating system. For more information, see the following topics:
    -   [Installation](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/installation?version=Cloud)
    -   [Configure the Cloud Connector](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-cloud-connector?version=Cloud)

-   To discover RFCs from backend system, you need to allow the following BAPIs in the resources section of Cloud Connector:

    -   RFC\_FUNCTION\_SEARCH
    -   SWO\_QUERY\_API\_METHODS
    -   RFC\_METADATA\_GET
    -   RFC\_GET\_STRUCTURE\_DEFINITION
    -   BAPI\_TRANSACTION\_COMMIT

        > ### Note:  
        > Ensure that BAPI\_TRANSACTION\_COMMIT is exposed through the SAP Cloud Connector, as it is required for BAPI calls.

    -   BAPI\_TRANSACTION\_ROLLBACK





## Context

An MCP server can be created using an RFC-based backend to enable access to business logic implemented in SAP systems such as SAP S/4HANA or SAP ECC.

To achieve this, you:

-   Connect to a backend system using a configured destination.

-   Discover available RFC function modules.

-   Select specific RFCs and expose them as MCP tools.

-   This approach allows you to reuse existing backend functionality without building new APIs.


> ### Note:  
> MCP over RFC is available for the following SAP systems:
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> SAP Systems
> 
> </th>
> <th valign="top">
> 
> Level of Support
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> SAP ECC 6.0 \(NetWeaver 7.0 up to 7.5\)
> 
> </td>
> <td valign="top">
> 
> Fully supported
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> SAP ECC 5.0 \(NetWeaver 2004\)
> 
> </td>
> <td valign="top">
> 
> Fully supported
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> SAP S/4 HANA
> 
> </td>
> <td valign="top">
> 
> Fully Supported
> 
> </td>
> </tr>
> </table>



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an MCP server artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *MCP Server*.

    The *Create MCP Server* dialog opens.

5.  Select *RFC* as the source type and choose *Next*.

    This option enables you to create an MCP server by connecting to an RFC backend system.

6.  In the *Select Destination* step, select an RFC destination pointing to your backend system \(for example, SAP S/4HANA or ECC\), and choose *Next*.

7.  In the *Select Tools* step, use the search field to find RFCs.

    Select one or more RFC functions to include as MCP tools and choose *Next*.

    > ### Note:  
    > The maximum number of tools allowed for RFC is 15.

8.  In the *Provide MCP Details* step, enter the required information:


    <table>
    <tr>
    <th valign="top">

    API Details
    
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
    
    APIs are identified by their IDs on the home screen. You can use space and special characters in an ID.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    MCP Path
    
    </td>
    <td valign="top">
    
    Enter the path prefix for the MCP server. For example, `/SFlight`.

    > ### Note:  
    > The base path shouldn't be left empty or set to only "/".


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Version
    
    </td>
    <td valign="top">
    
    Add a version if you want to improve, upgrade, or customize the functional behavior of an existing MCP server. Versioning allows the creation and management of multiple concurrent versions of an API.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Runtime Profile
    
    </td>
    <td valign="top">
    
    The runtime node on which the MCP server will be deployed.
    
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
    
9.  Choose *Create*.


