<!-- loiofe19d580a41c4788acd46a770291ae17 -->

# Error Response

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

