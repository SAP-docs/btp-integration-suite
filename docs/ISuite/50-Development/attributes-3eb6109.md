<!-- loio3eb61094d6674178beb9726e3a8e0990 -->

# Attributes

The guidelines for attribute names and attribute types.

<a name="loio68627239a5be455d93c5d6173e2b202d"/>

<!-- loio68627239a5be455d93c5d6173e2b202d -->

## Attribute Names

Attribute names start with a lowercase letter and use lower camelCase, with only ASCII alphanumeric characters and underscores.

Attribute names must be precise and unambiguous in defining the semantics, interpreted in the context of an entity. For example, an entity `Student` has an attribute age, rather than `studentAge`. By convention, acronyms remain in capital letters, such as `baseURL`, except at the beginning of the name: `iataCode`.

Custom entities should be designed to have only one unique key attribute, by convention called `id`. We also recommend to have an additional attribute called `displayId`, which is the preferred value to display on UIs. Often, `id` and `displayId` map to the same source attribute value, but since Graph uses the `id` field to encode additional \(opaque\) information, it shouldn't be used for UIs.

<a name="loio38ca8c48464048efb22635f8b07fc78f"/>

<!-- loio38ca8c48464048efb22635f8b07fc78f -->

## Attribute Types

When creating a custom entity, you can use several kinds of attributes.

Graph's supported attribute types are a subset of the core data services types. For more information, see [Core Data Services \(CDS\) primitive types](https://cap.cloud.sap/docs/cds/types).



<a name="loio38ca8c48464048efb22635f8b07fc78f__section_wfp_r2q_dvb"/>

## Primitive

Primitive attributes are the simplest unstructured attributes, usually of type `String` or `Integer`. Primitive attribute names are singular. Primitive attributes that are `Boolean` should be named as positive and prefixed with a modal or auxiliary verb like *is*, *can*, or *has*. For example, `isActive` rather than `isInactive` or `active`.



<a name="loio38ca8c48464048efb22635f8b07fc78f__section_c4d_v2q_dvb"/>

## Structured

You can group certain attributes as a structure. A good example is attributes that together form an address. You can create a structured attribute by specifying the attribute name using a dotted path. Each path segment adds an additional nesting layer. For example:

```
{
  "entity": "bestrun.Customer",
  "attributes": [
    { "name": "address.street", "source": ["Street"] },
    { "name": "address.city", "source": ["City"] },
    { "name": "address.zip", "source": ["ZipCode"] }
  ]
}

```

`address` and `zip` are path-segments. Clients see the data as a nicely nested JSON object. For example:

```
  :
  address: {
    street: "Main Street";
    city: "Plains";
    zip: "44345";
  }
  :

```

> ### Note:  
> Graph doesn't support *Composition of one*, which would yield a similar result.



<a name="loio38ca8c48464048efb22635f8b07fc78f__section_gf2_z2q_dvb"/>

## Arrays of Primitive Values

Arrays of primitive values can be defined using the `arrayFill` transform. Attribute names that represent an array are plural, and must be followed by open and closed square brackets `[]` as a suffix. For example, `children[]` or `contacts[]`. The array base type is inferred from the source's first entry, but can be overwritten by the `property` type. All primitive types are allowed.

```
{
  "entity": "bestrun.Customer",
  "attributes": [
    { "name": "tags[]", "transform": "arrayFill", "source": ["Tag1", "Tag2", "Tag3"], "type": "String(21)" }
  ]
}

```



<a name="loio38ca8c48464048efb22635f8b07fc78f__section_grw_cfq_dvb"/>

## Compositions of Many \(Arrays of Sub-Entities\)

A composition is an attribute that represents a nested array of a structured type, a contained subentity, with a whole-and-parts semantics: the subentity doesn’t exist without the whole part. Examples are the list of items on a sales order, or the chapters of a book. Most existing data sources and APIs don't support compositions and just use foreign keys or associations to another entity, without highlighting the whole-and-parts semantics of the composition. Composition names are plural, and must be followed by open and closed square brackets `[]` as a suffix.

As a modeler of a Graph custom entity, you can represent whole-and-parts semantics correctly as a real composition, as follows:

