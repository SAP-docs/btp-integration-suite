<!-- loiocec1e73284394e8095c101457317f172 -->

# Transform Functions

Transform functions are used to define custom projection attributes.

The following transforms are supported. The descriptions below start from the primary direction, `GET` \(read\) data. Changing data is in the other direction, from the custom-entity to the data source.

> ### Note:  
> All transforms are bidirectional.


<table>
<tr>
<th valign="top">

transform

</th>
<th valign="top">

Parameters \(source property\)

</th>
<th valign="top">

Description

</th>
<th valign="top">

Resulting Default Type

</th>
</tr>
<tr>
<td valign="top">

`rename`

</td>
<td valign="top">

Value is adjusted and renamed

</td>
<td valign="top">

Renames and translates the value according to the type specifications in the corresponding models. Applies type conversions as required.

</td>
<td valign="top">

Same as source, or as indicated by type

</td>
</tr>
<tr>
<td valign="top">

`arrayFill`

</td>
<td valign="top">

Two or more attributes

</td>
<td valign="top">

Creates an array of primitive types

</td>
<td valign="top">

array

</td>
</tr>
<tr>
<td valign="top">

`bool`

</td>
<td valign="top">

An attribute name, true and false values

</td>
<td valign="top">

Converts a pair of values into a boolean

</td>
<td valign="top">

Boolean

</td>
</tr>
<tr>
<td valign="top">

`toDateTime`

</td>
<td valign="top">

Date and time values

</td>
<td valign="top">

Combine date and time attributes into one attribute of type `DateTime` 

</td>
<td valign="top">

DateTime

</td>
</tr>
<tr>
<td valign="top">

`constant`

</td>
<td valign="top">

Constant value to be assigned

</td>
<td valign="top">

Produces a constant value

</td>
<td valign="top">

Same as source, or as indicated by type

</td>
</tr>
<tr>
<td valign="top">

`join`

</td>
<td valign="top">

None

</td>
<td valign="top">

Specify a composition without an underlying foreign key

</td>
<td valign="top">

Composition to-many

</td>
</tr>
<tr>
<td valign="top">

`dict`

</td>
<td valign="top">

Dictionary and value

</td>
<td valign="top">

Uses a dictionary to map source values to or from custom values

</td>
<td valign="top">

String

</td>
</tr>
<tr>
<td valign="top">

`keyConcat`

</td>
<td valign="top">

Two or more source attributes

</td>
<td valign="top">

Concatenates a key-value into a single key-value in a reversible way

</td>
<td valign="top">

String or overrule by type

</td>
</tr>
<tr>
<td valign="top">

`localized`

</td>
<td valign="top">

Association, language-selector, and text field

</td>
<td valign="top">

Produces a localized string, when the string is from a language-indexed string table

</td>
<td valign="top">

String

</td>
</tr>
<tr>
<td valign="top">

`negation`

</td>
<td valign="top">

Attribute value to be negated

</td>
<td valign="top">

Negation of boolean value

</td>
<td valign="top">

Boolean

</td>
</tr>
<tr>
<td valign="top">

`stringConcat`

</td>
<td valign="top">

Two or more attributes

</td>
<td valign="top">

Concatenates multiple source attributes into a single string

</td>
<td valign="top">

String with length, sum of source string lengths

</td>
</tr>
</table>



<a name="loiocec1e73284394e8095c101457317f172__section_qlm_pmy_nvb"/>

## Default Property

When the transform property isn't specified, `rename` is assumed. If no source is specified, the attribute is a type conversion of the attribute of the same name in the \(main\) source entity.

```
{ "name": "firstName", "source": "FirstName" } // rename "FirstName" to "firstName", inferred type. is from source
{ "name": "FirstName" } // implied source is also called "FirstName"

```



<a name="loiocec1e73284394e8095c101457317f172__section_axt_34q_dvb"/>

## `rename`

