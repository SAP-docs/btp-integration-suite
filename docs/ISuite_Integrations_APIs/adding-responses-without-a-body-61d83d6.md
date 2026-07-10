<!-- loio61d83d656a4a43ddbacfed4bee78c217 -->

# Adding Responses without a Body

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

