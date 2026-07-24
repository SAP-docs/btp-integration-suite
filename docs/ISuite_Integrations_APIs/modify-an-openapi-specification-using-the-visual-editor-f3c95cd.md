<!-- loiof3c95cdefa9744ec8d1745401a4b2cdb -->

# Modify an OpenAPI Specification Using the Visual Editor

The OpenAPI Specification visual editor provides an interactive interface to easily update and extend API objects, such as resources and schemas, for existing APIs.

Use this tool to efficiently manage and modify your API definitions without manual coding.



## Prerequisites

You have existing APIs that need to be updated. See [Creating an API Artifact](creating-an-api-artifact-c2fe62c.md).



## Procedure

1.  Go to *Design* \> *Integrations and APIs* and search for the API package you want to update.
2.  Go to the *Artifacts* tab and select the API you want to update. Choose *Switch to API Specification* \> *Edit* \> *Editor* to make your updates using the visual editor.

You can add and update the following API objects using the visual editor:

-   Resources
    -   Parameters
    -   Request Body
    -   Response Body
    -   Response Headers

-   Components
    -   Schemas
    -   Responses
    -   Headers
    -   Request Bodies
    -   Parameters


> ### Note:  
> For OpenAPI 2.X specifications, definitions like schemas, responses, request bodies, and parameters are located in the *Components* tab.



## Resources

You can update an existing resource by searching and selecting it under *Resources* or add a new one as follows:

1.  Go to *Resources* and choose *Add* to add a new resource for your API.
2.  Fill in the following information:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Input
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Tag
    
    </td>
    <td valign="top">
    
    Select *Existing* and choose the relevant tag if you want to add this resource to an existing tag.

    Select *New* and enter the name of the tag if you want to create a new tag for your API. The name must be unique in the list of tags.
    
    </td>
    <td valign="top">
    
    You can define tags to group related operations by logical categories rather than just by resources.

    This helps the API consumer to easily identify the operations that provide a certain functionality, thus improving the usability of the API documentation.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Path Prefix
    
    </td>
    <td valign="top">
    
    Enter the path for your resource. For example, `/BusinessPartners`.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Operation
    
    </td>
    <td valign="top">
    
    Choose the operations you need for this resource and delete the rest.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    In the text box below the *Operation*, write an explanation of what the operation does, and its usage specifics, if any.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    
3.  Choose *Save*.

Now you can add parameters, a request header \(if needed\), a response header, and a response body to your resource.



### Parameters

You can add or update existing request parameters or request headers for a specific resource by searching and selecting it under *Parameters* or add a new one as follows:

1.  Go to *Resources* and select the resource you want to add a new parameter to.
2.  Go to *Parameters* and choose *Add*. Select *newParameter* from the list of parameters.
3.  In the *Edit* pane, fill in the following information:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Input
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Key
    
    </td>
    <td valign="top">
    
    Enter the name of the parameter.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Required
    
    </td>
    <td valign="top">
    
    Select *Required* if the parameter is mandatory for the request.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Parameter
    
    </td>
    <td valign="top">
    
    Select the parameter type, such as *query* or *path*.
    
    </td>
    <td valign="top">
    
    To add a header parameter, select *header*.
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="3">
    
    Data Type
    
    </td>
    <td valign="top">
    
    Basic
    
    </td>
    <td valign="top">
    
    Select the data type, such as *string*, *boolean,* and so forth.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Component
    
    </td>
    <td valign="top">
    
    Select a parameter from the available common components. This will add a reference to the selected parameter in the OpenAPI specification.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Operator
    
    </td>
    <td valign="top">
    
    Add multiple components and define how they are combined by selecting one of the following operator types:

    -   *allOf*
    -   *oneOf*
    -   *anyOf*
    -   *not*

    > ### Note:  
    > This is only supported for OpenAPI Specification 3.x.x and higher.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Enter the parameter description.
    
    </td>
    <td valign="top">
    
    Depending on the parameter type, enter a short noun phrase or begin with a verb describing the parameter in the description field. If applicable, describe usage specifics, for example, for different values.

    Example:

    Determines whether users are allowed to edit the count for this attendee type.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Default
    
    </td>
    <td valign="top">
    
    Enter a default value if your parameter is optional. This varies based on the data type.
    
    </td>
    <td valign="top">
    
    For example:

    -   String - any constant value
    -   Boolean - `true` or `false`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Max Length
    
    </td>
    <td valign="top">
    
    Enter the maximum length for a string.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    



### Response Header

You can update existing response headers by searching and selecting it under *Response Header*.

Add response headers whenever your API must provide additional information outside of the main response body. For example, rate limiting, pagination or caching.

Fill in the following information for a *Response Header*:


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Input

</th>
<th valign="top">

 

</th>
</tr>
<tr>
<td valign="top">

Key

</td>
<td valign="top">

Enter the name of the response header.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Required

</td>
<td valign="top">

Select *Required* if this header is mandatory in the response header for a specific response code.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Data Type

</td>
<td valign="top">

Basic

</td>
<td valign="top">

Select the data type, such as string, boolean, and so forth.

</td>
</tr>
<tr>
<td valign="top">

Component

</td>
<td valign="top">

Select a parameter from the available common components. This will add a reference to the selected response header in the OpenAPI specification.

</td>
</tr>
<tr>
<td valign="top">

Response Code

</td>
<td valign="top">