The `rename` transform is the simplest and most common. As its name implies, the `rename` transform only provides an attribute renaming and a type conversion to SAP [Core Data Services \(CDS\) primitive types](https://cap.cloud.sap/docs/cds/types). An optional type property overrides the default type conversion.



<a name="loiocec1e73284394e8095c101457317f172__section_ent_54q_dvb"/>

## `bool`

Returns the result of comparing the source attribute value to the provided values. If the value matches the true value \(`YES` in the following example\), the transform returns true, if the value is null, the transform returns null, else false.

When changing data, the boolean values true and false are converted to the values specified as source parameters in the attribute-mapping object.

```
{ "name": "isOrderBlocked", "transform": "bool", "source": ["OrderIsBlocked", "YES", "NO"] },
```



<a name="loiocec1e73284394e8095c101457317f172__section_vzy_z4q_dvb"/>

## `negation`

The translated value is the logical NOT of the source boolean attribute value \(true<=\>false, "null" <=\> "null"\). Negating a source attribute of nonboolean type results in an error.



<a name="loiocec1e73284394e8095c101457317f172__section_ppy_bpq_dvb"/>

## `constant`

The transform returns a constant value, for example, an empty string.

```
{ "name": "theAnswer", "transform": "constant", "source": [42]
```



<a name="loiocec1e73284394e8095c101457317f172__section_bbr_ypq_dvb"/>

## `dict`

The transform uses a dictionary to translate source values, often values in a number range, to a string. In the following example, an SAP S/4HANA numeric category is translated to a list of meaningful string values, found in the `BPCategories` object of the dicts header object.

```

"dicts": {
   BPCatDict: { "person": "1", "organization": "2", "group": 3, "other": "3" } 
},

"attributes": [
   { "name": "Relation", "source": ["BPCatDict", "BusinessPartnerCategory"] }


```

The first source is a reference to an entry in the `dicts` structure found in the same translation file. The second source is the actual SAP S/4HANA source attribute. In this example, reading a source value of `2` results in the `organization` value. Writing the `person` value actually writes `1`.

The last element of a dictionary is always the default value, if the `a to b` transformed value doesn't match other entries in the dictionary. For example, if the value of `BusinessPartnerCategory` is `7`, the value returned by the transform is `other`. If the value to be transformed is null, the returned value is also null.



<a name="loiocec1e73284394e8095c101457317f172__section_inr_wyv_dvb"/>

## `join`

The join transform is used to specify a composition of-many attribute, referencing another source entity, without the use of an underlying foreign key \(or association attribute\) in the data source. Instead, the composed sub-entity is expected to have keys that match those of the custom entity where the composition is defined.

This is useful if the subentity originates from a different API, possibly even a different system. Most commonly, when an extension application is created side by side with the main application, on the basis of common keys.

Use the join transform for the composition attribute, with an explicit `sourceEntity` and without a source. Subsequent composition substructure attributes are specified as before, but since their source is in a different `sourceEntity`, it must be explicitly specified. Here's an example:

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



<a name="loiocec1e73284394e8095c101457317f172__section_shx_2zv_dvb"/>

## `arrayFill`

The arrayFill transform creates a simple array of a primitive type, from individual source attributes.

```
{ "name": "phones[]", "transform": "arrayFill", "source": ["mobile1", "mobile2", "homePhone"], "type": "String(10)" }
```



<a name="loiocec1e73284394e8095c101457317f172__section_yww_hzv_dvb"/>

## `stringConcat`

This transform has two or more parameters. The transform provides a simple concatenation of source values, without any \(space\) fillers.

In the other direction, the transform breaks the string up according to the precise sizes of the corresponding source-attributes.

A real-world example is a 13-digit `GLN`\(Global Location Number\), split back into 7+5+1 digits. Another real-world example is a `source` field with a limited string length and an `overflow` field.

```
{ "name": "myGLN", "transform": "stringConcat", "source": ["prefix", "locationRef", "checkDigit"], "type": "String(13)" }
```



<a name="loiocec1e73284394e8095c101457317f172__section_jt4_mzv_dvb"/>

## `keyConcat`

This transform concatenates multiple source attributes into a single string, using the following algorithm:

1.  All source strings are scanned to find a character that isn't used in any value.

2.  This becomes the first char of the concatenated string and also the separation character.


To write such a string back, reverse decoding is followed. If str1=abc;d and str2 is f-12, then a concatenated string might be: Aabc;dAf-12.

A common use is to translate a multi-attribute \(composite\) primary key to a single-attribute primary key, which is why this transform is called a keyConcat.

```
"name": "id", "transform": "keyConcat", "source": ["EntityId", "SystemId"], "key": true},
```



<a name="loiocec1e73284394e8095c101457317f172__section_ogk_31w_dvb"/>

## `localized`

This transform has three parameters:

1.  Name of the reference attribute \(the association to the string table\).

2.  Name of the field in the string table used to encode the required language \(usually a two or three character field\).

3.  Name of the field with the desired local string value


The transform returns a localized string. A typical use is when the source API provides texts in all available languages, and the Graph API only provides a single text in the `HTTP Content-Language` of the response. Implementation-wise, Graph knows the preferred language of the client application user via the `HTTP Accept-Language` header in the query. This hides the complexity of language-specific string handling from the developer. When the `HTTP Accept-Language` header isn't in the request, `en` \(English\) is the assumed default.

An example of reading a data source, expressed using CDS is as follows:

```
entity A_Product {
  key Product: String(40);
  to_Description: Association(*) to A_ProductDescription { Product, Language };
}
  
entity A_ProductDescription {
  key Product: String(40);
  key Language: String(2);
  ProductDescription: String(40);
};

```

The translation has the following parameters:

```
name: "displayId", source: ["to_Description[]", "Language", "ProductDescription"]
```

> ### Note:  
> The other direction \(such as an update\) of such attributes is supported.



<a name="loiocec1e73284394e8095c101457317f172__section_iyx_dfw_dvb"/>

## `toDateTime`

This transform has two parameters: the source time and date attributes.

The provided value is the date and time source attributes combined into an attribute of type `dateTime`.

```
{ "name": "dateTime", "transform": "toDateTime", "source": ["DateProp", "TimeProp"] },
```

