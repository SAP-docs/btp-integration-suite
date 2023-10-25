<!-- loio67f336dbe357433f8d260b657e0f979f -->

# Adding Responses

Define all the expected responses, including the response headers, response message, and error messages.

The server receives an incoming request and responds with a message indicating whether the request was successful or not. Such a response consists of the following elements:

-   An HTTP status code

-   Zero or more Response Headers

-   An optional Response Body


Use the standard HTTP status codes for describing the success or failure of the request. It is also recommended to use the HTTP response headers.



<a name="loio67f336dbe357433f8d260b657e0f979f__section_fm2_zpd_4mb"/>

## Adding Responses without a Body

It is a valid and common feature of a RESTFul API that the response to certain operations contains no body. For instance, the Update operations \(implemented by the HTTP method PUT \) belonging to the ESPM OData API in the example below typically return an HTTP status code 204 with no message body.

In the example below, the same information is modeled using the Open API specification:

> ### Sample Code:  
> API specification in YAML
> 
> ```
> paths:
>   '/Products(''{ProductId}'')':
>     put:
>       summary: Update a product entity in Products entityset
>       description: Update a product entity in Products entityset
>       tags:
>         - Products
>       parameters:
>         - name: ProductId
>           in: path
>           required: true
>           description: 'key: ProductId'
>           type: string
>         - name: Product
>           in: body
>           description: The entity to patch
>           schema:
>             $ref: '#/definitions/Product'
>       responses:
>         '204':
>           description: Empty response
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
>    "paths": {
>       "/Products('{ProductId}')": {
>          "put": {
>             "summary": "Update a product entity in Products entityset",
>             "description": "Update a product entity in Products entityset",
>             "tags": [
>                "Products"
>             ],
>             "parameters": [
>                {
>                   "name": "ProductId",
>                   "in": "path",
>                   "required": true,
>                   "description": "key: ProductId",
>                   "type": "string"
>                },
>                {
>                   "name": "Product",
>                   "in": "body",
>                   "description": "The entity to patch",
>                   "schema": {
>                      "$ref": "#/definitions/Product"
>                   }
>                }
>             ],
>             "responses": {
>                "204": {
>                   "description": "Empty response"
>                }
>             }
>          }
>       }
>    }
> }
> ```



<a name="loio67f336dbe357433f8d260b657e0f979f__section_dnh_4sd_4mb"/>

## Responses with a Body

For certain operations like Create \(implemented by the HTTP method POST \), the newly created resource is typically returned as the response body. This is to save the client from then having to perform a subsequent Read operation to determine the exact server-side state of the newly created resource.

In the example below, this information is modeled using the Open API specification. Since the definition of the Product returned in the response is exactly the same as that previously defined in the section on requests, the reference to the Product definition can be reused

> ### Sample Code:  
> API specification in YAML
> 
> ```
> paths:
>   '/Products(''{ProductId}'')':
>     post:
>       summary: Create a product
>       description: Create a product entity in Products entityset
>       tags:
>         - Products
>       parameters:
>         - name: Product
>           in: body
>           description: Product entity to be created
>           schema:
>             $ref: '#/definitions/Product'
>       responses:
>         '201':
>           description: Created product
>           schema:
>             $ref: '#/definitions/Product'
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
>    "paths": {
>       "/Products('{ProductId}')": {
>          "post": {
>             "summary": "Create a product",
>             "description": "Create a product entity in Products entityset",
>             "tags": [
>                "Products"
>             ],
>             "parameters": [
>                {
>                   "name": "Product",
>                   "in": "body",
>                   "description": "Product entity to be created",
>                   "schema": {
>                      "$ref": "#/definitions/Product"
>                   }
>                }
>             ],
>             "responses": {
>                "201": {
>                   "description": "Created product",
>                   "schema": {
>                      "$ref": "#/definitions/Product"
>                   }
>                }
>             }
>          }
>       }
>    }
> }
> ```



<a name="loio67f336dbe357433f8d260b657e0f979f__section_db1_4td_4mb"/>

## Response Headers

Along with the response message, the server can respond with zero or more headers.

In the example below, the custom HTTP header DataServiceVersion is described. This header informs the client about the version of OData used to build the response.

> ### Sample Code:  
> API specification in YAML
> 
> ```
> paths:
>   '/Products(''{ProductId}'')':
>     post:
>       summary: Create a new product
>       description: Post a new entity to entity set Products
>       tags:
>         - Products
>       parameters:
>         - name: Product
>           in: body
>           description: Product entity to be created
>           schema:
>             $ref: '#/definitions/Product'
>       responses:
>         '201':
>           description: Created Product
>           headers:
>             DataServiceVersion:
>               type: string
>               description: |
>                 The value states the OData version the server used to generate the response 
>                 and that should be used by the client to determine if it can correctly interpret the response
>           schema:
>             $ref: '#/definitions/Product'
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
>    "paths": {
>       "/Products('{ProductId}')": {
>          "post": {
>             "summary": "Create a new product",
>             "description": "Post a new entity to entity set Products",
>             "tags": [
>                "Products"
>             ],
>             "parameters": [
>                {
>                   "name": "Product",
>                   "in": "body",
>                   "description": "Product entity to be created",
>                   "schema": {
>                      "$ref": "#/definitions/Product"
>                   }
>                }
>             ],
>             "responses": {
>                "201": {
>                   "description": "Created Product",
>                   "headers": {
>                      "DataServiceVersion": {
>                         "type": "string",
>                         "description": "The value states the OData version the server used to generate the response \nand that should be used by the client to determine if it can correctly interpret the response\n"
>                      }
>                   },
>                   "schema": {
>                      "$ref": "#/definitions/Product"
>                   }
>                }
>             }
>          }
>       }
>    }
> }
> ```

