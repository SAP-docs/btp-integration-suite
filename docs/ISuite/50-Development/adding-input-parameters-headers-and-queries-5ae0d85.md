<!-- loio5ae0d85bb03b4a548a1de89a6e6d5790 -->

# Adding Input Parameters - Headers and Queries

Define all input parameters for your API operation, irrespective of whether they are mandatory or optional. The parameters information can be modeled under `parameters` definitions object in the OpenAPI specification.

In a RESTFul API, the input parameters can be any of the following types:

-   **Query Parameters**

    When submitting a request, these parameters form the query string part at the end of the request URL .A question mark \(?\) character delimits the URL from the query string. For example, `Products?$top=2`. Multiple parameters can be supplied as name/value pairs in the format name="value". Each name/value pair is separated by the ampersand \(&\) character. For example, `Products?$skip=10&$top=2&someName="someValue"`.

    > ### Sample Code:  
    > API specification in YAML
    > 
    > ```
    > parameters:
    >         - in: query
    >           name: pageNumber
    >           type: integer
    >           description: The page number from which the items must be listed .
    >         - in: query
    >           name: limit
    >           type: pageSize
    >           description: The number of items to be returned on the specified page.
    > ```
    > 
    > In the above example a GET call, say `GET /products?pageNumber=2&pageSize=20` returns 20 products from page number 2.

    > ### Sample Code:  
    > API specification in JSON
    > 
    > ```
    > {
    >    "parameters": [
    >       {
    >          "in": "query",
    >          "name": "pageNumber",
    >          "type": "integer",
    >          "description": "The page number from which the items must be listed ."
    >       },
    >       {
    >          "in": "query",
    >          "name": "limit",
    >          "type": "pageSize",
    >          "description": "The number of items to be returned on the specified page."
    >       }
    >    ]
    > }
    > ```
    > 
    > In the above example a GET call, say `GET /products?pageNumber=2&pageSize=20` returns 20 products from page number 2.

-   **Header Parameters**

    Header parameters are components of the header section of an HTTP request or response. The name of a header field must be immediately followed by a colon : character. Any whitespace between the field name and the colon is syntactically incorrect. The header parameter value is provided as a plain text string. For example, `Accept: application/json`.

    For example, suppose a call to `GET /check` requires the `Request-ID` header:

    > ### Sample Code:  
    > ```
    > GET /check HTTP/1.1
    > Host: localhost
    > Request-ID: 2345-23567-4356-ab32-43ed
    > ```

    In the API Specification, you will write the operation definition as follows:

    > ### Sample Code:  
    > API specification in YAML
    > 
    > ```
    > /check:
    >     get:
    >       summary: Checks if the server is up.
    >       parameters:
    >         - in: header
    >           name: Request-ID
    >           type: string
    >           required: true  
    >       responses:
    >           200:
    >             description: OK
    > ```

    > ### Sample Code:  
    > API specification in JSON
    > 
    > ```
    > {
    >    "/check": {
    >       "get": {
    >          "summary": "Checks if the server is up.",
    >          "parameters": [
    >             {
    >                "in": "header",
    >                "name": "Request-ID",
    >                "type": "string",
    >                "required": true
    >             }
    >          ],
    >          "responses": {
    >             "200": {
    >                "description": "OK"
    >             }
    >          }
    >       }
    >    }
    > }
    > ```

-   **Path Parameters**

    Path parameters are a flexible way of parameterizing the actual values used when creating the path to a resource. For example, if the value of the Product ID needs to be present in the path name, then this can be parameterized as follows:`/Products/{ProductId}`.

    > ### Note:  
    > The parameter name must be the same as specified in the path. Also, remember to add `required: true`, because path parameters are always required.

    > ### Sample Code:  
    > API specification in YAML
    > 
    > ```
    > paths:
    >   /products{productId}:
    >     get:
    >       parameters:
    >         - in: path
    >           name: ProductId   # Note the name is the same as in the path
    >           required: true 
    >           type: integer
    >           minimum: 1
    >           description: The product ID.
    >       responses:
    >           200:
    >            description: OK
    > ```

    > ### Sample Code:  
    > API specification in JSON
    > 
    > ```
    > {
    >    "paths": {
    >       "/products{productId}": {
    >          "get": {
    >             "parameters": [
    >                {
    >                   "in": "path",
    >                   "name": "ProductId",
    >                   "required": true,
    >                   "type": "integer",
    >                   "minimum": 1,
    >                   "description": "The product ID."
    >                }
    >             ],
    >             "responses": {
    >                "200": {
    >                   "description": "OK"
    >                }
    >             }
    >          }
    >       }
    >    }
    > }
    > ```


