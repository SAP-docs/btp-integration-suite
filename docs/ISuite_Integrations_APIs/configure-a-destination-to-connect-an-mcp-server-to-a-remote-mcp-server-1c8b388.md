<!-- loio1c8b388024f04129a8983b3e8d4dbb07 -->

# Configure a Destination to Connect an MCP Server to a Remote MCP Server

To communicate with a remote MCP server, the MCP server in SAP Integration Suite uses a destination configured in your SAP BTP subaccount.



## Prerequisites

-   The **Subaccount Administrator** role collection should be assigned to you.
-   Obtain the URL of the remote MCP server and authentication details of the remote MCP server.

> ### Note:  
> The MCP remote server must support the Streamable HTTP transport. Only MCP servers exposed through Streamable HTTP can be proxified.



## Context

This destination holds the connection details and credentials required to authenticate and route requests to the remote MCP server.



## Procedure

1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

2.  From the left navigation pane, choose *Connectivity* \> *Destinations*.

3.  Choose *Create*. The *Create New Destination* window appears.

4.  Choose *From Scratch* to create a new destination manually.

5.  In the *Destination Details* section, enter all the required information as described in the table below:


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Provide a unique name for the destination.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Choose *HTTP* as the supported type.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Choose *Internet* as the only supported proxy type.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description \(optional\)
    
    </td>
    <td valign="top">
    
    Enter a brief description stating the purpose of creating a new destination in the *Description* field.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    Enter the URL of the remote MCP server that you want to connect to..

    Example: `"https://api.ai.intprod-eu10.eu-central-1.aws.ml.hana.ondemand.com" }`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    Enter the `url` value of the SAP AI Core system.

    For example: `https://<servername>/oauth/token`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    Select the authentication mechanism required by the remote MCP server. Depending on the authentication mechanism you select, additional fields are displayed. Enter the required authentication details.

    Select one of the supported authentication mechanisms:

    -   NoAuthentication
    -   BasicAuthentication
    -   OAuth2ClientCredentials
    -   OAuth2Password
    -   ClientCertificate


    
    </td>
    </tr>
    </table>
    
    Scroll down to the *Labels* section, choose *Add* and add the following labels:

    **Labels**


    <table>
    <tr>
    <th valign="top">

    Additional Properties
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    IntegrationCell.Include
    
    </td>
    <td valign="top">
    
    Set its value to *true*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    IntegrationCell.Provides
    
    </td>
    <td valign="top">
    
    Set its value to *mcp*.
    
    </td>
    </tr>
    </table>
    