Enter the response range or code number.

</td>
<td valign="top">

For example:

-   Range - 2XX, 4XX
-   Number - 201, 404



</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Add a short and meaningful description for the response header, including when it is expected in the response.

</td>
<td valign="top">

For example:

-   204 - Indicates that the API operation was successful.

    This is usually preferred when indicating that a DELETE, PUT or PATCH update operation was successful.

-   2XX - The request was processed successfully.
-   4XX - The request cannot be completed due to an issue on the client's end. Please try again.

    > ### Note:  
    > This range indicate a group of HTTP status codes, such as 400-499 that are used to describe client errors.




</td>
</tr>
<tr>
<td valign="top">

Default

</td>
<td valign="top">

Default value of the header.

</td>
<td valign="top">

For example, a server can define a rate limit of 100.

</td>
</tr>
<tr>
<td valign="top">

Max Length

</td>
<td valign="top">

Enter the maximum length for a string.

</td>
<td valign="top">

 

</td>
</tr>
</table>



### Response Body

You can update an existing response body for a specific resource by searching and selecting it under *Response Body*.

1.  Under *Response Body*, choose *\+*. Add a *Response Code* and *Description*.

2.  Choose *Add* to create a new response body.
3.  Fill in the following information for each new field:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Input
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Node
    
    </td>
    <td valign="top">
    
    Select a root node or add the response body as new root node.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Key
    
    </td>
    <td valign="top">
    
    Enter the name of the response body.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Required
    
    </td>
    <td valign="top">
    
    Select *Required* if the response body should provide additional information outside of the main response body.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="3">
    
    Data Type
    
    </td>
    <td valign="top">
    
    Basic
    
    </td>
    <td valign="top">
    
    Select the data type, such as string, boolean, and so forth.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Component
    
    </td>
    <td valign="top">
    
    Select schemas and parameters from available components.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Operator
    
    </td>
    <td valign="top">
    
    Add multiple components and define how they are combined by selecting one of the following operator types:

    -   *allOf*
    -   *oneOf*
    -   *anyOf*
    -   *not*

    > ### Note:  
    > This is only supported for OpenAPI Specification 3.x.x and higher.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Response Code
    
    </td>
    <td valign="top">
    
    Enter response code number.
    
    </td>
    <td valign="top">
    
    For example:

    -   Number - 201, 404


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Add a short and meaningful description for the response code number in the resource.
    
    </td>
    <td valign="top">
    
    For example,

    -   204 - Has a generic meaning "No content", but for a specific operation it has a specific meaning, for example, "the product is out of stock", or "the order is not found".


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Default
    
    </td>
    <td valign="top">
    
    Enter the default value of the body.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Max Length
    
    </td>
    <td valign="top">
    
    Enter the maximum length for a string.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    



## Components

This tab is where you manage reusable components such as schemas, responses, request bodies, headers, and parameters. To reuse these components for a specific resource, select *Component* or *Operator*under *Data Type* in the *Resources* tab.

You can reuse responses for a specific response code at the root level. You can reuse request bodies at the root level for a specific content type or for part of the payload.

A schema contains a list of fields that are used to extract data for the result of an API.

> ### Note:  
> For OpenAPI Specification 2.X, definitions, responses, and parameters are supported common components. OpenAPI Specification 3.X supports request bodies.

Go to *Components* and select an existing schema or add new ones as follows:


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Input

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Node

</td>
<td valign="top">

Select a parent node if available.

</td>
<td valign="top">

The default is *root* node.

</td>
</tr>
<tr>
<td valign="top">

Key

</td>
<td valign="top">

Enter the name of the field.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Required

</td>
<td valign="top">

Select *Required* if the field is needed to successfully process the API resource.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Data Type

</td>
<td valign="top">

Basic

</td>
<td valign="top">

Select the data type, such as string, boolean, and so forth.

</td>
</tr>
<tr>
<td valign="top">

Component

</td>
<td valign="top">

Select schemas, responses, and headers from available components.

</td>
</tr>
<tr>
<td valign="top">

Operator

</td>
<td valign="top">

Add multiple components and define how they are combined by selecting one of the following operator types:

-   *allOf*
-   *oneOf*
-   *anyOf*
-   *not*

> ### Note:  
> This is only supported for OpenAPI Specification 3.x.x and higher.



</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Enter the field description.

</td>
<td valign="top">

Depending on the field type, enter a short noun phrase or begin with a verb describing the field in the description field. If applicable, describe usage specifics, for example, for different values.

Example:

Determines whether users are allowed to edit the count for this attendee type.

</td>
</tr>
<tr>
<td valign="top">

Default

</td>
<td valign="top">

Enter a default value for the schema.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Max Length

</td>
<td valign="top">

Enter the maximum length for a string.

</td>
<td valign="top">

 

</td>
</tr>
</table>



## Final Steps and Results

When you are finished modifying your API, check for validation errors. If there are errors, you must fix or delete them before you will be able to switch between editors.

> ### Note:  
> When you switch between the *Code* and visual *Editor* or back to API Details, your changes to the OpenAPI specification are kept if they are valid.

Once your changes have been successfully validated, choose one of the following:

1.  Choose *Save* to save your changes.
2.  Choose *Save as Version* to keep your original API and create a new version.

You can only save and deploy a valid OpenAPI specification. The deployed state indicates that the OpenAPI specification is published.

