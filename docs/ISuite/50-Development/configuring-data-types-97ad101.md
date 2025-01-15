<!-- loio97ad10142fc34269902006e488af1eff -->

# Configuring Data Types

Data Type is an object, containing the structure of data that defines the message. A data type is defined using XML Schema Definition Language \(XSDL\).

Cloud Integration allows you to view and [edit](editing-data-type-7136a31.md) your data types.



<a name="loio97ad10142fc34269902006e488af1eff__section_yvy_nnp_mxb"/>

## Structure

The nodes are represented in a hierarchical manner using indents with the following information:

****


<table>
<tr>
<th valign="top">

Entry

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Name of the node.

</td>
</tr>
<tr>
<td valign="top">

Category

</td>
<td valign="top">

Displays category of the node. For root node, it can be *Simple Type* or *Complex Type*. For child nodes, it can be *Elements* and *Attributes*.

> ### Note:  
> The difference between elements and attributes is that attributes don't have any child node, and you can't use the same attribute more than once in an element.



</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Displays a built-in data type \(example string, decimal, or integer\) or reference to an existing data type for an element or attribute.

</td>
</tr>
<tr>
<td valign="top">

Occurrence

</td>
<td valign="top">

Determines how often elements occur.

</td>
</tr>
<tr>
<td valign="top">

Restrictions

</td>
<td valign="top">

Displays the restriction of the value range of a built-in data type for simple data types, elements, or attributes.

</td>
</tr>
</table>



<a name="loio97ad10142fc34269902006e488af1eff__section_zgr_fnp_mxb"/>

## Overview

From Cloud Integration Web UI you can view the following general details of a Data Type:

****


<table>
<tr>
<th valign="top">

Entry

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Name of the Data Type.

</td>
</tr>
<tr>
<td valign="top">

ID

</td>
<td valign="top">

Displays the unique ID of the artifact.

</td>
</tr>
<tr>
<td valign="top">

Namespace

</td>
<td valign="top">

Displays the namespace to which Data Type belongs to or where it's created.

</td>
</tr>
<tr>
<td valign="top">

Version

</td>
<td valign="top">

Current version of data type.

</td>
</tr>
<tr>
<td valign="top">

Created On & Created By

</td>
<td valign="top">

Displays the identity of the user who imported the data type and the date when it was imported.

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Displays the description associated with the data type, if any. User who created the data type and when it's created.

</td>
</tr>
<tr>
<td valign="top">

ES Repository Information

</td>
<td valign="top">

-   Software Component Version: Displays the software component version to which the data type belongs to in ES repository.
-   Classification: Displays the data type classification as:
    -   Free-style data types are based on the primitive data types and they don't need any further parameters to define themselves. For example: Decimal, String, Integer, and so on.
    -   Core and aggregated data types are based on Core Components Technical Specification \(CCTS\) and are the basis for application-specific data types accepted across the businesses.




</td>
</tr>
</table>



<a name="loio97ad10142fc34269902006e488af1eff__section_r5l_g4p_mxb"/>

## XSD

Displays the XML Schema Definition \(XSD\) that is, the text view of the data type in read-only mode. To download this XML schema to a file, choose *Export*.

**Related Information**  


[Configuring Message Types](configuring-message-types-2eb71b8.md "A message type comprises a data type that describes the structure of a message. For technical reasons, a data type alone is not sufficient to describe the instance of a message. Data types are defined in XML Schema as abstract types that aren't yet tied to an element. You can only describe an instance of a message when you've specified a data type. Therefore, a message type defines the root element of a message.")