You can familiarize more about defining parameters with the below examples:

The following APIs use OData protocol, and they support OData system queries. The commonly used system query parameters are defined in the following example:

> ### Sample Code:  
> API Specification in YAML
> 
> ```
> parameters:
>   top:
>     name: $top
>     in: query
>     description: >-
>       Show only the first N elements, where N is a positive integer. 
>       If a value less than 0 is specified, the URI should be considered malformed. 
>       ref [link](http://www.odata.org/documentation/odata-version-2-0/uri-conventions/#SystemQueryOptions) for more information
>     type: integer
>     minimum: 0
>   skip:
>     name: $skip
>     in: query
>     description: >-
>       Skip the first N elements, where N is a positive integer as specified by this query option. 
>       If a value less than 0 is specified, the URI should be considered malformed. 
>       ref [link](http://www.odata.org/documentation/odata-version-2-0/uri-conventions/#SystemQueryOptions) for more information
>     type: integer
>     minimum: 0
>   count:
>     name: $count
>     in: query
>     description: >-
>       Include count of elements.
>       ref [link](http://www.odata.org/documentation/odata-version-2-0/uri-conventions/#SystemQueryOptions) for more information
>     type: boolean
> ```

> ### Sample Code:  
> API Specification in JSON
> 
> ```
> {
>    "parameters": {
>       "top": {
>          "name": "$top",
>          "in": "query",
>          "description": "Show only the first N elements, where N is a positive integer.",
>          "type": "integer",
>          "minimum": 0
>       },
>       "skip": {
>          "name": "$skip",
>          "in": "query",
>          "description": "Skip the first N elements, where N is a positive integer as specified by this query option.",
>          "type": "integer",
>          "minimum": 0
>       },
>       "count": {
>          "name": "$count",
>          "in": "query",
>          "description": "Include count of elements.",
>          "type": "boolean"
>       }
>    }
> }
> ```

These parameters can be referred in the `get` operation listed under *paths* \> */Products* as follows:

> ### Sample Code:  
> API Specification in YAML
> 
> ```
> paths:
>   /Products:
>     get:
>       summary: Get entities from entity set Products
>       description: Get entities from entity set Products
>       security:
>         - oauth2:
>             - product_view
>       tags:
>         - Products
>       parameters:
>         - $ref: '#/parameters/top'
>         - $ref: '#/parameters/skip'
>         - $ref: '#/parameters/count'
> ```

> ### Sample Code:  
> API Specification in JSON
> 
> ```
> {
>    "paths": {
>       "/Products": {
>          "get": {
>             "summary": "Get entities from entity set Products",
>             "description": "Get entities from entity set Products",
>             "security": [
>                {
>                   "oauth2": [
>                      "product_view"
>                   ]
>                }
>             ],
>             "tags": [
>                "Products"
>             ],
>             "parameters": [
>                {
>                   "$ref": "#/parameters/top"
>                },
>                {
>                   "$ref": "#/parameters/skip"
>                },
>                {
>                   "$ref": "#/parameters/count"
>                }
>             ]
>          }
>       }
>    }
> }
> ```

The advantage of defining the parameters in this way is that they can be defined once, and then later referenced from multiple places within the same specification file.

In the following example, other system queries such as `$select` , `$expand` and`$orderby` are defined at the operations level:

