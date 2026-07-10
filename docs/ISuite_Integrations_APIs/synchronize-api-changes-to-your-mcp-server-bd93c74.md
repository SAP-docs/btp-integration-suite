<!-- loiobd93c74534ad4d6eb3d5421d5e5211b2 -->

# Synchronize API Changes to Your MCP Server

When the source API artifact undergoes changes, such as updated endpoints, modified input/output schemas, removed resources, or authentication policy updates, you need to synchronize those changes to your MCP server definition. This ensures your MCP tools and MCP resources remain consistent with the latest API specification. The *Synchronize* option is only available for MCP servers created from an API artifact.



## Prerequisites

-   You have an MCP server created from an API artifact. See, [Create an MCP Server from an API Artifact](create-an-mcp-server-from-an-api-artifact-9f18140.md).

-   The source API artifact has been updated with changes that are not yet reflected in your MCP server definition.

-   You have the necessary permissions to edit and deploy the MCP server.


> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Open the package containing your MCP server.

4.  Select your MCP server artifact to open the overview page, choose *Edit*.

5.  Choose *Synchronize* in the upper-right corner of the screen.

    The system pulls the latest OpenAPI Specification from the source API artifact and compares it against the existing MCP server definition.

6.  Review the synchronization summary.

    The system displays the following categories of changes:


    <table>
    <tr>
    <th valign="top">

    **Category** 
    
    </th>
    <th valign="top">

    **Description** 
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Tools
    
    </td>
    <td valign="top">
    
    MCP tools that have been removed because the corresponding API resource no longer exists in the source, newly added tools based on new API resources, or existing tools with modifications to their input or output schema.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Resources
    
    </td>
    <td valign="top">
    
    MCP rsources that have been removed because the corresponding API resource no longer exists in the source.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication Policy Changes
    
    </td>
    <td valign="top">
    
    Any changes to the authentication policy of the source API that may impact how the MCP server authenticates requests to the backend.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Schema Changes
    
    </td>
    <td valign="top">
    
    Modifications to the input or output schema of API resources that are already configured as MCP Tools or MCP Resources. These changes may affect how AI agents interact with the tool or resource.
    
    </td>
    </tr>
    </table>
    
    To proceed with updating the MCP server definition with the latest OpenAPI specification, choose *Confirm*. To retain the existing changes and discard the synchronization updates, choose *Cancel*.

7.  Review each listed change carefully and choose *Confirm*.

    The MCP server definition is updated with the latest OAS and all identified changes are incorporated.

    > ### Note:  
    > Confirming the synchronization alone does not apply the updates to the MCP server configuration.

8.  Navigate to the *MCP Configuration* tab to verify that the MCP tools and MCP resources reflect the synchronized changes.

9.  After confirming the synchronization, choose *Save* or *Deploy* for the changes to take effect.




## Results

The MCP server definition is now synchronized with the latest version of the source API artifact.

