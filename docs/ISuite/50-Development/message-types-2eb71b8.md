<!-- loio2eb71b84b55f4269a5379f6efe9a6f3a -->

# Message Types

Cloud Integration allows you to view your imported Message Types along with their referenced data types.

A message type comprises a [data type](data-types-97ad101.md) that describes the structure of a message. For technical reasons, a data type alone is not sufficient to describe the instance of a message. Data types are defined in XML Schema as abstract types that aren't yet tied to an element. You can only describe an instance of a message when you've specified a data type. Therefore, a message type defines the root element of a message.



<a name="loio2eb71b84b55f4269a5379f6efe9a6f3a__section_kxs_34p_mxb"/>

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

Displays category of the node. It can be an *Element* or *Attribute*.

> ### Note:  
> The difference between elements and attributes is that attributes dont have any child node, and you can't use the same attribute more than once in an element.



</td>
</tr>
<tr>
<td valign="top">

Type



</td>
<td valign="top">

Displays the referenced [data type](data-types-97ad101.md) assigned to the root node and built-in data type \(decimal, string, or integer\) of the child nodes.



</td>
</tr>
<tr>
<td valign="top">

Occurrence



</td>
<td valign="top">

Determines how often elements occur. For attributes, the possible value is *Optional* or *Required*.



</td>
</tr>
<tr>
<td valign="top">

Restrictions



</td>
<td valign="top">

Displays the of the value range of a node.



</td>
</tr>
</table>

Choose a row to view the [Element Details](data-types-97ad101.md#loio97ad10142fc34269902006e488af1eff__table_xtn_yqp_l5b).



<a name="loio2eb71b84b55f4269a5379f6efe9a6f3a__section_djw_j4p_mxb"/>

## Overview

From Cloud Integration Web UI you can view the following general details of a Message Type:

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

Name of the Message Type



</td>
</tr>
<tr>
<td valign="top">

ID



</td>
<td valign="top">

Displays the unique ID of the artifact



</td>
</tr>
<tr>
<td valign="top">

XML Namespace



</td>
<td valign="top">

Displays the namespace to which Message Type belongs to or where it's created.



</td>
</tr>
<tr>
<td valign="top">

Data Type Used & Data Type's Package



</td>
<td valign="top">

Displays the data type of this message type and name of the package in which the data type exists.



</td>
</tr>
<tr>
<td valign="top">

Version



</td>
<td valign="top">

Current version of message type.



</td>
</tr>
<tr>
<td valign="top">

Created On & Created By



</td>
<td valign="top">

User who created the artifact and when it's created.



</td>
</tr>
<tr>
<td valign="top">

Description



</td>
<td valign="top">

Displays the description associated with the Message Type, if any.



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
    -   Core and aggregated data types are based on Core Components Technical Specification \(CCTS\) specification and are the basis for application-specific data types accepted across the businesses.




</td>
</tr>
</table>



<a name="loio2eb71b84b55f4269a5379f6efe9a6f3a__section_u2d_k4p_mxb"/>

## XSD

Displays the XML Schema Definition \(XSD\) that is, the text view of the message type in read-only mode.

**Related Information**  


[Message Mapping](message-mapping-459ccdf.md "")

