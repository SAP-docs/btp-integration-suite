<!-- loio499950b547dc453e8605727bec44747b -->

# Mutations

While queries focus on reading data from the API, mutations allow data to be modified by creating, updating, or deleting it.

The schema for mutations looks like this:

```
mutation {
  <namespace> {
    <entity> {
      create (
        input: {
          <field>
          ...
        }
      ) {
        <field>
        ...
      }

      delete (
        filter: [
          {
            <field>: {
              <contains, endswith, eq, ge, gt, le, lt, ne, startswith>: [<filter values>]
            }
          },
          ...
        ]
      )

      update (
        input: {
          <field>
          ...
        },
        filter: [
          {
            <field>: {
              <contains, endswith, eq, ge, gt, le, lt, ne, startswith>: [<filter values>]
            }
          },
          ...
        ]
      ) {
        <field>
        ...
      }
    }
  }
}
```

`Create` mutations specify the entity body as the input argument of the create field. Additionally, the fields that are queried from the created entity are specified in the body of the create field.

`Delete` mutations specify a filter for selecting the entities to be deleted. All entities matching the specified filters are deleted. It returns the count of deleted entities.

`Update` mutations specify the entity body to be updated as the input argument of the update field. Additionally, the filter field specifies one or more multiple filter expressions to select the entities to be updated. Finally, the fields that are queried from the updated entities are specified in the body of the update field.



<a name="loio499950b547dc453e8605727bec44747b__section_sxz_z2v_mvb"/>

## Examples



### Example 1

Create `A_Product` in the `sap.s4` namespace.

```
mutation {
  sap_s4 {
    A_Product {
      create (
        input: {
          Brand: "...",
          CountryOfOrigin: "...",
          ...
        }
      ) {
        Product
        Brand
        CountryOfOrigin
        ...
      }
    }
  }
}
```



### Example 2

Delete `A_Product` entities filtering on the `Product` field to be equal to `1` in the `sap.s4` namespace.

```
mutation {
  sap_s4 {
    A_Product {
      delete (
        filter: [
          {
            Product: { eq: "1" }
          }
        ]
      )
    }
  }
}
```



### Example 3

Update `A_Product` entities on the `Brand` and `CountryOfOrigin` fields filtering on the `Product` field to start with 10 and querying the `Product`, `Brand`, and `CountryOfOrigin` fields.

```
mutation {
  sap_s4 {
    A_Product {
      update (
        input: {
          Brand: "...",
          CountryOfOrigin: "..."  
        },
        filter: [
          {
            Product: { startswith: "10" }
          }
        ]
      ) {
        Product
        Brand
        CountryOfOrigin
      }
    }
  }
}
```

