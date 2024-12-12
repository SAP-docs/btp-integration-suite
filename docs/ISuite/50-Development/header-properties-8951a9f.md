<!-- loio8951a9f2cb57421a8d3c638050042c2e -->

# Header Properties

A list of header properties that can be found in project definition files.



<a name="loio8951a9f2cb57421a8d3c638050042c2e__section_c2d_d22_cvb"/>

## `label`

A short description of the custom entity that is used in metadata documentation.



<a name="loio8951a9f2cb57421a8d3c638050042c2e__section_smm_l22_cvb"/>

## `entity`

The full name of the custom entity. For example:

```
"entity": "bestrun.financials.Receipt"
```

In this example,`bestrun.financials` is the namespace, and `Receipt` is the entity name.



<a name="loio8951a9f2cb57421a8d3c638050042c2e__section_km5_s22_cvb"/>

## `version`

The current semantic version of the custom entity, using a [semver](https://semver.org/) convention. Using this convention, the format of this property value is `major.minor.patch`. The major version number is incremented to indicate an incompatible change. The minor version is incremented for new backwards-compatible functionality, and the patch number is incremented to indicate a bug fix, documentation change, or other small improvement.

A data graph can only contain one version of a custom entity, but different data graphs can use different versions of the custom entity.

```
"version": "1.0.5" // major version 1, patch 5
```



<a name="loio8951a9f2cb57421a8d3c638050042c2e__section_gpj_z22_cvb"/>

## `sourceEntities`

Custom entities are constructed from attributes, which are mapped to mirrored data source entity attributes. The `sourceEntities` array property lists the mirrored entities whose attributes are used in these mappings.

> ### Note:  
> Only mirrored projection entities can be specified as data source entities. It is not possible to recursively define a custom entity as a mapping of another custom or unified entity.

Most custom entities only require one source entity. Complex, composed custom entities can have two or more source entities. The first or only source entity is referred to as the *main source* entity, and is the default one if none is specified in an attribute mapping. The subsequent source entities are defined via a join property of the corresponding source attributes that have matching instance values.

Each source entity is described as an object with the following structure:


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

`name` 

</td>
<td valign="top">

String

</td>
<td valign="top">

Yes

</td>
<td valign="top">

The full name of the source entity. Like the custom entity, the source entity name must be fully qualified, including the namespace.

The first `sourceEntity` in the array is the default.

</td>
</tr>
<tr>
<td valign="top">

`join` 

</td>
<td valign="top">

Array

</td>
<td valign="top">

Yes

</td>
<td valign="top">

This property doesn't apply to the first, default source entity, but must be present in all nondefault source entity objects. It consists of one or more pairs of primary key attributes, which indicate how the instances of the source entity match the main source entity. The first item in the pair is the name of a source key attribute in the main source entity and the second is the corresponding key attribute name in the current source entity. For example:

```
"join": [["BusinessPartner", "Customer"]] 
```

indicates that the `Customer` key in this source entity corresponds to the `BusinessPartner` key in the main source entity. If more than one pair is specified, they must both match:

```
"sourceEntities": [
  { "name": "my.course" },
  { "name": "my.classRoom", "join": [["subject", "Subject"], ["teacher", "Teacher"]] }
]

```

This is interpreted as:`my.course.subject = my.classRoom.Subject AND my.course.teacher = my.classRoom.Teacher`

</td>
</tr>
</table>

Here's an example of a complex `sourceEntities` property:

```
"sourceEntities": [
    { "name": "sap.s4.A_BusinessPartnerRole" },
    { "name": "sap.s4.A_BusinessPartner", "join": [["BusinessPartner", "BusinessPartner"]] },
    { "name": "sap.s4.A_BusinessPartnerContact", "join": [["BusinessPartner", "BusinessPartnerPerson"]] }
  ],

```

> ### Note:  
> Custom entities based on multiple data sources can't be written atomically, since data changes involve multiple systems, which can't guarantee an atomic transaction. The approach Graph takes is to allow developers to change \(write, update\) only the non read-only attributes of the main data source \(the first one in the list\). Attributes from the source entity, that is not a main source entity, cannot be written and are always read-only, whether explicitly declared so in an annotation, or not. Deleting a custom entity instance only deletes the corresponding underlying main source entity, but not the other source entities.



<a name="loio8951a9f2cb57421a8d3c638050042c2e__section_ynt_cl2_cvb"/>

## `dicts`

The dicts objects contain dictionary objects. Each dictionary object is a simple value mapping. For example, a certain data source attribute is defined as a single digit, 1, 2, … 5 representing five enumeration values, from poor to excellent. Modelers can replace the numeric values by defining them as follows:

```
"dicts": {
     "qualityDict": { "poor": "1", … "excellent":  "5", "not rated": "0" }
}

```

The last entry in the dictionary is the default value, when no other value matches. For more information, see the dict transform in [Transform Functions](transform-functions-cec1e73.md).



<a name="loio8951a9f2cb57421a8d3c638050042c2e__section_vxz_rq2_cvb"/>

## `annotations`

A list \(object\) of annotation properties. You can use the following optional properties:

-   `description` \(String\)

    A comprehensive description of the entity, used in metadata documentation.

-   `readonly` \(boolean, default is false\)

    True if the custom entity is treated as read-only.


