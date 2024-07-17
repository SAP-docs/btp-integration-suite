<!-- loio97ad10142fc34269902006e488af1eff -->

# Configuring Data Types

Data Type is an object, containing the structure of data that defines the message. A data type is defined using XML Schema Definition Language \(XSDL\).

Cloud Integration allows you to view and edit your data types.



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



### 

To edit a data type, choose *Edit*. Select the node to be edited. The editable details are populated in the right-hand side panel.

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

Displays the default value defined for the node.

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

MinOccurs & Maxoccurs

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

**Adding Child Nodes**

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
    

**Saving Data Types**

Choose *Save* to save the draft. Choose*Save as version* to save the data type with a new version. All modifications are reflected in XSD tab.

> ### Note:  
> You can save te artifact even if you have validation errors in your *Structure* tab.



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

Displays the XML Schema Definition \(XSD\) that is, the text view of the data type in read-only mode.

**Related Information**  


[Configuring Message Types](configuring-message-types-2eb71b8.md "A message type comprises a data type that describes the structure of a message. For technical reasons, a data type alone is not sufficient to describe the instance of a message. Data types are defined in XML Schema as abstract types that aren't yet tied to an element. You can only describe an instance of a message when you've specified a data type. Therefore, a message type defines the root element of a message.")