Based on such a definition, the client can then expect to receive a response containing at least the DataServiceVersion header. For example, a Gateway OData server returns the following headers. Notice that DataServiceVersion is among those headers.

> ### Sample Code:  
> ```
> cache-control:no-store, no-cache, must-revalidate, max-age=0, post-check=0, pre-check=0
> content-encoding:gzip
> content-length:785
> content-type:application/xml
> dataserviceversion:2.0
> pragma:no-cache
> sap-metadata-last-modified:Fri, 15 Jan 2016 04:01:16 GMT
> server:SAP NetWeaver Application Server / ABAP 702
> ```

> ### Note:  
> Notice also that all the HTTP header fields returned from an ABAP OData server are in lowercase. This conforms to the HTTP standard that all HTTP header fields are case insensitive.



<a name="loio67f336dbe357433f8d260b657e0f979f__section_jvz_x22_jxb"/>

## Error Response

In case of an error, the server should return an error message that best describes the cause of the problem and, where possible, provides information on how to correct that problem. It is a good practice to use standard HTTP error status codes to inform about the nature of the error and have a common error schema describing each of these status codes.

The text of error message should always help move the user towards the solution. Simply responding with a generic error message such as "Internal server error" leaves the user stranded and unable to proceed towards a solution.

For example, the ESPM OData API returns errors using the OData error format, and therefore we have documented some of the commonly returned error codes. Since the error messages are the same for all the operations, we have documented them in one place using the responses object of the Open API specification, then referenced those definitions within the same file.

> ### Sample Code:  
> API specification in YAML
> 
> ```
> responses:
>   401:
>     description: Unauthorized
>   404:
>     description: Not Found
>     schema:
>       $ref: '#/definitions/odata.error'
>   400:
>     description: Bad Request
>     schema:
>       $ref: '#/definitions/odata.error'
>   500:
>     description: Internal server error
>     schema:
>       $ref: '#/definitions/odata.error'
> definitions:
>   odata.error:
>     type: object
>     properties:
>       code:
>         type: string
>         description: Error code
>       message:
>         type: object
>         properties:
>           lang:
>             type: string
>             description: Language code of the error message
>           value:
>             type: string
>             description: Detailed error message
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
>    "responses": {
>       "400": {
>          "description": "Bad Request",
>          "schema": {
>             "$ref": "#/definitions/odata.error"
>          }
>       },
>       "401": {
>          "description": "Unauthorized"
>       },
>       "404": {
>          "description": "Not Found",
>          "schema": {
>             "$ref": "#/definitions/odata.error"
>          }
>       },
>       "500": {
>          "description": "Internal server error",
>          "schema": {
>             "$ref": "#/definitions/odata.error"
>          }
>       }
>    },
>    "definitions": {
>       "odata.error": {
>          "type": "object",
>          "properties": {
>             "code": {
>                "type": "string",
>                "description": "Error code"
>             },
>             "message": {
>                "type": "object",
>                "properties": {
>                   "lang": {
>                      "type": "string",
>                      "description": "Language code of the error message"
>                   },
>                   "value": {
>                      "type": "string",
>                      "description": "Detailed error message"
>                   }
>                }
>             }
>          }
>       }
>    }
> }
> ```

In the example below, we show the usage of the above error responses within an operation to update a Product entity.

> ### Sample Code:  
> API specification in YAML
> 
> ```
> paths:
>   '/Products(''{ProductId}'')':
>     put:
>       summary: Update entity in EntitySet Products
>       description: Update entity in EntitySet Products
>       tags:
>         - Products
>       parameters:
>         - name: ProductId
>           in: path
>           required: true
>           description: 'key: ProductId'
>           type: string
>         - name: Product
>           in: body
>           description: The entity to patch
>           schema:
>             $ref: '#/definitions/Product'
>       responses:
>         '204':
>           description: Empty response
>         401:
>            $ref: '#/responses/401'
>         404:
>            $ref: '#/responses/404'
>         400:
>            $ref: '#/responses/400'
>         500:
>           $ref: '#/responses/500'
> ```

> ### Sample Code:  
> API specification in JSON
> 
> ```
> {
>    "paths": {
>       "/Products('{ProductId}')": {
>          "put": {
>             "summary": "Update entity in EntitySet Products",
>             "description": "Update entity in EntitySet Products",
>             "tags": [
>                "Products"
>             ],
>             "parameters": [
>                {
>                   "name": "ProductId",
>                   "in": "path",
>                   "required": true,
>                   "description": "key: ProductId",
>                   "type": "string"
>                },
>                {
>                   "name": "Product",
>                   "in": "body",
>                   "description": "The entity to patch",
>                   "schema": {
>                      "$ref": "#/definitions/Product"
>                   }
>                }
>             ],
>             "responses": {
>                "204": {
>                   "description": "Empty response"
>                },
>                "400": {
>                   "$ref": "#/responses/400"
>                },
>                "401": {
>                   "$ref": "#/responses/401"
>                },
>                "404": {
>                   "$ref": "#/responses/404"
>                },
>                "500": {
>                   "$ref": "#/responses/500"
>                }
>             }
>          }
>       }
>    }
> }
> ```

