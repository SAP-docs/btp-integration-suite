<!-- loio6dfaa7a0bfad42d59c59095ddfc4734b -->

# Configuring Fault Message Type

Fault message types are designed for application-specific errors that occur at the provider \(inbound side\) and that are reported back to the sender or persisted in monitoring.

A Fault Message Type consists of the following:

-   **Standard Data \(default\)**: This data type is used to return the fault message standard information for an error at runtime. All fault message types reference the data type `ExchangeFaultData` for this and, indirectly, the data type `ExchangeLogData`. These data types are automatically created in a namespace when you create the first fault message type there.
-   **Additional Data \(optional\)**: This data type is used to attach any additional application-specific information to the fault message. To do so, import the dependent data types while importing from ESR repository, see [Import Fault Message Type Artifact from Enterprise Service Repository](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/creating-fault-message-type?state=CLOUD&ai=true#import-fault-message-type-artifact-from-enterprise-service-repository). Else, assign a data type from the structure or overview tabs.



<a name="loio6dfaa7a0bfad42d59c59095ddfc4734b__section_djw_j4p_mxb"/>

## Overview

From Cloud Integration Web UI you can view the following general details of a message type. To edit the referenced data type or namespace, choose *Edit*.

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

Displays the name of the fault message type. The name of the root node is the same as the artifact.

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

Displays the namespace to which fault message type belongs to or where it's created.

You can edit the existing namespace or define a new one if it's not already created.

</td>
</tr>
<tr>
<td valign="top">

Data Type Used & Data Type's Package

</td>
<td valign="top">

Displays the additional data type referenced in the fault message type and name of the package in which the data type exists.

Choose *Select* to select and assign a new data type from the integration packages of this tenant. All the related fields are updated. The Structure and XSD schema of the fault message type is also updated in the respective tabs.

> ### Note:  
> Data Type of only the 'addition' node can be edited.



</td>
</tr>
<tr>
<td valign="top">

Version

</td>
<td valign="top">

Displays the current version of fault message type.

</td>
</tr>
<tr>
<td valign="top">

Created On & Created By

</td>
<td valign="top">

Displays the identity of the user who imported the fault message type and the date when it was imported

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Displays the description associated with the message type, if any.

</td>
</tr>
<tr>
<td valign="top">

ES Repository Information

</td>
<td valign="top">

-   Software Component Version: Displays the software component version to which the message type belongs to in ES repository.
-   Namespace: Displays the ES repository namespace where the message type is created.



</td>
</tr>
</table>



<a name="loio6dfaa7a0bfad42d59c59095ddfc4734b__section_kxs_34p_mxb"/>

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

Displays the name of the node. The standard \(added by default\) and addition \(selected dependent data types\) are also listed.

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

Displays the referenced [Consuming Data Types](consuming-data-types-97ad101.md) assigned to the root node and built-in data type \(decimal, string, or integer\) of the child nodes.

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

You can view following additional details of a fault message type.

In fault message types, only referenced data types of the addition nodes can be edited. To do so, choose *Edit* and then select the node to populate the details in the right-hand side panel.

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

From the *Overview* or *Structure* tab, to assign another user-defined data type, choose *Select*. Choose the integration packages from which you wish to list the data types and select the one to be used. The structure of the selected data type gets loaded in the tree table.

> ### Note:  
> You can edit the referenced data type of the addition node only.



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

**Saving Fault Message Types**

Choose *Save* to save the draft. Choose *Save as version* to save the fault message type with a new version. All modifications are also reflected in the XSD tab.

> ### Note:  
> You can save the artifact even if you have validation errors in your structure tab.

The displayed value range [restrictions](editing-data-type-7136a31.md#loio7136a3141d294a8a86884a3b03aad5b4__table_xtn_yqp_l5b) can't be edited for message types.



<a name="loio6dfaa7a0bfad42d59c59095ddfc4734b__section_u2d_k4p_mxb"/>

## XSD

Displays the XML Schema Definition \(XSD\) that is, the text view of the fault message type in read-only mode.

**Related Information**  


[Consuming Fault Message Type in Service Interface](consuming-fault-message-type-in-service-interface-3613e60.md "")

