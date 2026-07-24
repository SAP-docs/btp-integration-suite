<!-- loiob59f141932664893921fc3c34974e800 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create an MCP Server from an HTTP Endpoint

Create an MCP Server from any HTTP endpoint by providing its OpenAPI specification. This enables you to connect and expose REST-based services as MCP tools for AI-driven consumption.



## Prerequisites

-   Activate API Management capability. See, [Activate and Configure the API Management Capability](activate-and-configure-the-api-management-capability-f6eb433.md).

-   Activate Integration Cell runtime. See, [Activate Integration Cell](activate-integration-cell-1a627da.md).

-   Assign the *PI\_Integration\_Developer* role collection to yourself.

-   Create a content package. See, [Creating an Integration Package](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-integration-package?version=CLOUD).

-   Set up a destination in SAP BTP Cockpit. To set up a HTTP destination from scratch, navigate to *Connectivity* \> *Destinations* from the side navigation pane, and follow the step-by-step instructions in [Create HTTP Destinations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/create-http-destinations?version=Cloud). Also, ensure that you scroll to the *Labels* section \(below Additional Properties\) and add the label*IntegrationCell.Include* and set its value to *true*.

    > ### Note:  
    > Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).




## Context

This topic explains how to create an MCP server by connecting to an external HTTP endpoint using its OpenAPI specification. It guides you through configuring the required details, choosing between generating or uploading an API specification, and selecting API resources to expose as MCP tools. By following this process, you can make REST-based services available for AI-driven interactions within SAP Integration Suite.

> ### Note:  
> The OpenAPI specification must be a version between 3.0.0 and 3.0.3. Swagger 2.0 and earlier versions are not supported.



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *MCP Server*.

    The *Create MCP Server* dialog opens.

5.  Select *HTTP Endpoint with OpenAPI Specification* as the source type and choose *Next*.

    This option will enable you to create an MCP server from any HTTP endpoint by providing the URL and importing the OpenAPI Specification.

