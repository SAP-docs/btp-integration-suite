<!-- loio51f3ca114ea74d4c87990aafd8e6c778 -->

# API Designer

You can create APIs in API designer.

Use the [OpenAPI Specification](https://github.com/OAI/OpenAPI-Specification) to create APIs in API designer.

API specification can be written in YAML or JSON. In this guide, we use both YAML and JSON examples.

The API designer has a preview pane. You can write API specification in YAML in the right-hand pane and preview the corresponding reference documentation in the left-hand pane.

The following image illustrates the process of API creation in API designer.

> ### Note:  
> All the API code samples shown in this document refers to only API 2.0 specification.

> ### Note:  
> The image contains links to more information. You can hover over each shape for a description and click on it for more information.



![](images/Image_Map_-_Create_APIs_v3_8fc90a1.png)



### Define Metadata

Enter the general information or the metadata of the API:

-   **swagger** - The version of the OpenAPI Specification. 2.0 being the latest version.
-   **title** - A short summary of the API overall functionality.
-   **description** -

    An expanded description of the API overall functionality and its usage specifics, if any.

    Descriptions can be entered in multiline. Basic html tags with appropriate attributes, can be used for styling.

    Tags that can be used are:

    -   <a\>
    -   <b\>
    -   <blockquote\>
    -   <br\>
    -   <cite\>
    -   <code\>
    -   <dd\>
    -   <dl\>
    -   <dt\>
    -   <em\>
    -   <i\>
    -   <li\>
    -   <ol\>
    -   <p\>
    -   <pre\>
    -   <q\>
    -   <small\>
    -   <span\>
    -   <strike\>
    -   <strong\>
    -   <sub\>
    -   <sup\>
    -   <u\>
    -   <ul\>
    -   <img\>

    Any other tags will be auto-removed.

    For the image, only Base64 encoded content is supported.

-   **version** - The version of the API.

    > ### Sample Code:  
    > API specification in YAML
    > 
    > ```
    > swagger: '2.0'
    > info:
    >   title: SAP Workflow API
    >   description: |
    >          This API provides functionality to work with
    >          SAP Workflow Service.
    >          You can, for example, start new workflow instances 
    >          and work with tasks.  
    >   version: 1.0      
    > 
    > ```

    > ### Sample Code:  
    > API specification in JSON
    > 
    > ```
    > {
    >   "swagger": "2.0",
    >   "info": {
    >     "title": "SAP Workflow API",
    >     "description": "This API provides functionality to work with SAP Workflow Service.",
    >     "version": 1
    >   }
    > }
    > ```

    > ### Sample Code:  
    > API specification in YAML
    > 
    > ```
    > swagger: '2.0'
    > info:
    >   title: SAP e-commerce API
    >   description: |
    >          This API provides functionality to build an 
    >          e-commerce site selling electronic products
    >          The following scenarios are covered:
    >          * Customer can order products
    >          * Customer can provide product reviews
    >          * Retailer can create sales orders
    >          * Retailer can update product stock
    >   version: 1.0
    >       
    > ```

    > ### Sample Code:  
    > API specification in JSON
    > 
    > ```
    > {
    >   "swagger": "2.0",
    >   "info": {
    >     "title": "SAP e-commerce API",
    >     "description": "This API provides functionality to build an e-commerce site selling electronic products.",
    >     "version": 1
    >   }
    > }
    > ```

    It is also a good practice to provide the license and the contacts details of the API. In the `license` object, you can provide a link to the licensing rules for the API, and in the `contact` object, you can provide details of the API provider.

    > ### Sample Code:  
    > API specification in YAML
    > 
    > ```
    > 
    >   license:
    >     name: Apache-2.0
    >     url: "https://github.com/SAP/master/LICENSE"
    >   contact:
    >     name: SAP API Business Hub team
    >     email: SAPAPIHubInfo@sap.com
    >     url: https://api.sap.com/#/community
    > ```

    > ### Sample Code:  
    > API specification in JSON
    > 
    > ```
    > {
    >   "license": {
    >     "name": "Apache-2.0",
    >     "url": "https://github.com/SAP/master/LICENSE"
    >   },
    >   "contact": {
    >     "name": "SAP API Business Hub team",
    >     "email": "SAPAPIHubInfo@sap.com",
    >     "url": "https://api.sap.com/#/community"
    >   }
    > }
    > ```




### Define Root URL

APIs have a root URL to which the paths or the endpoints are appended. The root URL is defined by `host`, `schemes`, and `basePath` on the root level of the OpenAPI Specification.:

-   **host** - The host \(name or IP address\) serving the API. The host might include a port number. If a value for host is missing, then the host \(including the port\) providing the documentation is assumed also to provide the API.
-   **schemes** - The transfer protocol expected by the API. Values must be either `http` or `https`. If a value for schemes is missing, then the scheme used to access the OpenAPI Specification definition becomes the scheme used to access the API.
-   **basePath** - The base path on which the API is served, relative to the host. If this value is missing, then the API must be available directly under the host. The value must start with a leading forward slash \( / \).

    > ### Sample Code:  
    > API specification in YAML
    > 
    > ```
    > 
    > host: localhost
    > schemes:
    >   - https
    > basePath: /espm-cloud-web/espm.svc/secure
    > ```

    > ### Sample Code:  
    > API specification in JSON
    > 
    > ```
    > {
    >   "host": "localhost",
    >   "schemes": [
    >     "https"
    >   ],
    >   "basePath": "/espm-cloud-web/espm.svc/secure"
    > }
    > ```




### Add Attributes

You can define additional fields or attributes in the Open API Specification to enhance the usability of your API. Swagger JSON provides additional attributes that start with x-, such as x-servers. They can be used to describe additional functionality that is not covered by the standard OpenAPI Specification.



### Define Operations

Define the available paths \(endpoints\) and API operations. Paths are endpoints \(resources\) that your API exposes, such as `/products` or `/store/inventory`. Operations are the HTTP methods used to manipulate these paths, such as `put`, `get`, or `post`. Each operation is defined in its own `operation` object, including the path \(endpoint\), the HTTP method name, such as `get` or `put`, `summary`, and the `description`. You can add as many paths as you require.

> ### Sample Code:  
> API specification in YAML
> 
> ```
> paths:
>   /products:
>     get:
>        summary: Retrieves all products	
>        description: |
>               Retrieves the list of all available
>               products in the inventory.
> 
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
>    "paths": {
>       "/products": {
>          "get": {
>             "summary": "Retrieves all products",
>             "description": "Retrieves the list of all available\nproducts in the inventory.\n"
>          }
>       }
>    }
> }
> ```

All API paths or endpoints are relative to the root URL, for example, `/products` means `<scheme>://<host>/<basePath>/products.` That is, if you want to list all the products available in the inventory, your API call would be:

`GET http://localhost//espm-cloud-web/espm.svc/secure/products`



### Define Parameters

Define the input parameters that you want your API Operation to accept. The information about the input parameters is provided in the `Parameters` object of each operation in the API definition file. Each parameter accepted by an operation is defined by a number of properties of the parameter object. The `in` property defines the location in which the parameter is passed.

> ### Sample Code:  
> API specification in YAML
> 
> ```
> parameters:
>         description: | 
>                The workflow instance ID for
>                which task instances are returned.
>         in: query
>         name: workflowInstanceID
>         required: true
>         type: string
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
>   "parameters": {
>     "description": "The workflow instance ID for which task instances are returned.",
>     "in": "query",
>     "name": "workflowInstanceID",
>     "required": true,
>     "type": "string"
>   }
> }
> ```

For a detailed explanation about how to define the input parameters for your API, see [Adding Input Parameters - Headers and Queries](adding-input-parameters-headers-and-queries-d460d43.md)



### Define Responses

Define the responses for API operations. For each possible response returned by an API operation, define a corresponding HTTP response status code and its description in the `responses` object. Defining HTTP status codes is crucial, as it describes the purpose of each method and the corresponding responses.

> ### Sample Code:  
> API specification in YAML
> 
> ```
> 
> responses:
>    '204':
>      description: | 
>             The task was successfully completed 
>             and the context was updated.
>    '400':
>      description: |
>             Wrong format or structure 
>             of the provided request body.
>    '403':
>      description: | 
>             Access denied. 
>             You did not have the required permissions
>             to access the resource.
>    '404':
>      description: |
>             Not found. Possible reasons:
>             - You provided a wrong URL.
>             - The given task you are referring to doesn't 
>             exist.
>             - You are not allowed to access the task.
> 
>    '422':
>      description: |
>             The workflow context provided in the 
>             request body contained invalid keys or values.
>    '500':
>      description: |
>             Internal server error. 
>             The operation you requested 
>             led to an error during execution.
>    
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
>    "responses": {
>       "204": {
>          "description": "The task was successfully completed \nand the context was updated.\n"
>       },
>       "400": {
>          "description": "Wrong format or structure \nof the provided request body.\n"
>       }
>    }
> }
> ```

For a detailed explanation about how to define responses for your API Operation, see [Adding Responses](adding-responses-ea40cd7.md).



### Add Definitions

If the same data type, parameter or response are used in multiple operations within the same API or service, you can simplify the API definition file by creating a reusable definition for each of them, and reference it where relevant across the API.



### Add Security Definitions

Define all the implemented security mechanism for your APIs. Information about these schemes is provided under the `Security Definitions` object. The OpenAPI specification currently supports `basic`, `apiKey`, and `oauth2` security scheme types.

> ### Sample Code:  
> ```
> securityDefinitions:
>   basicAuthentication:
>     type: basic
>   oauth2:
>     type: oauth2
>     description: > To use this API, you need to obtain
> 	 the OAuth client credentials (client ID and secret)
> 	 using the SAP HANA BTP cockpit. 
> 	 After that, pass these client credentials to
> 	 the SAP HANA BTP token endpoint
> 	 to obtain an access token. 
>     authorizationUrl: >-
>       https://host1/oauth/tok/v1?grant_type=client_credentials
>     flow: implicit
>     scopes:
>       product_view: Read Product entities
>       product_manage: Manage Product entities
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
>   "securityDefinitions": {
>     "basicAuthentication": {
>       "type": "basic"
>     }
>   }
> }
> ```

For more information, see [Adding Security Definitions](adding-security-definitions-092f7f2.md).



### Add tags

To group related operations by categories, you can define tags to the operations so that they are rendered in an organized manner in the output. You define the tags under `tags` in the root swagger object. Each tag is identified by its `name`, which must be unique in the list of tags, and optional `description` and `externalDocs`. Then, you can assign the defined tags to operations, referring to them by names. Note that you can define a tag directly in an operation even if it is not defined on the root level.

> ### Sample Code:  
> API specification in YAML
> 
> ```
> tags:
> - name: Task Instances
>   description: ''
> - name: Workflow Definitions
>   description: ''
> - name: Workflow Instances
>   description: ''
> 
> ...
> get:
>       tags:
>       - Task Instances
>       description: Retrieves the context of a task.
> 
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
>   "tags": [
>     {
>       "name": "Task Instances",
>       "description": ""
>     },
>     {
>       "name": "Workflow Definitions",
>       "description": ""
>     },
>     {
>       "name": "Workflow Instances",
>       "description": ""
>     }
>   ]
> }
> . . . 
> 
> {
>   "get": {
>     "tags": [
>       "Task Instances"
>     ],
>     "description": "Retrieves the context of a task."
>   }
> }
> 
> ```



### Add External Links

Add external links, if any, in your API Definition to provide enhanced user assistance for using the APIs. You define the external links in the `externalDocs` object, which can be used on the root level for the entire API, and/or on the operation or tag level, as required.

> ### Sample Code:  
> API specification in YAML
> 
> ```
> externalDocs:
>   description: SAP Workflow Documentation
>   url: https://help.sap.com/viewer/p/WORKFLOW_SERVICE
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
>   "externalDocs": {
>     "description": "SAP Workflow Documentation",
>     "url": "https://help.sap.com/viewer/p/WORKFLOW_SERVICE"
>   }
> }
> ```

Once you have defined all the necessary information of the API, choose *File* \> *Save* in API designer .

> ### Note:  
> If you have created a new API, enter a name for it. If you are editing an existing API, save it under the existing name. When you save, you may receive warning messages about missing parameters. In this case, add the required parameters and save again.

**Related Information**  


[Perform Additional Tasks in API Designer](perform-additional-tasks-in-api-designer-a92cf80.md "")

