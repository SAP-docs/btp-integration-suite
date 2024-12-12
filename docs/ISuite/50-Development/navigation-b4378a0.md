<!-- loiob4378a0d02f74928920ecb65d4a411fa -->

# Navigation

Unlike the data models found in SAP's business systems, the data model of Graph is highly interconnected. This ensures that developers develop highly efficient code for navigating across the systems, without being concerned about where the data originated.

Graph reference attributes enable navigation through SAP-managed data. For example, a sales order contains references to the customer, and to the products ordered. A purchase order includes references to the requisition owner and organization, to materials ordered, recommended vendors, includes and more.

The following describes the metadata of a `SalesOrder`:

```json
{
  id:		key string(70)
  displayId: 	string(10)
  orderType: 	string(4)
  soldToParty: 	string(10)
  _soldToParty: 	sap.graph/Customer
  paymentTerms: 	string(4)
  items: 		array
}
```

A `SalesOrder` has a key, called `id`, and a variety of attributes. Note the `_soldToParty` attribute. This is a reference, or association to a `Customer`. It's used to navigate across the business data graph, for example, obtain the name of the customer for this `SalesOrder` in a single efficient request.

```json
GET https://<subdomain>.a.integration.cloud.sap/graph/api/v1/SalesOrder/14/_soldToParty/name
```

Without these navigation attributes, this would have required two OData calls, plus some logic to extract the value of `_soldToParty` from the first response and interpret it as a key in the second call.



<a name="loiob4378a0d02f74928920ecb65d4a411fa__section_pn1_35w_5rb"/>

## Cross-system Navigation

Enterprises commonly have the same data in more than one data source. They're referred to as *multi-source entities*. They can occur for a number of reasons:

-   Overlapping data models \(for example, multiple data sources have product catalogs or concepts of person\).

-   Intentional replication from one system to another, to optimize and simplify local access and references.

-   Partitioning of the same type of data over multiple systems \(of the same type\) based on data-specific criteria.

-   Traversal of data from one system to another because of lifetime workflows.


Within a single data source, such references are local references: they refer to unique identifiers \(keys\) of the referenced objects. However, navigating across systems, there's the problem that the same data object has one local key in one system and another in a second system. A reference is to a local or external key.

As a developer, you use Graph to navigate and access SAP-managed data, regardless of where this data resides. Graph accesses the data on your behalf, so you don't have to deal with these complexities.

Graph must solve the following data-locating challenges on behalf of client applications:

1.  Which data source can provide the data that the application wants to access? If the data is in more than one data source, which one is accessed?

2.  Is the reference to the data applicable for a cross-system reference?


These problems are particularly challenging, because Graph makes no assumptions about:

-   The customer's landscape

-   How keys are allocated or defined, uniquely, immutable or not.

-   How data is replicated or distributed, consistently or not.


Graph is configured with a locating policy, and makes references to globally unique entities by adding a source-specific prefix to local key references. For example, the key `14` of an entity in a certain data source, and all its references, appear as `s4hq~14`. In most cases, this is opaque to client application developers.



### Cues

Locating data under such conditions isn't always a simple decision: client apps sometimes need the data from one system, and sometimes from another, based on application-specific considerations.

*Cues* are used to overwrite the default data source in the landscape, by adding them as OData query options. A common use case is when the same type of data, for example sales orders, is managed in two different systems, because different sales territories: European sales in oneSAP S/4HANA instance, and North American sales in another. To address this, the key user who configured the landscape policy, may have added a differentiating cue to the appropriate rules for locating sales data, allowing applications to issue a request like:

```json
GET https://<subdomain>.a.integration.cloud.sap/graph/api/v1/SalesOrder/14/items?cue=NA
```

This request overrides the default of European sales. The use of cues, a type of landscape-specific convention, must of course be communicated to the developers of client applications. Technically, a cue is just an alphanumeric string, or in the form of string=string \(alphanumeric\). Only a single cue can be provided for any query. This cue only applies to the root entity of the query.

