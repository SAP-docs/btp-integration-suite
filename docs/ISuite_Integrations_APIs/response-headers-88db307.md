<!-- loio88db30730060465d9f1203b729ba50ff -->

# Response Headers

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

