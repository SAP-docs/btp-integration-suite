<!-- loio37f9ad1102754c13a5444bebb63cd088 -->

# Responses with a Body

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