> ### Sample Code:  
> API Specification in YAML
> 
> ```
> paths:
>   /Products:
>     get:
>       summary: Get entities from entity set Products
>       description: Get entities from entity set Products
>       security:
>         - oauth2:
>             - product_view
>       tags:
>         - Products
>       parameters:
>         - $ref: '#/parameters/top'
>         - $ref: '#/parameters/skip'
>         - $ref: '#/parameters/count'
>         - name: $orderby
>           in: query
>           description: >-
>             Order by property values, for example `?$orderby=Name` for sorting
>             the Products by Name and `?$orderby=Name desc` for sorting the
>             Products by Name in descending order
>           type: array
>           uniqueItems: true
>           items:
>             type: string
>           enum:
>             - Category
>             - Category desc
>             - CategoryName
>         - name: $select
>           in: query
>           description: >-
>             Select properties to be returned, The value of a $select System
>             Query Option is a comma-separated list of selection clauses. Each
>             selection clause may be a Property name, Navigation Property name.
>             for example `?$select=Category,Name` so that only Category and Name is returned
>           type: array
>           uniqueItems: true
>           items:
>             type: string
>           enum:
>             - Category
>             - CategoryName
>             - CurrencyCode
>         - name: $expand
>           in: query
>           description: >-
>             Expand related entities,The syntax of a $expand query option is a
>             comma-separated list of Navigation Properties. for example
>             `?$expand=Supplier` to get the related Supplier information inline.
>           type: array
>           uniqueItems: true
>           items:
>             type: string
>           enum:
>             - CustomerReview
>             - Supplier
> ```

> ### Sample Code:  
> API Specification in JSON
> 
> ```
> {
>    "paths": {
>       "/Products": {
>          "get": {
>             "summary": "Get entities from entity set Products",
>             "description": "Get entities from entity set Products",
>             "security": [
>                {
>                   "oauth2": [
>                      "product_view"
>                   ]
>                }
>             ],
>             "tags": [
>                "Products"
>             ],
>             "parameters": [
>                {
>                   "$ref": "#/parameters/top"
>                },
>                {
>                   "$ref": "#/parameters/skip"
>                },
>                {
>                   "$ref": "#/parameters/count"
>                },
>                {
>                   "name": "$orderby",
>                   "in": "query",
>                   "description": "Order by property values", 
>                   "type": "array",
>                   "uniqueItems": true,
>                   "items": {
>                      "type": "string"
>                   },
>                   "enum": [
>                      "Category",
>                      "Category desc",
>                      "CategoryName"
>                   ]
>                },
>                {
>                   "name": "$select",
>                   "in": "query",
>                   "description": "Select properties to be returned",
>                   "type": "array",
>                   "uniqueItems": true,
>                   "items": {
>                      "type": "string"
>                   },
>                   "enum": [
>                      "Category",
>                      "CategoryName",
>                      "CurrencyCode"
>                   ]
>                },
>                {
>                   "name": "$expand",
>                   "in": "query",
>                   "description": "Expand related entities",
>                   "type": "array",
>                   "uniqueItems": true,
>                   "items": {
>                      "type": "string"
>                   },
>                   "enum": [
>                      "CustomerReview",
>                      "Supplier"
>                   ]
>                }
>             ]
>          }
>       }
>    }
> }
> ```

In the following example, a paths parameter called `ProductId` is defined as a required field:

> ### Sample Code:  
> API Specification in YAML
> 
> ```
> paths:
>   /Products{ProductId}:
>     get:
>       summary: Get entity from Products by key.
>       description: Returns the entity with the key from Products
>       tags:
>         - Products
>       parameters:
>         - name: ProductId
>           in: path
>           required: true
>           description: 'key: ProductId'
>           type: string
> ```

> ### Sample Code:  
> API Specification in JSON
> 
> ```
> {
>    "paths": {
>       "/Products{ProductId}": {
>          "get": {
>             "summary": "Get entity from Products by key.",
>             "description": "Returns the entity with the key from Products",
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
>                }
>             ]
>          }
>       }
>    }
> }
> ```

