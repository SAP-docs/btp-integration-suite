<!-- loio742216d01dfd4c58ab22090068216638 -->

# Create an MCP Server Using a Remote MCP Server as the Source

Create an MCP server using a remote MCP server as the source type to selectively expose, govern, and standardize access to its tools, resources, and prompts for AI agent consumption.



## Prerequisites

-   Create a content package. See, [Creating an Integration Package](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-integration-package?version=CLOUD).

-   Activate API Management capability. See, [Activate and Configure the API Management Capability](activate-and-configure-the-api-management-capability-f6eb433.md).

-   Activate Integration Cell runtime. See, [Activate Integration Cell](activate-integration-cell-1a627da.md).

-   Assign the *PI\_Integration\_Developer* role collection to yourself.

-   Set up a destination in SAP BTP Cockpit. To set up a HTTP destination from scratch, navigate to *Connectivity* \> *Destinations* from the side navigation pane, and follow the step-by-step instructions in [Create HTTP Destinations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/create-http-destinations?version=Cloud). Also, ensure that you scroll to the *Labels* section \(below Additional Properties\) and add the label*MCP usage* and set its value to *true*.

    > ### Note:  
    > Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

    > ### Note:  
    > Only destinations with the *Proxy Type* set to `Internet` is currently supported.
    > 
    > The following authentication mechanisms are supported:
    > 
    > 
    > <table>
    > <tr>
    > <th valign="top">
    > 
    > Proxy Type
    > 
    > </th>
    > <th valign="top">
    > 
    > Authentication Mechanism
    > 
    > </th>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Internet
    > 
    > </td>
    > <td valign="top">
    > 
    > -   OAuth2ClientCredentials
    > 
    > -   NoAuthentication
    > 
    > -   BasicAuthentication
    > 
    > 
    > 
    > 
    > </td>
    > </tr>
    > </table>




## Context

Integration Developers can discover remote server offerings via a destination, synchronize tool catalog on demand, and selectively expose only the required tools, resources, and prompts for AI agent consumption. By applying security and traffic management policies at the proxy layer, SAP Integration Suite acts as the managed proxy and governance layer, providing a single, unified endpoint for agents while leveraging existing MCP implementations.



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *MCP Server*.

    The *Create MCP Server* dialog opens.

5.  Select *Remote MCP Server* as the source type and choose *Next*.

    This option will enable you to create an MCP server from a remote or a third-party MCP server.

6.  Select a destination pointing to a remote MCP server.

    Verify the following and choose *Next*

    -   **Name**: Destination identifier
    -   **URL**: Remote MCP server endpoint
    -   **Authentication**: OAuth2 / Basic / None

7.  
