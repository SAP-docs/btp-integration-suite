<!-- loio83b14c2886e94c9b95679a3fcba1f0f3 -->

# REST Services as Data Sources

Graph allows you to compose business data graphs from multiple-source APIs \(called data sources\).

Next to OData, it supports REST-services as data sources. To the outside Graph exposes an ODataV4 or GraphQL API for a business data graph, so that developers can consume all data via a single unified API with a single protocol. As generic REST-services can be designed and structured arbitrarily, Graph transforms how resources from REST-services are exposed in a business data graph in order to ensure compliance with the external OData API



<a name="loio83b14c2886e94c9b95679a3fcba1f0f3__section_gt5_4jv_42c"/>

## Transformations for REST Service Resources

To maintain OData v4 compliance, several transformations are applied to resources of REST services when they are added to a business data graph:

1.  Transformation to Unbound Actions & Functions

    All REST operations are transformed into unbound actions and functions within the OData API.

2.  Path Flattening

    All resource paths are flattened by replacing path separators with underscores to ensure a consistent naming convention compatible with OData. Path parameters, query options or custom headers become action/function parameters.

    > ### Sample Code:  
    > ```
    > GET /users/pets => GET /<namespace>/users_pets
    > GET /users/{id} => GET /<namespace>/users_(id=<value>)
    > GET /users => GET /<namespace>/users
    > 
    > ```

3.  Method Standardization

    All HTTP Methods are standardized to either GET or POST, in alignment with actions and functions within OData. To differentiate between similarly named paths, the method name is appended to the operation.

    > ### Sample Code:  
    > ```
    > DELETE /users/pets => POST /<namespace>/users_pets__delete
    > POST /users/pets => POST /<namespace>/users_pets__post
    > GET /users/pets => GET /<namespace>/users_pets
    > 
    > ```