6.  In the *Provide MCP Details* step, choose either *Create* or *Upload* and provide the MCP details:

    -   *Create*: Define the MCP server by selecting a source type, either *URL* or *Destination*, and provide the corresponding MCP details. For more information, see [MCP Details](create-an-mcp-server-from-an-http-endpoint-b59f141.md#loiob59f141932664893921fc3c34974e800__MCP_Details) table.

        > ### Note:  
        > After you provide the MCP details, the subsequent steps depend on whether the *OpenAPI Specification Generator* is enabled in *Settings* \> *Artificial Intelligence*.
        > 
        > > ### Note:  
        > > AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through September 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).
        > 
        > > ### Note:  
        > > Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).
        > 
        > -   If the OpenAPI Specification Generator is enabled, the *Next* button is displayed in the *Provide MCP Details* step, which takes you to step 3 *Generate API Specification*.
        > 
        >     In the *Generate API Specification* step:
        > 
        >     -   You can choose to skip generating an OpenAPI specification and directly choose *Create* to create the MCP server.
        >     -   If you generate an OpenAPI specification using AI, choose *Next* to proceed to step 4 *Create Tools*.
        > 
        > -   If the *OpenAPI Specification Generator* is not enabled, the *Create* button is available directly in the *Provide MCP Details* step.
        > 
        >     You can create the MCP server immediately without any additional steps.
        > 
        > 
        > In the *Create Tools* step:
        > 
        > -   Select the API resources that you want to expose as MCP tools.
        > 
        >     > ### Note:  
        >     > Each MCP server supports up to 15 tools.
        > 
        > -   Choose *Create* to finalize the MCP server. If resources are not available, then you can skip this step and choose *Create*.

    -   *Upload*: Upload an API specification file in JSON format.

        > ### Note:  
        > The OpenAPI specification must be a version between 3.0.0 and 3.0.3. Swagger 2.0 and earlier versions are not supported.

        After uploading, select the source type \(*URL* or *Destination*\) and provide the details. For more information, see [MCP Details](create-an-mcp-server-from-an-http-endpoint-b59f141.md#loiob59f141932664893921fc3c34974e800__MCP_Details) table.

        Now fill in all the required details, and choose *Next* to proceed to the *Create Tools* step, where you can select the API resources to expose as MCP tools. Then choose *Create* to finalize the MCP server.


    **MCP Details**


    <table>
    <tr>
    <th valign="top">

    MCP Details for Source Type: URL
    
    </th>
    <th valign="top">

    MCP Details for Source Type: Destination
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Under*Source Type*, select *URL*, enter the following details and choose *Next*:

    -   *URL*: Enter the target HTTPS endpoint URL of the MCP server. For example, `https://www.sap.com`

    -   *Name*: Enter an intuitive name. Use only alphanumeric characters and special character such as underscore "\_".

    -   *ID*: APIs are identified by their IDs on the home screen. You can use space and special characters in an ID.

    -   *MCP Path*: Enter the path prefix for the MCP server. This defines the proxified endpoint under which the MCP server is exposed. For example, /BusinessPartner or BusinessPartner.

        > ### Note:  
        > The base path shouldn't be left empty or set to only "/".

    -   *Runtime Profile*: The runtime node on which the MCP server will be deployed.

    -   *Virtual Host*:

        You can view the Virtual Host URL for the selected runtime profile. It defines the public-facing hostname, which is combined with the base path to expose your MCP server.

        For example, even if your backend service is hosted at https://internal.services.local/orders, you can expose it externally as https://mcpserver.yourdomain.com/v1/orders using a virtual host.



    
    </td>
    <td valign="top">
    
    Under*Source Type*, select *Destination*, enter the following details and choose *Next*:

    -   *Destination*: Choose the <span class="SAP-icons-V5"></span> icon to open the *Select Destination* dialog. Select the destination, and choose *Add*.

        A destination typically contains a base URL \(for example, https://api.example.com\)

        > ### Note:  
        > If the API specification includes a destination that is not available in the subaccount, you can select a different destination in the Select Destination dialog.

    -   *Relative URL*: The Relative URL defines the specific resource path that is appended to the base URL of the selected destination. For example,`/salesorder`. Final endpoint:`https://api.example.com + /salesorder`

    -   *Name*: Enter an intuitive name. Use only alphanumeric characters and special character such as underscore "\_".

    -   *ID*: APIs are identified by their IDs on the home screen. You can use space and special characters in an ID.

    -   *MCP Path*: Enter the path prefix for the MCP server. This defines the proxified endpoint under which the MCP server is exposed. For example, /BusinessPartner or BusinessPartner.

        > ### Note:  
        > The base path shouldn't be left empty or set to only "/".

    -   *Runtime Profile*: The runtime node on which the MCP server will be deployed.

    -   *Virtual Host*: You can view the Virtual Host URL for the selected runtime profile. It defines the public-facing hostname, which is combined with the base path to expose your MCP server.

        For example, even if your backend service is hosted at https://internal.services.local/orders, you can expose it externally as https://mcpserver.yourdomain.com/v1/orders using a virtual host.



    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Only destinations with the *Proxy Type* set to `Internet` or `OnPremise` are currently supported.
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
    > -   ClientCertificateAuthentication
    > 
    > -   OAuth2ClientCredentials
    > 
    > -   NoAuthentication
    > 
    > -   BasicAuthentication
    > 
    > -   OAuth2Password
    > 
    > -   OAuth2JWTBearer
    > 
    > -   SAMLAssertion
    > 
    > 
    > 
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > OnPremise
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
    > -   OAuth2Password
    > 
    > -   OAuth2JWTBearer
    > 
    > -   SAMLAssertion
    > 
    > 
    > 
    > 
    > </td>
    > </tr>
    > </table>

7.  After selecting the required API resources and choosing *Create*, the MCP server is created and opens in the editor view.

    Choose *Edit* to update the configuration \(all fields except ID\). Use the *MCP Configuration* tab to modify *Source*, *Tools*, *Resources*, and *Prompts*, and the *Policies* tab to configure traffic management and security policies. For detailed information, see [Configure an MCP Server Created from an HTTP Endpoint](configure-an-mcp-server-created-from-an-http-endpoint-f58f7b0.md).


