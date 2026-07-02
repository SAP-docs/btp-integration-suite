<!-- loio9ea58d63c6f64516b33c46079cc694e9 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Mapping the Source and Target Nodes

This topic helps you understand the concepts involved in mapping source and target nodes.

You can define a mapping between a source and a target node using the Mapping Guidelines \(MAGs\) editor. The source and target Message Implementation Guidelines \(MIGs\) are displayed in a hierarchical structure in the *Mapping* tab. You can drag a source node to a target node to specify a mapping, and apply functions based on your requirements to define a data transformation. For more information, see [Functions](functions-2ea22d0.md) and [Value Transformations](value-transformations-19f8374.md).

The resulting target document structure varies based on:

-   The type of mapping defined between the source and target nodes.

-   The cardinality of the target node.


The following table explains the basic terms involved in mapping nodes:


<table>
<tr>
<th valign="top">

Term

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Group Node

</td>
<td valign="top">

A node that has subnodes and doesn't contain data. It can also be a subnode to another group node.

</td>
</tr>
<tr>
<td valign="top">

Leaf Node

</td>
<td valign="top">

A subnode that contains data.

</td>
</tr>
<tr>
<td valign="top">

Cardinality

</td>
<td valign="top">

Specifies the number of times an element can occur in a document. There are two values: minimum and maximum.

> ### Example:  
> A cardinality of 1..n where n=5, means that a minimum of one element is instantiated and a maximum of five elements are instantiated at runtime.



</td>
</tr>
<tr>
<td valign="top">

Mapping Line

</td>
<td valign="top">

Mapping associates elements of a source structure with one or more elements of a target structure and determines target node construction. A mapping line is drawn to connect nodes and subnodes from source to target.

</td>
</tr>
<tr>
<td valign="top">

Mapping Entity

</td>
<td valign="top">

A mapping entity represents a mapping from one or more source elements to a single target element.

</td>
</tr>
</table>



<a name="loio9ea58d63c6f64516b33c46079cc694e9__section_hg1_sxl_wnb"/>

## Mapping Cardinality

Mapping cardinality represents the number of nodes associated in the source and target document structure.

> ### Example:  
> You can map one source node to one target node or one or more source nodes to one target node.

The root node is the highest node in the document structure. As you traverse down the structure from the root node, each mapped element sets the context for interpreting the cardinalities. The target document structure differs when you map either only the leaf nodes or the leaf nodes along with their group nodes.

When you map a source group node to a target group node whose target maximum occurrence is greater than one, an instance of the target group node is created for each instance of the source group node. The target group node serves as the context for realizing the cardinalities and the mappings of its leaf nodes.

If you map leaf nodes without including their group nodes, an instance of the target group node is created based on the instantiation of its leaf nodes.



### Group to Leaf Mapping

Mapping a source group node to a target leaf node creates a target node, where the cardinality of the target node is determined by the actual cardinality of the source group node. The newly created target node will be empty and you need to map the relevant source leaf nodes with this target node to provide data for the target instances.

For this mapping

-   If the target maximum occurrence equals 1 and

    -   If the actual occurrence of the source group node is at least one, the target leaf node gets created

    -   If the actual occurrence of the source group node is zero and the minimum occurrence of the target leaf node is zero, the target leaf node does not get created.
    -   If the actual occurrence of the source group node is zero and the minimum occurrence of the target leaf node is one, the target leaf node gets created.

-   If the target maximum occurrence is greater than 1, then the cardinality of the target leaf node corresponds to that of the mapped source group node. Each instance of the source group node creates exactly one instance of the group node in the target independent of the target cardinality, even if the actual occurrence of the source node is greater than the maximal occurrence of the target node.

    > ### Note:  
    > String Processing is not supported in group to leaf mapping.


If there is only one leaf node mapped to the target node and

-   If only one instance of this single node is relevant for the respective target node, then the content of each instance of the target node is filled with the content of the corresponding instance of the source node.

-   If more that one instances of this single leaf node are relevant, the values are concatenated for each occurrence of the source group node separately and assigned to the corresponding instance of the target leaf node.

If more than one leaf node is mapped, the values of all the nodes are concatenated for each occurrence of the source group node and the concatenated value is used for the target leaf node.



The following options are supported when mapping nodes from source to target.


<table>
<tr>
<th valign="top">

Mapping Cardinalities

</th>
<th valign="top">

Mapping Type

</th>
</tr>
<tr>
<td valign="top">

1:1

</td>
<td valign="top">

Leaf to Leaf

</td>
</tr>
<tr>
<td valign="top">

1:1

</td>
<td valign="top">

Group to Group

</td>
</tr>
<tr>
<td valign="top">

1:1

</td>
<td valign="top">

Leaf to Group

</td>
</tr>
<tr>
<td valign="top">

N:1

</td>
<td valign="top">

Leaf to Leaf

</td>
</tr>
<tr>
<td valign="top">

0:1

</td>
<td valign="top">

None to Leaf \(Constants\)

</td>
</tr>
<tr>
<td valign="top">

1:1

</td>
<td valign="top">

Group to Leaf

</td>
</tr>
<tr>
<td valign="top">

N:1

</td>
<td valign="top">

Group to Leaf

</td>
</tr>
</table>



### 1:1 Mapping

-   It represents an association in which one element of the source is mapped to only one element of the target.
-   If the maximum occurrence value of the target node is greater than one, then a target node is created for each instance of the source node.
-   If the maximum occurrence value of the target node is equal to one, then the contents of the source nodes are concatenated and written onto the target node.



### N:1 Mapping

-   It represents an association in which many elements of the source are mapped to one element of the target.
-   If the maximum occurrence value of the target node is equal to one, then the contents of the source nodes are concatenated and written onto the target node.
-   If the maximum occurrence value of the target node is greater than one, then this mapping isn't allowed.



