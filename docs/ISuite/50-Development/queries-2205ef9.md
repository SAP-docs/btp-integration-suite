<!-- loio2205ef90295b45cc9622fe85dea745eb -->

# Queries

Queries in GraphQL build on fields and arguments.

Fields represent the properties of an entity. Only fields that are specified in a query are returned by the API \(similar to `$select` in OData\). Arguments are additional options that can be passed in a query to modify the expected response by, for example paginating, filtering, or sorting.

The specification of fields and arguments works on the root level of a query, but are also deeply nested. This enables traversing the data graph and specifying exactly the data that should be returned by the API.

The GraphQL interface that Graph exposes is structured similar to the OData interface, and is capable of the same query features.

```
query {
  <namespace> {
    <entity> (
      top: <number>,
      skip: <number>,
      filter: [
        {
          <field>: {
            <contains, endswith, eq, ge, gt, le, lt, ne, startswith>: [<filter values>]
          }
        },
        ...
      ],
      orderBy: [
        {
          <field>: <asc or desc>
        }
      ]
    ) {
      nodes {
        <field>
        ...
      }
    }
  }
}

```

> ### Note:  
> The body of list queries always needs to be wrapped within `nodes { }`. The same applies when querying for nested to-many relationships.

As the period-character has a special meaning in GraphQL, any occurrence of it is replaced with the underscore \(`_`\) character in the namespace of a GraphQL request.



<a name="loio2205ef90295b45cc9622fe85dea745eb__section_gdw_gcv_mvb"/>

## Example - Query with Token-Based Pagination and Sorting

In the `sap.s4` namespace, read 10 `A_Product` entities skipping the first 10 and ordering by the`Product` field in ascending order selecting the following fields:

-   `Product`

-   `Brand`

-   `CountryOfOrigin`




### GraphQL

```
query {
  sap_s4 {
    A_Product (
      top: 10,
      skip: 10,
      orderBy: [
        { Product: asc }
      ]
    ) {
      nodes {
        Product
        Brand
        CountryOfOrigin
      }
    }
  }
}
```



### OData Equivalent

```
https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/<bdg identifier>/sap.s4/A_Product?$top=10&$skip=10&$select=Product,Brand,CountryOfOrigin&$orderby=Product asc
```



<a name="loio2205ef90295b45cc9622fe85dea745eb__section_l4l_wqy_xwb"/>

## Example - Query with Nested To-Many Query

In the `sap.s4` namespace, read 10 `A_Product` entities skipping the first 10, selecting the following fields:

-   `Product`

-   `ProductType`

-   `ProductDescription` from the extended `to_Description`




### GraphQL

```
query {
  sap_s4 {
    A_Product (
      top: 10,
      skip: 10,
      orderBy: [
        { Product: asc }
      ]
    ) {
      nodes {
        Product
        ProductType
        to_Description {
          nodes {
            ProductDescription
          }
        }
      }
    }
  }
}
```



### OData Equivalent

```
https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/<bdg identifier>/sap.s4/A_Product?$top=10&$skip=10&$select=Product,ProductType&$expand=to_Description($select=ProductDescription)
```