-   Specify a `[]` following the path segment that becomes the composition attribute, with a source property that represents a foreign key \(association to many\). Don't specify a transform or type.

-   Specify the composition substructure, attribute by attribute, using the same name syntax, and adding the attribute as a path segment.

-   Mark at least one subentity attribute as a key.


The following example shows an attribute, called `addresses`, which is an inline composition of many addresses.

```
{
  "entity": "bestrun.Customer",
  "attributes": [
    { "name": "addresses[]","source": ["to_Addresses[]"] },
    { "name": "addresses[].id", "source": ["to_Addresses[].AddressID"], "key": true },
    { "name": "addresses[].street", "source": ["to_Addresses[].Street"] },
    { "name": "addresses[].city", "source": ["to_Addresses[].City"] }
  ]
}

```



<a name="loio38ca8c48464048efb22635f8b07fc78f__section_l3j_ffq_dvb"/>

## Compositions of Many Different Data Source APIs

In the *Compositions of Many \(Arrays of Sub-Entities \)* section, the composition attribute and the subentity are linked in the same data source API, and a foreign key exists in the data source. You can also create a composition where the subentity is part of a different API, possibly even in a different system. This could be the case, for example, when an extension application was created side by side with the main application.

If there is no foreign key or *Association to many* in the data source, a slightly different syntax must be used. Use the join transform for the composition attribute, with an explicit `sourceEntity` and without a source. Subsequent composition substructure attributes are specified as before, but since their source is in a different `sourceEntity`, it must be explicitly specified. Here's an example:

```
{
  "entity": "bestrun.Customer",
  "sourceEntities": [
    { "name": "sap.s4.A_Customer" },
    { "name": "sap.s4.A_BusinessPartnerAddress", "join": [["Customer", "BusinessPartner"]] }
  ],

  "attributes": [
    { "name": "addresses[]", "transform": "join", "sourceEntity": "A_BusinessPartnerAddress" },
    { "name": "addresses[].id", "source": ["AddressID"], "sourceEntity": "A_BusinessPartnerAddress", "key": true },
    { "name": "addresses[].street", "source": ["Street"], "sourceEntity": "A_BusinessPartnerAddress" },
    { "name": "addresses[].city", "source": ["City"], "sourceEntity": "A_BusinessPartnerAddress" }
  ]
}

```



<a name="loio38ca8c48464048efb22635f8b07fc78f__section_k2p_3fq_dvb"/>

## Associations to-One

Associations are relations based on an equality match of an underlying attribute \(sometimes called the *foreign key*\) with the key of the associated target entity. For example, you can model an association from a `Class` to one `Teacher` in your source model. The foreign key is defined as a string. For composite keys, the associating entity must have corresponding foreign keys in the source entity.

By convention, association to-one attribute names are singular, and prefixed with an underscore.

To describe an association:

-   Specify `Association` as the type and specify the `associationTarget` as a reference to the full entity name that your association points at.

-   Add a path-segment mapping to the attribute name for each key of the association target with a corresponding source.


The target entity usually has only one key, as in the following example:

```
{
  "entity": "bestrun.SalesOrder",
  "attributes": [
    {"name": "_sellTo", "type": "Association", "associationTarget": "sap.s4.A_Customer"}
    {"name": "_sellTo.Customer", "source": ["soldToParty"] } // Customer is the name of the key in A_Customer
  ]
}

```



<a name="loio38ca8c48464048efb22635f8b07fc78f__section_chr_nfq_dvb"/>

## Associations to-Many

An association to-many is a relationship to many target records that match on their key attribute. Such an association requires the existence of a corresponding to-one association in the other direction \(a backlink\).

![](images/Modeling_Reference_44dd2ab.png)

To create an association to-many, you specify `Association` as the type and use the `on` clause to specify the to-one association \(backlink\) attribute in the target entity. Association to-many attribute names are plural, followed by open and closed square brackets `[]`. And by convention, they are prefixed with an underscore `_`.

```
"entity": "Teacher",
:
"attributes": [
   { "name": "_classes[]", "type": "Association", "associationTarget": "my.new.Class", "on": "_teacher" }
:

```

