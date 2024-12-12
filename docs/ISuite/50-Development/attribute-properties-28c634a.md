<!-- loio28c634acc884470c8b7591b17b2b899e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Attribute Properties

A list of attribute properties that can be found in project definition files.



<a name="loio28c634acc884470c8b7591b17b2b899e__section_f53_vfq_dvb"/>

## `name`

The name of the new attribute. For example:

```
lastName 		// attribute of scalar type at root level
mainAddress.country 	// primitive attribute country in a sub-structure mainAddress
addresses[] 		// to-many composition on root level (or array if the source attribute is defined as an array)
addresses[].country 	// primitive property country in to-many composition (or array) addresses

```



<a name="loio28c634acc884470c8b7591b17b2b899e__section_jcz_xfq_dvb"/>

## `key`

Indicates that this attribute, called `id`, is the entity key. Custom entities must have exactly one key at the root level, and convention dictates that you should call this key `id`. We also recommend to introduce an attribute called `displayId`, which provides a human-friendly version of the key, even if they share the same source.

```
{ "name": "id", "key": true, "source": ["Product"], type: String(70) } // rename "Product" to key "id"
{ "name": "displayId", "source": ["Product"], type: String} 

```



<a name="loio28c634acc884470c8b7591b17b2b899e__section_zgt_1gq_dvb"/>

## `source`

The source attribute for the transform, which is an array of one or more parameters. When both the source and transform are not specified, the default of the source is the same `name` in the source entity.

```
{ "name": "firstName", "source": ["FirstName"] } // rename "FirstName" to "firstName", inferred type is from source
{ "name": "FirstName" } // implied source is also called "FirstName" 

```



<a name="loio28c634acc884470c8b7591b17b2b899e__section_rq1_dgq_dvb"/>

## `sourceEntity`

The full name of the mirrored source entity to which this attribute mapping applies. The first source entity in the `sourceEntities` header property is used as the default source entity.



<a name="loio28c634acc884470c8b7591b17b2b899e__section_i42_ggq_dvb"/>

## `type`

This optional property defines the type of the custom entity attribute. If not specified, the default type is inferred from the mapped source attribute or the specified transform. The type attribute can be used as a typecast to overwrite the default. Graph supports two versions of `String` and `Decimal`. The `String` type doesn't provide a max-length \(expressed as a character count\) intentionally, but you can specify a maximal string length, as in `String(10)`. Similarly, the `Decimal` type can be specified explicitly with a precision and scale, as in `Decimal(5,2)`. Date and time formats follow [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601).

The following are supported types \(type names are capitalized\):


<table>
<tr>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

String

</td>
<td valign="top">

String of unspecified length.

</td>
<td valign="top">

Alphanumeric text

</td>
</tr>
<tr>
<td valign="top">

String \(length\)

</td>
<td valign="top">

String of maximum length; longer strings are truncated.

</td>
<td valign="top">

Alphanumeric text

</td>
</tr>
<tr>
<td valign="top">

Integer

</td>
<td valign="top">

A whole number.

</td>
<td valign="top">

`52` 

</td>
</tr>
<tr>
<td valign="top">

Decimal

</td>
<td valign="top">

A whole and fractional number.

</td>
<td valign="top">

`17.63` 

</td>
</tr>
<tr>
<td valign="top">

Decimal \(precision, scale\)

</td>
<td valign="top">

A decimal value witha specification of precision and scale.

</td>
<td valign="top">

`Decimal(3,2) => 7.56` 

</td>
</tr>
<tr>
<td valign="top">

Boolean

</td>
<td valign="top">

Boolean values.

</td>
<td valign="top">

True, False

</td>
</tr>
<tr>
<td valign="top">

Date

</td>
<td valign="top">

Date as yyyy-mm-dd.

</td>
<td valign="top">

`2016-01-24` 

</td>
</tr>
<tr>
<td valign="top">

DateTime

</td>
<td valign="top">

Date and time as yyyy-mm-dd T hh:mm:ss.

</td>
<td valign="top">

`2016-11-24T16:11:45` 

</td>
</tr>
<tr>
<td valign="top">

Time

</td>
<td valign="top">

Time as hh:mm:ss.

</td>
<td valign="top">

`16:11:45` 

</td>
</tr>
<tr>
<td valign="top">

Timestamp

</td>
<td valign="top">

High-precision date and time.

</td>
<td valign="top">

`2016-11-24 16:11:32.4209753` 

</td>
</tr>
<tr>
<td valign="top">

Association

</td>
<td valign="top">

Association, specified with the `associationTarget` property.

</td>
<td valign="top">



</td>
</tr>
</table>

Example:

```
{ "name": "FirstName", "type": "String" } // implied source is also called "FirstName", overrides source type "String(127)".
```

> ### Note:  
> All values \(unless the attribute is explicitly defined as non-null\) can have a null value. For example, an attribute of type Boolean can be true, false, or null.

**Conversion Types**


<table>
<tr>
<th valign="top">

To

From

</th>
<th valign="top">

String

</th>
<th valign="top">

String \(L\)

</th>
<th valign="top">

Integer

</th>
<th valign="top">

Decimal

</th>
<th valign="top">

Boolean

</th>
<th valign="top">

Date

</th>
<th valign="top">

DateTime

</th>
<th valign="top">

Time

</th>
<th valign="top">

Time Stamp

</th>
</tr>
<tr>
<td valign="top">

`String` 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> \(3\)

</td>
<td valign="top">

\(1\)

</td>
<td valign="top">

Must be an integer.

</td>
<td valign="top">

Must match a decimal.

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> \(2\)

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> \(2\)

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> \(2\)

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> \(2\)

</td>
</tr>
<tr>
<td valign="top">

`Integer` 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
</tr>
<tr>
<td valign="top">

`Decimal` 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
</tr>
<tr>
<td valign="top">

Boolean

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
</tr>
<tr>
<td valign="top">

`Date` 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
</tr>
<tr>
<td valign="top">

`DateTime` 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
</tr>
<tr>
<td valign="top">

`Time` 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
</tr>
<tr>
<td valign="top">

`TimeStamp` 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#BB0000;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
</tr>
</table>

\(1\) When reading, the string value is returned as is, and may, therefore, exceed the length. When writing, the operation fails when an attempt is made to write a string that is larger than the defined type.

\(2\) String must match ISO date\(time\) format, based on [Date.parse\(\)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/parse). Timestamps are expected in UTC time zone. Nonmatching date/time formats are changed to null.

\(3\) `key` attributes, and the corresponding associations are treated as opaque local strings, and translated into *Qualified ID \(QID\)* format. A QID is a local ID or reference with a qualifier. When returning a response to a client, Graph adds a qualifier to each local ID and reference that it receives from a business system. When it receives a request from a client for a data item with a qualified reference, it removes the qualifier before sending the request to the business system.



<a name="loio28c634acc884470c8b7591b17b2b899e__section_rq4_mlq_dvb"/>

## `transform`

This property specifies the transformation function for the attribute value of the custom entity. The parameters of the transform are described by the source property. For more information, see [Transform Functions](transform-functions-cec1e73.md).



<a name="loio28c634acc884470c8b7591b17b2b899e__section_d4g_4lq_dvb"/>

## `annotations`

A list \(object\) of annotation properties. The following optional properties can be used:

-   `description` \(string\) - a comprehensive description of the attribute that is used in metadata documentation.

-   `readonly` \(boolean, default is false\): true if the attribute is treated as read-only.


