<!-- loiode723090712e4d3dafab951b89b88faf -->

# GraphQL

GraphQL is a query language for APIs that uses similar modeling principles to OData. It features a type system to describe the data model and gives clients the ability to specify the data they want to request. Graph supports GraphQL as an alternative protocol to OData.

> ### Caution:  
> The GraphQL interface is in an early general availability state. It means it is generally available with stable APIs, unless otherwise indicated, and you can use it productively. However, there are current limitations compared to the OData interface that is stable. For more information, see [Limitations](graphql-de72309.md#loiode723090712e4d3dafab951b89b88faf__section_limitations).

GraphQL is a query language for APIs that provides a type system to describe the data model in a structured way. It provides a type system to describe the data model of an API in a structured way. Additionally, clients of an API use the query language to describe the data they want to request. GraphQL is similar to OData because they both provide a structured, typed schema for APIs and also enable clients to write powerful queries to request exactly the data they need using a single request. Graph offers two protocol adapters out of the box:

-   OData

-   GraphQL


The GraphQL adapter builds on the same metadata as the OData adapter.



<a name="loiode723090712e4d3dafab951b89b88faf__section_vsv_255_mvb"/>

## Explore

The GraphQL interface is exposed on a single endpoint in any given business data graph:

```
POST https://<subdomain>.a.integration.cloud.sap/graph/api/<bdg>/graphql
```

-   `subdomain` is the subdomain assigned to the tenant. For example, `is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef`.
-   `bdg` is the business data graph identifier specified by the Graph configuration.

Because the Graph API is always protected by OAuth 2.0 authorization, the bearer token is sent with all of the requests in the `Authorization` header.

The GraphQL interface can be viewed in detail using a number of tools. The following is a list of recommended tools that support exploring GraphQL endpoints:

-   Altair GraphQL Client
-   Postman
-   Insomnia
-   GraphQL Playground


All of these tools exploring the GraphQL interface in a similar way. Before you use one of the tools, you need the following:

-   The GraphQL endpoint of your business data graph.
-   An OAuth bearer token for your business data graph to send as the `Authorization` header.

> ### Sample Code:  
> ```
> POST https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/graphql
> Authorization: Bearer <bearer token>
> ```



<a name="loiode723090712e4d3dafab951b89b88faf__section_limitations"/>

## Limitations

For the lastest list of limitations when using the GraphQL schema in Graph, see [Limitations](https://github.com/cap-js/graphql?tab=readme-ov-file#limitations).

**Related Information**  


[GraphQL.Org](https://graphql.org/)

[CAP GraphQL Protocol Adapter](https://github.com/cap-js/graphql#readme)

[Altair GraphQL Client](https://altairgraphql.dev/)

[Postman: Querying with GraphQL](https://learning.postman.com/docs/sending-requests/graphql/graphql/)

[Insomnia: GraphQL Queries](https://docs.insomnia.rest/insomnia/graphql-queries)

[GraphQL Playground](https://github.com/graphql/graphql-playground)

[The Graph OData V4 API](the-graph-odata-v4-api-79162b2.md "Graph supports the OData v4 protocol to access business data graphs.")

