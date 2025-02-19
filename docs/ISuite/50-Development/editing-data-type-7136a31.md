<!-- loio7136a3141d294a8a86884a3b03aad5b4 -->

# Editing Data Type

To edit a data type, choose *Edit*. Select the node to be edited. The editable details are populated in the right-hand side panel.

> ### Note:  
> For visual instructions on how to edit data types, refer the tutorial [Editing data types.](https://developers.sap.com/tutorials/btp-integration-suite-editingdatatype-messagetype.html) 

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

Name

</td>
<td valign="top">

Enter the name of the selected node.

> ### Note:  
> You can't change the name of the root node.



</td>
</tr>
<tr>
<td valign="top">

Category

</td>
<td valign="top">

Displays the category of the selected node. The category of a node is not editable.

</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Choose a type for an element or attribute:

-   Primitive Type: From the *Value* field, select a built-in data type \(example string, decimal, or integer\)

-   Data Type: To assign a user-defined data type, choose *Select*. Choose the integration packages from which you wish to list the data types and select the one to be used. The structure of the selected data type gets loaded in the tree table.

    > ### Note:  
    > While assigning user-defined data type, only simple type data types can be assigned to root node and child attribute nodes. Hence, only simple type data types from the selected packages are listed. The data types that are currently being edited are excluded from the list.


> ### Note:  
> -   If no *Type* is assigned to a child node, Primitive type is selected by default with no *Value* assigned to the node.
> 
> -   Changing the Type of a parent element node will delete its child attributes.
> -   Changing the Type of root node will delete all its subelements.
> -   Assigning a Type to the root node or parent node when no Type is assigned, will delete all its subelements.



</td>
</tr>
<tr>
<td valign="top">

Namespace

</td>
<td valign="top">

Displays the namespace to which the user-defined data type belongs to or where it's created.

</td>
</tr>
<tr>
<td valign="top">

Package Name

\(appears only if the Type is Data Type\)

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

Enter the default value for the selected node.

</td>
</tr>
<tr>
<td valign="top">

Qualify Schema

</td>
<td valign="top">

1.  Choose the root node to enable qualify schema.
2.  Choose *Element* or *Attribute* or both to add form="qualified"\(in the generated XSD tab\) to all the child elements or attributes or both respectively.

> ### Note:  
> The selection has no impact on simple type data type or when there are no elements or attributes in complex type data type.



</td>
</tr>
<tr>
<td valign="top">

Occurrence

\(appears only if the selected node is an Attribute\)

</td>
<td valign="top">

Choose *required* or *optional*.

</td>
</tr>
<tr>
<td valign="top">

MinOccurs & MaxOccurs

\(appears only if the selected node is an Element\)

</td>
<td valign="top">

Specify the minimum and maximum occurrence of an element.

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Enter the description of the selected node.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

**Restrictions**

> ### Note:  
> You can restrict the value range of a built-in data type for simple data types, elements or attributes.



</td>
</tr>
<tr>
<td valign="top">

enumeration

</td>
<td valign="top">

Restricts the value range to a set of individual values. The allowed value is 'float'. You can add multiple enumeration.

</td>
</tr>
<tr>
<td valign="top">

fractionDigits

</td>
<td valign="top">

Specify the number of places permitted after the comma. The allowed value is only non negative integer type.

</td>
</tr>
<tr>
<td valign="top">

length, maxLength, minLength

</td>
<td valign="top">

Specify the exact \(length\), maximum \(maxLength\), or minimum \(minLength\) length of a string-based data type. The allowed value is only non negative integer type.

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

Specify a pattern for string-based data types. The pattern has the form of a regular expression that describes a set of appropriate character sequences. You can add multiple patterns.

</td>
</tr>
<tr>
<td valign="top">

totalDigits

</td>
<td valign="top">

Specify the total number of digits in a number. The allowed value is only positive integer type.

</td>
</tr>
<tr>
<td valign="top">

whiteSpace

</td>
<td valign="top">

Specify how white-space character \(line feed, tabs, blanks, and carriage returns\) is applied. It has three values:

preserve: Retains all white-space characters.

replace: Replaces every line feed, tab, and carriage return with a blank.

collapse: Similar to replace but subsequent blanks are replaced by a single blank and leading, final blanks are deleted.

</td>
</tr>
</table>



<a name="loio7136a3141d294a8a86884a3b03aad5b4__section_pcq_smc_gcc"/>

## Adding Child Nodes

To add elements and attributes while editing the data type, follow these steps:

1.  Select the node where you want to add a child element or attribute.
2.  Choose *Edit*.
3.  Choose *Add* and select whether you wish to add Element or Attribute. If you wish to add multiple row of element or attributes, choose *Rows*. Specify the number of rows to be added and choose *Add*. Refer the following table to understand when and where can you add the elements and attributes.

    ****


    <table>
    <tr>
    <th valign="top">

    Node
    
    </th>
    <th valign="top">

    Category
    
    </th>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Add Element
    
    </th>
    <th valign="top">

    Add Attribute
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Root
    
    </td>
    <td valign="top">
    
    Complex
    
    </td>
    <td valign="top">
    
    Assigned \(Any\)
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Root
    
    </td>
    <td valign="top">
    
    Complex
    
    </td>
    <td valign="top">
    
    Not assigned
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Any
    
    </td>
    <td valign="top">
    
    Simple
    
    </td>
    <td valign="top">
    
    Any
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Child
    
    </td>
    <td valign="top">
    
    Element
    
    </td>
    <td valign="top">
    
    Primitive or user-defined simple data type
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Child
    
    </td>
    <td valign="top">
    
    Element
    
    </td>
    <td valign="top">
    
    User-defined complex data type
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Child
    
    </td>
    <td valign="top">
    
    Element
    
    </td>
    <td valign="top">
    
    Not assigned
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Child
    
    </td>
    <td valign="top">
    
    Attribute
    
    </td>
    <td valign="top">
    
    Any
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    </table>
    



<a name="loio7136a3141d294a8a86884a3b03aad5b4__section_lz2_mmc_gcc"/>

## Deleting Nodes

You can also delete nodes from the data type. To do so follow these steps:

1.  Use the checkboxes to select the nodes that you want to delete.

    > ### Note:  
    > -   You can't delete a root node.
    > -   If you delete a parent node, all its child nodes will also be deleted.
    > -   You can't delete individual child nodes of an element which has user-defined data type assigned.

2.  Choose *Delete*.

    > ### Caution:  
    > Select the delete button just above the table. Selecting *Delete* at the top will delete the data type itself.




<a name="loio7136a3141d294a8a86884a3b03aad5b4__section_alx_rpj_bdc"/>

## Moving Nodes

Use the checkboxes to perform actions like cut, copy, paste, change positions to up or down, drag, and drop on the nodes. The XSD tab is updated simultaneously.

> ### Note:  
> -   All these actions are disabled for the root node.
> -   All these actions are disabled if multiple nodes are selected at once.
> -   For pasting the cut or copied nodes, all the rules of [adding a node](editing-data-type-7136a31.md#loio7136a3141d294a8a86884a3b03aad5b4__section_pcq_smc_gcc) will apply.
> -   If you cut a parent node, all its child node are also cut.



<a name="loio7136a3141d294a8a86884a3b03aad5b4__section_pcp_smc_gcc"/>

## Saving Data Types

Choose *Save* to save the draft. Choose*Save as version* to save the data type with a new version. All modifications are reflected in XSD tab.

> ### Note:  
> You can save te artifact even if you have validation errors in your *Structure* tab.

