<!-- loio2eb71b84b55f4269a5379f6efe9a6f3a -->

# Configuring Message Types

A message type comprises a [data type](configuring-data-types-97ad101.md) that describes the structure of a message. For technical reasons, a data type alone is not sufficient to describe the instance of a message. Data types are defined in XML Schema as abstract types that aren't yet tied to an element. You can only describe an instance of a message when you've specified a data type. Therefore, a message type defines the root element of a message.

Cloud Integration allows you to view and edit your message types along with its referenced data types.



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

> ### Note:  
> The name of the root node is the same as the message type.



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

Displays the referenced [Configuring Data Types](configuring-data-types-97ad101.md) assigned to the root node and built-in data type \(decimal, string, or integer\) of the child nodes.

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

Displays the of the value range of a node.

</td>
</tr>
</table>

You can view following additional details of a message type.

In message types, only root nodes can be edited and only the user-defined data type can be modified. To do so, choose *Edit* and then select the node to populate the details in the right-hand side panel.

**Element/Attribute Details**


<table>
<tr>
<th valign="top">

Field

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

Data Type Used

</td>
<td valign="top">

To assign another user-defined data type, choose *Select*. Choose the integration packages from which you wish to list the data types and select the one to be used. The structure of the selected data type gets loaded in the tree table.

> ### Note:  
> You can edit the referenced data type of the root node only.



</td>
</tr>
<tr>
<td valign="top">

Namespace

</td>
<td valign="top">

Displays the namespace to which the referenced data type belongs to or where it's created.

</td>
</tr>
<tr>
<td valign="top">

Package Name

</td>
<td valign="top">

Displays the package name of the user-defined data type assigned to the node.

</td>
</tr>
<tr>
<td valign="top">

Default

</td>
<td valign="top">

Displays the default value defined for the node.

</td>
</tr>
<tr>
<td valign="top">

Occurrence

\(appears only if the selected node is an Attribute\)

</td>
<td valign="top">

Displays *required* or *optional*.

</td>
</tr>
<tr>
<td valign="top">

MinOccurs & Maxoccurs

\(appears only if the selected node is an Element\)

</td>
<td valign="top">

Displays the minimum and maximum occurrence of an element.

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Displays the description of the selected node.

</td>
</tr>
</table>

**Saving Message Types**

Choose *Save* to save the draft. Choose *Save as version* to save the message type with a new version. All modifications are also reflected in the XSD tab.

> ### Note:  
> You can save the artifact even if you have validation errors in your structure tab.

The displayed value range [restrictions](editing-data-type-7136a31.md#loio7136a3141d294a8a86884a3b03aad5b4__table_xtn_yqp_l5b) can't be edited for Message Types.



<a name="loio2eb71b84b55f4269a5379f6efe9a6f3a__section_djw_j4p_mxb"/>

## Overview

From Cloud Integration Web UI you can view the following general details of a Message Type. To edit the referenced data type or namespace, choose *Edit*.

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

Displays the name of the Message Type. The name of the root node is the same as the Message Type.

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

You can edit the existing namespace or define a new one if it's not already created.

</td>
</tr>
<tr>
<td valign="top">

Data Type Used & Data Type's Package

</td>
<td valign="top">

Displays the data type of this message type and name of the package in which the data type exists.

Choose *Select* to assign a new data type to refer to from the displayed list of data types. All the related fields are updated. The Structure and XSD schema of the Message type is also updated in the respective tabs.

> ### Note:  
> Data Type of only the root node can be edited.



</td>
</tr>
<tr>
<td valign="top">

Version

</td>
<td valign="top">

Displays the current version of message type.

</td>
</tr>
<tr>
<td valign="top">

Created On & Created By

</td>
<td valign="top">

Displays the identity of the user who imported the data type and the date when it was imported

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

-   Software Component Version: Displays the software component version to which the Message Type belongs to in ES repository.
-   Namespace: Displays the ES repository namespace where the Message Type is created.



</td>
</tr>
</table>



<a name="loio2eb71b84b55f4269a5379f6efe9a6f3a__section_u2d_k4p_mxb"/>

## XSD

Displays the XML Schema Definition \(XSD\) that is, the text view of the message type in read-only mode. To download this XML schema to a file, choose *Export*.

**Related Information**  


[Message Mapping](message-mapping-459ccdf.md "")

