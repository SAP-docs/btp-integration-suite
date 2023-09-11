<!-- loio97ad10142fc34269902006e488af1eff -->

# Data Types

Cloud Integration allows you to view your imported Data Types.

Data Type is an object, containing the structure of data that defines the message. A data type is defined using XML Schema Definition Language \(XSDL\).



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

Determines how often elements occur. For attributes the possible value is *Optional* or *Required*.



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

Choose a row to view the following details:

**Element Details**


<table>
<tr>
<th valign="top">

Facet



</th>
<th valign="top">

Meaning



</th>
</tr>
<tr>
<td valign="top" colspan="2">

**Properties**



</td>
</tr>
<tr>
<td valign="top">

Name



</td>
<td valign="top">

Displays the name of the selected node



</td>
</tr>
<tr>
<td valign="top">

Category



</td>
<td valign="top">

Displays the category of the selected node



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

Namespace



</td>
<td valign="top">

Displays the namespace to which the parent artifact of the selected node belongs to or where it's created.



</td>
</tr>
<tr>
<td valign="top">

Package Name

\(appears only if the Type is reference to an existing data type\)



</td>
<td valign="top">

Displays the name of the package for referenced data type.



</td>
</tr>
<tr>
<td valign="top">

MinOccurs & Maxoccurs



</td>
<td valign="top">

Specify the minimum and maximum occurrence of an an element



</td>
</tr>
<tr>
<td valign="top">

Description



</td>
<td valign="top">

Displays description of the node.



</td>
</tr>
<tr>
<td valign="top" colspan="2">

**Restrictions**



</td>
</tr>
<tr>
<td valign="top">

enumeration



</td>
<td valign="top">

Restricts the value range to a set of individual values.



</td>
</tr>
<tr>
<td valign="top">

fractionDigits



</td>
<td valign="top">

Specifies the number of places permitted after the comma.



</td>
</tr>
<tr>
<td valign="top">

length, maxLength, minLength



</td>
<td valign="top">

Exact \(length\), maximum \(maxLength\), or minimum \(minLength\) length of a data type.



</td>
</tr>
<tr>
<td valign="top">

maxExclusive, maxInclusive



</td>
<td valign="top">

Upper limit for the value set exclusive \(maxExclusive\) or inclusive \(maxInclusive\) of the specified value. The value of this facet doesn't exceed the value range of the data type that is restricted by the facet.



</td>
</tr>
<tr>
<td valign="top">

minExclusive, minInclusive



</td>
<td valign="top">

Lower limit for the value set exclusive \(minExclusive\) or inclusive \(minInclusive\) of the specified value. The value of this facet does not exceed the value range of the data type that is restricted by the facet.



</td>
</tr>
<tr>
<td valign="top">

pattern



</td>
<td valign="top">

Specifies a pattern for string-based data types. The pattern has the form of a regular expression that describes a set of appropriate character sequences.



</td>
</tr>
<tr>
<td valign="top">

totalDigits



</td>
<td valign="top">

Specifies the total number of digits in a number. The value is only xsd: positiveInteger type.



</td>
</tr>
<tr>
<td valign="top">

whiteSpace



</td>
<td valign="top">

Specifies how white-space character \(line feed, tabs, blanks, and carriage returns\) is applied. It has three values:

preserve: Retains all white-space characters.

replace: Replaces every line feed, tab, and carriage return with a blank.

collapse: As for replace but subsequent blanks are replaced by a single blank and leading, final blanks are deleted.



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

Name of the Data Type



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

User who created the data type and when it's created.



</td>
</tr>
<tr>
<td valign="top">

Description



</td>
<td valign="top">

Displays the description associated with the data type, if any.



</td>
</tr>
<tr>
<td valign="top">

ES Repository Information



</td>
<td valign="top">

-   Software Component Version: Displays the software component version from which the data type is referenced.
-   Classification: Displays the data type classification as:
    -   Free-style data types are based on the primitive data types and they don't need any further parameters to define themselves. For example: Decimal, String, Integer, and so on.
    -   Core and aggregated data types are based on Core Components Technical Specification \(CCTS\) and are the basis for application-specific data types accepted across the businesses.




</td>
</tr>
</table>



<a name="loio97ad10142fc34269902006e488af1eff__section_r5l_g4p_mxb"/>

## XSD

Displays the XML Schema Definition \(XSD\) that is, the text view of the data type in read-only mode.

**Related Information**  


[Message Types](message-types-2eb71b8.md "Cloud Integration allows you to view your imported Message Types along with their referenced data types.")

