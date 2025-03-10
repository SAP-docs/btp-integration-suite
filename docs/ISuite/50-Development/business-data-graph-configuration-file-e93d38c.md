<!-- loioe93d38c976b147b390df68b06d1a461d -->

# Business Data Graph Configuration File

The business data graph configuration file is a JSON file that specifies the configuration of a specific business data graph in a landscape.

The configuration file consists of five parts:

1.  Graph model version

2.  Business data graph identifier

3.  Data sources

4.  Locating policy

5.  Extensions


Each of these parts can be modified before the configuration file is activated. You don't need to write this file from scratch. You can generate a defaultGraph configuration file after selecting destinations in your landscape from Graph on the Integration Suite home page.



<a name="loioe93d38c976b147b390df68b06d1a461d__section_b51_5qp_zqb"/>

## Graph Model Version

The Graph model version is the latest version of Graph's unified API entities. When generating the configuration, the version is set to the latest available graph model version, for example 1.0.0.



<a name="loioe93d38c976b147b390df68b06d1a461d__section_xpn_1rp_zqb"/>

## Business Data Graph Identifier

The identifier is what developers use in the Graph URL to access the business data graph:

```json
https://<subdomain>.a.integration.cloud.sap/graph/api/<bdgid>/<resources>?<options>...
```

The business data graph identifier is useful to distinguish multiple business data graph specifications within a single landscape or to manage changes of the business data graph over time. It must be a short string of up to 20 lowercase alphanumeric characters and hyphen separators. For example, `abc-xyz-123mn`.



<a name="loioe93d38c976b147b390df68b06d1a461d__section_qm1_frp_zqb"/>

## Data Sources

The data sources section of the configuration file lists the services \(APIs\) that are configured as destinations in the landscape by the SAP BTP administrator. When you first generate a default configuration file, the list of data sources is automatically discovered from the destination service instances in the SAP BTP subaccount. The list is displayed when the new business data graph is created.

An example of the format for the `dataSources` section is as follows:

```json
"dataSources": [ 
      { "name": "s4_1", "services": [ 
        { "destinationName": "s4a-bupa" }, 
        { "destinationName": "s4a-product" }, 
        { "destinationName": "s4a-sales-order" }, 
        ...   
      ] }, 
      { 
        "name": "cx_sales",
        "services": [ { "destinationName": "c4c-odata" } 
      ] },
      {
        "name": "custom",
        "namespace": "company.custom",
        "services": [ { "destinationName": "custom-odata" }
      ] }, 
      ...  
],
```

You can change the data source names \(`s4_1`, and `cx_sales` in the example\) to any name you like, but we recommend keeping them short. These names appear in the response payload of key-based references as key qualifiers. Don’t change the names of the service destinations, because they must match the names of the destinations in your SAP BTP subaccount. You can comment out or delete a destination that you don’t want to expose to the developers and applications that access data in this landscape.



### Custom Services

The namespace for entities of custom OData services must be explicitly specified in the data source namespace property. For example, Graph automatically discovers custom OData services as shown in the data sources code example. A data source and corresponding locating rule are added to the generated graph configuration. The `CustomProduct` entity of the `custom-odata` service is available in the business data graph using the following path:

```json
https://<subdomain>.a.integration.cloud.sap/api/<bdgid>/company.custom/CustomProduct
```

You don't need to specify a namespace for SAP systems known by Graph. For more information, see [Connect to Your Business Systems](connect-to-your-business-systems-1a0dd22.md).



### Path \(Optional\)

> ### Tip:  
> It's recommended to use the path parameter when working with a business system with multiple OData services.

In a business data graph configuration file, you can add an optional path to the URL of a destination configured in SAP BTP. It's useful when the destination is defined as a general root URL by the SAP BTP administrator, but the actual service API is located relative to that root.

A typical use case is the connection to an SAP S/4 HANA business system. Instead of maintaining multiple SAP BTP destinations for the same business systems, the SAP BTP administrator can create a single SAP BTP destination using the root URL. The Graph key user then edits the business data graph configuration file to include a path to each individual service before the business data graph is activated. For example, if the host URL is `https://sandbox.api.sap.com`, the configuration of the SAP BTP destination looks like this:

