<!-- loiofab3489ae4d74acb983ebfd8908810df -->

# Projection Definition File Format

Custom entities are specified in JSONC files that follow the projection definition file format.

Technically, a custom entity definition is a single JSON object following the projection definition file format and governed by a JSON validation schema. By convention, each custom entity definition is stored separately in a `JSONC` file, which allows the use of comments.

> ### Note:  
> Download this [schema file](https://help.sap.com/doc/custom-entity-projection/PROD/en-US) to create and validate your projection file.

Here's an example of a projection definition file with one custom entity, `bestrun.Customer`, which is a projection on the mirrored `A_Customer` entity:

```
1	{
2	 
3	  "label": "example",
4	  "entity": "bestrun.Customer", // the name of the new custom entity
5	  "version": "1.0.0",
6	
7	  "sourceEntities": [ { "name": "sap.s4.A_Customer" } ],
8
9	  attributes: [
10	    // …
11	    { "name": "paysOnTime",   "transform": "negation",  "source": [ "isBlocked" ] },   
12	    { "name": "displayId",    "transform": "rename",    "source": [ "customerName" ] },
13	    { "name": "country.code", "transform": "rename",    "source": [ "countryCode" ] }, // flat to structured 
14	    { "name": "country.name", "transform": "rename",    "source": [ "countryName" ] },
15	    { "name": "monikers",     "transform": "arrayFill", "source": [ "PrimaryName","AlternativeName" ] },  
16	    // …
17	  ]
18	}

```

A custom entity definition consisting of two parts:

-   A header with several header key-value pairs

-   Attributes with an array of objects


The following header properties are supported:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Type

</th>
<th valign="top">

Mandatory

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`label` 

</td>
<td valign="top">

String

</td>
<td valign="top">

Yes

</td>
<td valign="top">

A short description of the entity, which is used in metadata documentation.

</td>
</tr>
<tr>
<td valign="top">

`entity` 

</td>
<td valign="top">

String

</td>
<td valign="top">

Yes

</td>
<td valign="top">

The full name of the custom entity.

</td>
</tr>
<tr>
<td valign="top">

`version` 

</td>
<td valign="top">

Semver

</td>
<td valign="top">

Yes

</td>
<td valign="top">

The current semantic version of the custom entity.

</td>
</tr>
<tr>
<td valign="top">

`sourceEntities` 

</td>
<td valign="top">

Array

</td>
<td valign="top">

Yes

</td>
<td valign="top">

An array of one or more data source entities, used in attribute mappings.

</td>
</tr>
<tr>
<td valign="top">

`dicts` 

</td>
<td valign="top">

Object

</td>
<td valign="top">

No

</td>
<td valign="top">

A list of dictionaries, used to map source values to or from custom values. For more information, see [Transform Functions](transform-functions-cec1e73.md).

</td>
</tr>
<tr>
<td valign="top">

`annotations` 

</td>
<td valign="top">

Object

</td>
<td valign="top">

No

</td>
<td valign="top">

A list of annotation properties.

</td>
</tr>
</table>

The `attributes` property is an array of mapping-specification objects. Each object represents the mapping specification for a single attribute of the custom entity. That is, it describes a transform from source attributes of a specific `sourceEntity` to a custom entity attribute with a new name and data type. The transform specification is the essence of creating custom entities.

The following attribute properties are supported:

****


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Type

</th>
<th valign="top">

Mandatory

</th>
<th valign="top">

Description

</th>
<th valign="top">

Default

</th>
</tr>
<tr>
<td valign="top">

`name` 

</td>
<td valign="top">

String

</td>
<td valign="top">

Yes

</td>
<td valign="top">

The name of the new attribute.

</td>
<td valign="top">

Not applicable

</td>
</tr>
<tr>
<td valign="top">

`key` 

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

No

</td>
<td valign="top">

Set to true if this attribute \(called `id`\) is the key of the entity.

</td>
<td valign="top">

False

</td>
</tr>
<tr>
<td valign="top">

`source` 

</td>
<td valign="top">

array

</td>
<td valign="top">

No

</td>
<td valign="top">

The source attribute of the corresponding `sourceEntity`.

</td>
<td valign="top">

If the transform is `rename`, then the default is a source attribute with the same name. Not specified for type=`Association` or transform=`join`. In all other cases, specifying a source is mandatory.

</td>
</tr>
<tr>
<td valign="top">

`sourceEntity` 

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

The source entity used.

</td>
<td valign="top">

The first in the list of`sourceEntities`.

</td>
</tr>
<tr>
<td valign="top">

`type` 

</td>
<td valign="top">

enum

</td>
<td valign="top">

No

</td>
<td valign="top">

The type of new attribute.

</td>
<td valign="top">

Type is taken from the source or the transform, or is set explicitly.

</td>
</tr>
<tr>
<td valign="top">

`transform` 

</td>
<td valign="top">

enum

</td>
<td valign="top">

No

</td>
<td valign="top">

One of several transformation functions.

</td>
<td valign="top">

`rename` 

</td>
</tr>
<tr>
<td valign="top">

`on` 

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

The specification expression of an attribute of type `Association to-many`.

</td>
<td valign="top">

Must appear in to-many associations.

</td>
</tr>
<tr>
<td valign="top">

`associationTarget` 

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

The target entity name of an attribute `Association`.

</td>
<td valign="top">

Must appear in associations.

</td>
</tr>
<tr>
<td valign="top">

`annotations` 

</td>
<td valign="top">

object

</td>
<td valign="top">

No

</td>
<td valign="top">

A list of annotation properties.

</td>
<td valign="top">



</td>
</tr>
</table>