### 0:1 Mapping

You can directly assign a constant value to a target leaf node without defining a mapping for it.

> ### Note:  
> The following mapping options aren't supported:
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Mapping Cardinalities
> 
> </th>
> <th valign="top">
> 
> Mapping Type
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> N:1
> 
> </td>
> <td valign="top">
> 
> Group to Group
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> N:1
> 
> </td>
> <td valign="top">
> 
> Leaf to Group
> 
> </td>
> </tr>
> </table>

There are two variables which can be used in functions from Group-to-leaf mapping:

-   *@position*: This variable gives the position of the current instance in the list of all instances of the mapped source group node.

-   *@last*: The variable gives the index of the last instance \(equals the number of instances\) of the mapped source group node.



<a name="loio9ea58d63c6f64516b33c46079cc694e9__section_olb_5j4_bpb"/>

## Conditional Mapping

You can specify conditions on leaf nodes to control the creation and cardinality of the target group or leaf node instances in a group-to-group and leaf-to-leaf node mapping respectively.

When a leaf node is added as a condition node to a leaf-to-leaf mapping:

-   A *Condition* checkbox is provided for the leaf node in the mapping list.

    > ### Note:  
    > Conditional mapping is not supported for nodes with
    > 
    > -   Constant value mapping
    > -   String Processing type
    > 
    > For such mapping, the *Condition* checkbox is disabled.

-   On selecting the checkbox, the *Condition* tab on the mapping pane becomes available.
-   The *XPath Code* editor is displayed where you can specify the condition as an XPath expression.

When a leaf node is added as a condition node to a group-to-group node mapping:

-   The *Condition* checkbox is selected by default for the leaf node in the mapping list.

    > ### Note:  
    > For group-to-group mappings, all additional source leaf nodes are automatically condition nodes.

-   The *Condition* tab on the mapping pane becomes available.
-   The *XPath Code* editor is displayed where you can specify the condition as an XPath expression.

> ### Note:  
> You can't add additional group nodes to an existing conditional mapping.

The default XPath expression, `boolean($nodes_in/*)`, of the mapping returns true only if the sequence isn't empty. The sequence `$nodes_id/*` contains all the instances of the conditional nodes, that are relevant for one instance of the target node. You can edit the default expression as per your business needs. For example, if the expression, `$nodes_in/partyRole = 'BUY'`, is specified as a condition on the leaf node, partyRole, the corresponding target node is created only if the condition is satisfied.

> ### Note:  
> For more information, refer to XPath specification published by W3C.

Use the shared code feature to create frequently used code snippets and reuse it as required within your Mapping Guideline \(MAG\). You can create, share, and reuse the XPath expressions in the same way as the XSLT functions. For more information, refer [Creating a Shared Code](creating-a-shared-code-e951f66.md).

When you choose to delete the last available conditional node in a group-to-group node mapping, the corresponding leaf node and its conditions are removed from the mapping.



You can know the type of mapping used based on the icon denoted over the mapping lines.

**Mapping line types**


<table>
<tr>
<th valign="top">

Icon

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons-V5"></span>

</td>
<td valign="top">

Denotes

-   Function without a source node

-   Group to leaf mapping
-   Leaf to leaf mapping



</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons-V5"></span>

</td>
<td valign="top">

String processing

</td>
</tr>
<tr>
<td valign="top">

:calendar:

</td>
<td valign="top">

Date Time mapping

</td>
</tr>
<tr>
<td valign="top">

:hash:

</td>
<td valign="top">

Constant

</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons-TNT-V3"></span>

</td>
<td valign="top">

Code value mapping

</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons-TNT-V3"></span>

</td>
<td valign="top">

Conditional mapping

</td>
</tr>
</table>

You can also search for a particular node in the target or source structure using the search bar provided.

If you want to search for a particular entry in the *Mapping List* tab, select the relevant column name and enter the search value in the filter <span class="SAP-icons-V5"></span> field. The filter option is also avaliable for the *Code Value Mapping* that allows you to filter values both in the source and target code values.



<a name="loio9ea58d63c6f64516b33c46079cc694e9__section_iwv_gsw_31c"/>

## Duplicate Target Nodes

You can now duplicate a target node and map other source nodes to the duplicated target node. This feature applies for both group and leaf node. To do so,

1.  Select the context menu <span class="SAP-icons-V5"></span> of the target node you wish to copy and select *Duplicate*.

2.  The *Duplicate Node* dialog box appears with the details of the selected node and a *Duplicates* table. Select *Add*.
3.  This will create a copy of the original node in the *Duplicates* table. You can maintain the name and cardinality of this new node.

    > ### Note:  
    > By default, to distinguish the duplicated nodes from the original node, the duplicate names are prefixed with a number in square \[\] brackets.

4.  You can create multiple duplicates of the node. Just select *Add* to create another copy of the node.
5.  After maintaining the necessary information, select *Apply*. The copied nodes will behave the same as the original node.

    > ### Note:  
    > If the original node is changed, then the changes will be applied to the duplicates as well.




<a name="loio9ea58d63c6f64516b33c46079cc694e9__section_hns_lqs_d4b"/>

## Deletion of Mapping Lines

You can delete both mapping lines and mapping entities that aren't required. In *Edit* mode, select the mapping line or entity, and press the [Delete\] key.

Alternatively, you can -

-   Right-click the mapping line or entity and choose *Delete* from the context menu.

-   Delete multiple mapping entities by selecting the check box of the entries you want to delete under the *Mapping List* tab and selecting *Delete* button provided above the table.

You can also delete an individual mapping line from a mapping entity. You can select the mapping entity and right-click the individual mapping line, and choose *Delete Line* from the context menu.