```
URL=https://sandbox.api.sap.com/s4hanacloud/sap/opu
Name=sandbox-s4
Type=HTTP
...
```

The URL consists of the host `https://sandbox.api.sap.com` and the root service path `/sap/opu`.

Using the following path parameter, the services of the data source can reuse the SAP BTP destination:

```

"dataSources": [
  {
    "name": "s4",
    "services": [
      {
        "destinationName": "sandbox-s4",
        "path": "/odata/sap/API_BUSINESS_PARTNER"
      },
      {
        "destinationName": "sandbox-s4",
        "path": "/odata4/sap/api_bank/srvd_a2x/sap/bank/0002"
      },
      {
        "destinationName": "sandbox-s4",
        "path": "/odata/acme/API_CUSTOM"
      }
    ]
  }
],
```

The first entry of this example is an OData v2 service for the `Business Partner` entity. The full URL is resolved as: `https://sandbox.api.sap.com/s4hanacloud/sap/opu/odata/sap/API_BUSINESS_PARTNER`.

The second entry is an OData v4 service for the `Bank` entity. The full URL is resolved as:`https://sandbox.api.sap.com/s4hanacloud/sap/opu/odata4/sap/api_bank/srvd_a2x/sap/bank/0002`.

The third entry is a custom OData v2 service using a custom namespace `acme` instead of the default `sap` namespace. The full URL is resolved as: `https://sandbox.api.sap.com/s4hanacloud/sap/opu/odata/acme/API_CUSTOM`.



<a name="loioe93d38c976b147b390df68b06d1a461d__section_dmq_trp_zqb"/>

## Locating Policy

The locating policy provides Graph with the information to determine where requested data is located. For an introduction to this topic, see [Data Locating Policy](data-locating-policy-28d2c2c.md).

The default configuration file generated by Graph contains an initial policy recommendation derived from the list and types of systems in the landscape. It's also derived from heuristics based on common enterprise landscapes. You can, and sometimes must, change this default template to match your actual landscape strategy.

The format for the locating policy is as follows:

```json
"locatingPolicy": { 
  "cues": [ … ],
  "keyMapping": [ … ], 
  "rules": [ … ] 
} 
```

Each cue used in the rules must be defined in the cues array. A cue has the following form:

```json
{
  "name": "…",
  "description": "…",
} 
```

Each key mapping required for the rules must be defined in the `keyMapping` array. Each key mapping has the following form:

```
{
  "foreignKey": {
    "dataSource": "…",
    "entityName": "…",
    "attributes": [ … ],
    "strategy": {
      "name": "format",
      "match": "…",
      "replace": "…"
    }
  },
  "references": {
    "dataSource": "…",
    "entityName": "…",
    "attributes": [ … ],
    "strategy": {
      "name": "format",
      "match": "…",
      "replace": "…"
    }
  }
}
```

The following table summarizes the aspects of a key mapping:


<table>
<tr>
<th valign="top">

Tag

</th>
<th valign="top">

Required

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

dataSource

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

The name of the data source as defined in the `dataSources` section.

</td>
</tr>
<tr>
<td valign="top">

entityName

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

A fully qualified entity name, including namespace, for example `sap.s4.A_Product`.

</td>
</tr>
<tr>
<td valign="top">

attributes

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

The attribute, that identifies the entity in the other data source. Currently, only a single attribute is supported.

</td>
</tr>
<tr>
<td valign="top">

strategy

</td>
<td valign="top">

Optional

</td>
<td valign="top">

Strategy used to select the correct entity.

</td>
</tr>
</table>

The strategy has the following fields:


<table>
<tr>
<th valign="top">

Tag

</th>
<th valign="top">

Required

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

name

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

The name of the strategy, currently only "format" is supported.

</td>
</tr>
<tr>
<td valign="top">

match

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

