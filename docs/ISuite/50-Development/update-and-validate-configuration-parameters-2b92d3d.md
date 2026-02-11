<!-- loio2b92d3d53f5048268a0ef952992ea8b7 -->

# Update and Validate Configuration Parameters

Update and validate configuration parameters of an integration flow.

1.  Update configuration parameters of the integration flow via an OData API, perform the below call:

    ****


    <table>
    <tr>
    <th valign="top">

    Method
    
    </th>
    <th valign="top">

    Resource Path
    
    </th>
    <th valign="top">

    Purpose
    
    </th>
    <th valign="top">

    Response Status
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    GET
    
    </td>
    <td valign="top">
    
    `api/v1 /IntegrationDesigntimeArtifacts(Id='{Id}',Version='{Version}')/Configurations` 
    
    </td>
    <td valign="top">
    
    Get configurations of an integration flow by Id and version.
    
    </td>
    <td valign="top">
    
    -   200: Retrieved entity

        > ### Example:  
        > Collection of Configuration for IntegrationDesigntimeArtifact
        > 
        > > ### Sample Code:  
        > > ```
        > > {
        > > d	{...}
        > > }
        > > ```

    -   400: Bad Request. Wrong format or structure of the provided request body or parameters.

    -   401: Unauthorized. Authorization information is missing or invalid.

    -   403: Forbidden. The required permissions to access the resource are missing.

    -   404: Not found. The requested resource could not be found.

    -   429: Too many requests. Server’s rate limit exceeded.

    -   default: Error

        > ### Example:  
        > odata.error
        > 
        > > ### Sample Code:  
        > > ```
        > > {
        > > error*	odata.error.main{...}
        > > }
        > > ```



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    GET
    
    </td>
    <td valign="top">
    
    `api/v1 /IntegrationDesigntimeArtifacts(Id='{Id}',Version='{Version}')/Configurations/$count` 
    
    </td>
    <td valign="top">
    
    Get number of configuration parameters.
    
    </td>
    <td valign="top">
    
    -   200: Number of retrieved configuration parameters for an integration flow.

    -   400: Bad Request. Wrong format or structure of the provided request body or parameters.

    -   401: Unauthorized. Authorization information is missing or invalid.

    -   403: Forbidden. The required permissions to access the resource are missing.

    -   404: Not found. The requested resource could not be found.

    -   429: Too many requests. Server’s rate limit exceeded.

    -   default: Error

        > ### Example:  
        > odata.error
        > 
        > > ### Sample Code:  
        > > ```
        > > {
        > > error*	odata.error.main{...}
        > > }
        > > ```



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    PUT
    
    </td>
    <td valign="top">
    
    `api/v1/ IntegrationDesigntimeArtifacts (Id='{Id}',Version='{Version}')/$links/Configurations('parameterKey’)` 
    
    </td>
    <td valign="top">
    
    Updates configuration parameter value
    
    </td>
    <td valign="top">
    
    202
    
    </td>
    </tr>
    </table>
    
2.  Once, all the configuration parameters are updated, validate the integration flow along with the configuration parameters via an OData API, perform the below call::

    ****


    <table>
    <tr>
    <th valign="top">

    Method
    
    </th>
    <th valign="top">

    Resource Path
    
    </th>
    <th valign="top">

    Purpose
    
    </th>
    <th valign="top">

    Response Status
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    POST
    
    </td>
    <td valign="top">
    
    `api/v1/ ValidateIntegrationDesigntimeArtifact?Id='{Id}'&Version='{Version}'` 
    
    </td>
    <td valign="top">
    
    Perform validation checks and return results
    
    </td>
    <td valign="top">
    
    -   202

        -   Passed: Checkexecutionresult: Passed
        -   Failed: Checkexecutionresult: Failed + detailed error list

            > ### Example:  
            > > ### Sample Code:  
            > > ```
            > > Checkexecutionresult: Failed[ {
            > > "severity": "Error",
            > > "message": "The address field must begin with '/' and can include alphanumeric values, and other special characters such as '_','.','-','$','~','' and '/'. For example, '/test/123' or '/test/'.",
            > > "sourceObject":"ComponentMetadataEditor/etype:MessageFlow/eid:MessageFlow_8/pid:urlPath/location:HTTPS/attrid:urlPath",
            > > "resourcePath": "src/main/resources/scenarioflows/integrationflow",
            > > "resourceName": "iflw1.iflw" }
            > > ]
            > > ```


    -   404

        > ### Example:  
        > > ### Sample Code:  
        > > ```
        > > {
        > > 
        > > "error": {
        > > 
        > > "code": "Not Found",
        > > 
        > > "message": {
        > > 
        > > "lang": "en",
        > > 
        > > "value": "Integration design time artifact not found."
        > > 
        > > }
        > > 
        > > }
        > > 
        > > }
        > > ```

    -   400



    
    </td>
    </tr>
    </table>
    