Specific to strategy "format". A regular expression to extract the parts of the attribute value. Use named capturing groups to identify each part. For more information on the supported regular expression syntax, see [RE Syntax](https://github.com/google/re2/wiki/Syntax).

</td>
</tr>
<tr>
<td valign="top">

replace

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

Specific to strategy "format". A pattern of the referenced attribute value. Use `$<name>` to reference the values of the capturing groups used in `match` \(keep \`<\` and \`\>\`\). Every name used in `replace` must occur in `match`.

</td>
</tr>
</table>

Each locating rule applies to one entity, or, via a wildcard, to multiple entities, and has the following format:

```json
{ "name": "…", "leading": "…", "local": [ … ], "cues": [ … ] }
```

Multiple rules can be defined for the same entity, as long as all but one of the rules has cues. A rule without cues is the default rule for that entity. A well-formed policy has one default rule for each entity in the business data graph. This is easy to achieve by using wildcard rules. A data source must appear only once in a rule.

The following table summarizes the aspects of a locating rule:


<table>
<tr>
<th valign="top">

Tag

</th>
<th valign="top">

Required

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

name

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

Entity name, including a namespace, that the rule applies to. An asterisk \* \(wildcard\) applies to all the entities in this namespace.

</td>
</tr>
<tr>
<td valign="top">

leading

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

Name of the data source that is the leading system for this entity.

</td>
</tr>
<tr>
<td valign="top">

local

</td>
<td valign="top">

Optional

</td>
<td valign="top">

List of data sources, where key-based references to this entity are treated as local references, overriding the leading system.

</td>
</tr>
<tr>
<td valign="top">

sourceEntity

</td>
<td valign="top">

Optional

</td>
<td valign="top">

The full name of the mirrored source entity for which the rule applies. It's only applicable to composite custom entities.

</td>
</tr>
</table>



### Cues \(Optional\)

The sets of cues defined for different rules matching the same entity must be disjoint. That is while a specific cue may appear in different rules for different entities, it must not appear in more than one rule for the same entity:

```json
{"name": "E1", "leading": "…", "cues": ["xyz"]},
{"name": "E2", "leading": "…", "cues": ["xyz", "abc"]}, // ok, "xyz" may appear in rules for E1 and E2
{"name": "E2", "leading": "…", "cues": ["mnq", "abc"]}  // error, "abc" cannot appear in two rules for E2
```

For examples of how to define locating policies for different landscape architectures, see [Configuration Strategies - Use Cases](configuration-strategies-use-cases-3652dcb.md).



### Key Mapping \(Optional\)

Key mapping must be configured to support navigation from one data source \(the local, or referencing system\) to another \(the leading, or referenced system\) for the same entity if different keys are used in the two systems.

For example, you have a `SalesQuote` in system A, with an `item` that refers to a `Product` with key K. This key refers to the local \(system A\) product catalog, but what if you want an application to access the `Product` information in the leading system B? A common example is when the application needs access to a 360° view of an entity, starting from a unified entity. For example, the application might run a request with a resource like: `sap.graph/SalesQuote/21687/item/10/_product/_s4/…` or `sap.graph/SalesQuote/21687/item/10/_product/_c4c/…`. If these two systems don't use the same key, then a key mapping must be defined between them to enable these requests.

In the following example, you have two data sources, one called `myS4`, the other called `myC4C`. The `myS4` data source is the natural source of truth for product information, and is therefore used as the leading system for `sap.graph.Product`, and of course also for `sap.s4.A_Product`.

The entity `sap.c4c.ProductCollection` has the foreign key called `ExternalID`, which Graph uses to access `sap.s4.A_Product` in the data source `myS4`. This is declared in the `keyMapping` section as `foreignKey`.

The referenced `sap.s4.A_Product` has the key attribute `Product` that is referenced by the foreign key. This is declared in the section `references` with a local key from the `myS4` data source, Graph references the `sap.c4c.ProductCollection` in the `myC4C` data source.

```
"locatingPolicy": {
  "keyMapping": [
    {
      "foreignKey": {
        "dataSource": "myC4C",
        "entityName": "sap.c4c.ProductCollection",
        "attributes": ["ExternalID"]
      },
      "references": {
        "dataSource": "myS4",
        "entityName": "sap.s4.A_Product",
        "attributes": ["Product"]
      }
    }
  ],
  "rules": [
    { "name": "sap.s4.*", "leading": "myS4" },
    { "name": "sap.c4c.*", "leading": "myC4C" },
    { "name": "sap.graph.*", "leading": "myS4", "local": ["myC4C"] },
    { "name": "sap.graph.SalesQuote", "leading": "myC4C", "local": ["myS4"] },
    { "name": "sap.graph.Product", "leading": "myS4", "local": ["myC4C"] }
  ]
}
```

The foreign key enables Graph to translate between the different keys and allows you to fetch the `_c4c` and `_s4` representations of the `sap.graph.SalesQuote` using the previously described requests that include the `_c4c` and `_s4` navigations.

Assume that the last locating rule is changed for the `sap.graph.Product`, as follows:

```
{ "name": "sap.graph.Product", "leading": "myS4" }
```

By removing `myC4C` from the `local` list, Graph is configured to always translate product IDs from `myC4C` to `myS4`. A request such as `sap.graph/SalesQuote/21687/item/10/?$expand=_product` returns an `sap.graph.SalesQuote` populated with data from the respective leading system `myC4C` with a nested `sap.graph.Product` populated with data from the leading system `myS4`. Because `myC4C` isn't listed in `local` for the locating rule of `sap.graph.Product`, Graph uses the defined foreign key to translate the reference.





### Key Mapping with Format Translation \(Optional\)

To extend the key mapping use case, sometimes the foreign key attribute has a different format than the referenced key attribute. In this case, Graph must know the different key notations that exist between data sources and how to convert the values. To achieve this, Graph requires a *Key Format Translation* to link the identical entities. The `keyMapping` must contain a `strategy` to transform the keys in both directions. For more information about the supported regular expression syntax, see [RE2 Syntax](https://github.com/google/re2/wiki/Syntax).



### Composite Custom Entity Rules

Custom entities are composed of several different source entities, originating from different data sources.

In such cases, you need to unambiguously inform Graph of the origin of each source entity. You do this by specifying separate locating rules for source entities that originate from a data source other than the main source entity \(that is, the first item in the `sourceEntities` array of the projection file\). This is done by providing additional rules with the `sourceEntity` property specified.

For example, consider a custom entity `bestrun.Product` composed of a main source entity `sap.s4.A_Product`, and a secondary source entity `company.custom.CustomProduct`. Then, you specify one locating rule per source entity:

```
{
  "name": "bestrun.Product",
  "leading": "s4",
  "sourceEntity": "sap.s4.A_Product" // Optional, since it is the main source entity.
},
{ // An additional rule is required, since the second source entity has a different leading system.
  "name": "bestrun.Product",
  "leading": "custom",
  "sourceEntity": "company.custom.CustomProduct"
}
```

For the main source entity and any other source entities originating from the same data source, the `sourceEntity` property can be omitted, and no other additional rules are required.

If source entity-specific rules aren't provided for composite custom entities with source entities originating from different data sources, then the resulting entity is partially available, with the properties omitted from the secondary systems.



<a name="loioe93d38c976b147b390df68b06d1a461d__section_yds_qkz_2zb"/>

## Exclude Mirror Entities

All available source entities are automatically added to the exposed graph. To exclude these mirrored entities from your business data graph, you can add the property `exclude`. This removes a defined list of mirrored entities completely from the exposed API. They cannot be queried and all associations linking to them are removed. The removed entities can still be used as a data source for entities in the unified model and for custom projections. Only mirrored entities can be removed, not elements of the unified model or custom entities.

The exclude property is a list of expression strings. They are matched against the entity name with the namespace prefix.

```
"exclude": ["sap.s4.A_Product", "sap.c4c.*"]
```

For example, `sap.s4.A_Product`. These expressions can contain an asterisk `*` at the end as a wildcard like `sap.s4.*`.

**Related Information**  


[Create a Business Data Graph in Integration Suite](create-a-business-data-graph-in-integration-suite-42daf3b.md "As a Graph Key User, you can create a new business data graph. You can also use an existing configuration file to create a business data graph.")

[Extend Your Business Data Graph](extend-your-business-data-graph-bb4f072.md "To extend your business data graph, you can create model extensions that describe your custom entity projections.")

[Configuration Strategies - Use Cases](configuration-strategies-use-cases-3652dcb.md "The strategy of configuring Graph starts with the question of what exactly is a landscape?")

