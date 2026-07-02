<!-- loio518b54f886e449edb62298eae123a694 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with a Node

You can edit the properties of a node

Once you have created a message implementation guideline, you can edit and modify the properties of the nodes in the structure.

1.  Choose *Edit* to edit your message implementation guideline.

2.  Navigate to the *Structure* tab and choose a node that you want to edit. The node details are displayed to the right side of the structure.
3.  Each node has the following details. Certain fields and section pertain only to a leaf node or a group node which is also mentioned below.

    **Details Tab**


    <table>
    <tr>
    <th valign="top">

    Section Name
    
    </th>
    <th valign="top">

    Field Name
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Editable
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="8">
    
    Identifier Information
    
    </td>
    <td valign="top">
    
    Identifier
    
    </td>
    <td valign="top">
    
    Displays the name of the node
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Namespace
    
    </td>
    <td valign="top">
    
    Displays the namespace of the node
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Namespace Prefix
    
    </td>
    <td valign="top">
    
    Namespace Prefix is only shown if the node comes with a namespace prefix \(XML namespace qualified\). If a default namespace is used, this is indicated through *<default\>*.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    XML Node Name
    
    </td>
    <td valign="top">
    
    Displays the corresponding XML tag name of the node. This might include a namespace prefix, if required.

    The name need not necessarily be identical to the node name.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ComplexType \(Group node\)
    
    </td>
    <td valign="top">
    
    Displays the complex data type of the group node
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Complex Type Namespace \(Group node\)
    
    </td>
    <td valign="top">
    
    Displays the complex type namespace of the group node
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SimpleType \(Leaf node\)
    
    </td>
    <td valign="top">
    
    Displays the data type of the leaf node
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Simple Type Namespace \(Leaf node\)
    
    </td>
    <td valign="top">
    
    Displays the type namespace of the leaf node
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="6">
    
    Properties
    
    </td>
    <td valign="top">
    
    Identifier
    
    </td>
    <td valign="top">
    
    Displays the name of the node
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Cardinality
    
    </td>
    <td valign="top">
    
    Displays the cardinality of the node with *min* and *max* values
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Nillable
    
    </td>
    <td valign="top">
    
    Displays if the XML-node is nillable
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Qualifier \(Leaf node\)
    
    </td>
    <td valign="top">
    
    This field appears only when the leaf node is a qualifying node.
    
    </td>
    <td valign="top">
    
    You can add multiple qualifiers using the add :heavy_plus_sign: icon.

    If you want to delete a qualifier from the list, choose the delete<span class="SAP-icons-V5"></span> icon.

    To know about qualifying nodes and how to qualify an instance, see [Qualifying Nodes](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/09be9835e1184603ad796071e0a86b98.html?version=Cloud)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Fixed Value \(Leaf node\)
    
    </td>
    <td valign="top">
    
    You can provide a fixed value to a particular node.

    You can use this field for a node that can have only one fixed value. This value will be included during XML validation of any payload data.
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Example Values \(Leaf node\)
    
    </td>
    <td valign="top">
    
    You can provide example values to a particular leaf node.

    You can set these example values to provide the business user a better understanding of the semantics and expected synatax of the field.

    These example values will be also be used during simulation when you choose *Simulate with Example Data*.
    
    </td>
    <td valign="top">
    
    Choose :heavy_plus_sign: to add an example value.

    Choose :pencil2: to edit an example value.

    Choose <span class="SAP-icons-V5"></span> to delete an example value.

    Choose <span class="SAP-icons-V5"></span> to move a value up the list.

    Choose <span class="SAP-icons-V5"></span> to move a value down the list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Documentation
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    You can enter a detailed description of the purpose of the node.
    
    </td>
    <td valign="top">
    
    Yes

    If you want to format the entered text, select the checkbox next to *Formatted Text*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Complex Type Properties \(Group node\)
    
    </td>
    <td valign="top">
    
    XSD Assertions
    
    </td>
    <td valign="top">
    
    Displays the XSD assertions of the group node.

    > ### Note:  
    > These assertions will be added to the MIG XSD runtime artefact and will be used to improve the payload validation.
    > 
    > Each entry should be a valid boolean XPath expression.
    > 
    > If the XPath value you add references to a node in your MIG message structure, you need to enter the value of the node name used in the XML payload. This information can be found in the *XML Node Name* field.
    > 
    > If you specify more than one XSD Assertion, then all the assertions must evaluate to true.


    
    </td>
    <td valign="top">
    
    Yes.

    Choose the add button :heavy_plus_sign: to add a XSD assertion.

    Select a XSD assertion and choose the edit button :pencil2:to edit the XSD assertion.

    Choose delete button <span class="SAP-icons-V5"></span> to delete a XSD assertion

    Choose <span class="SAP-icons-V5"></span> to move an assertion up the list.

    Choose <span class="SAP-icons-V5"></span> to move an assertion down the list.
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="5">
    
    Simple Type Properties

    This section is displayed only for leaf nodes
    
    </td>
    <td valign="top">
    
    Primitive Type

    > ### Note:  
    > Depending on the data type, other relevant fields may appear. Maintain the values for these fields if necessary.
    > 
    > For example, for the data type *Date*, *Time* or *DateTime*, you can maintain the field *Date Time Format*.


    
    </td>
    <td valign="top">
    
    You can select a primitive data type for the node
    
    </td>
    <td valign="top">
    
    Yes

    Choose the right data type for the node from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Length
    
    </td>
    <td valign="top">
    
    You can specify the minimum and maximum length of the value for the node
    
    </td>
    <td valign="top">
    
    Enter the minimum and maximum length of the value in the *min* and *max* fields respectively.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Format
    
    </td>
    <td valign="top">
    
    You can specify a value pattern for the data type. For example, nnnn for a four-digit number.

    > ### Note:  
    > This is free-style text and is used only for documentation purposes. For *Date* or *Time* patterns preferably use Date Time Format.


    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Date Time Format
    
    </td>
    <td valign="top">
    
    You can choose one of the predefined Date, Time or DateTime patterns. This will be used when defining a Date Time Conversion in the mapping.
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    XSD-Patterns
    
    </td>
    <td valign="top">
    
    Enter the XSD patterns for the leaf node.

    > ### Note:  
    > These patterns will be added to the MIG XSD runtime artefact and will be used to improve the payload validation.
    > 
    > Each entry should be a valid boolean XSD Pattern expression.
    > 
    > If the XPath value you add references to a node in your MIG message structure, you need to enter the value of the node name used in the XML payload. This information can be found in the *XML Node Name* field.
    > 
    > If you specify more than one XSD Pattern, then the field value must match to one of the given patterns.


    
    </td>
    <td valign="top">
    
    Yes

    Choose the add button :heavy_plus_sign: to add a XSD pattern.

    Choose the edit button :pencil2:to edit the XSD pattern.

    Choose delete button <span class="SAP-icons-V5"></span> to delete a XSD pattern.

    Choose <span class="SAP-icons-V5"></span> to move a pattern up the list.

    Choose <span class="SAP-icons-V5"></span> to move a pattern down the list.
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="4">
    
    Syntax Type Related
    
    </td>
    <td valign="top">
    
    External Category
    
    </td>
    <td valign="top">
    
    Displays the external category detail of the node.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Syntax Data Type
    
    </td>
    <td valign="top">
    
    Displays the data type of the syntax of a leaf node as it is originally defined by the B2B standard.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Position
    
    </td>
    <td valign="top">
    
    Displays the position of the syntax type of the node.

    > ### Note:  
    > This field data is relevant for EDI standards such as, ASC X12 and UN/EDIFACT.


    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Level
    
    </td>
    <td valign="top">
    
    Displays the level of the syntax type.

    > ### Note:  
    > This field data is relevant for EDI standards such as, ASC X12 and UN/EDIFACT.


    
    </td>
    <td valign="top">
    
    No
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="2">
    
    XPath Expressions
    
    </td>
    <td valign="top">
    
    CI Format
    
    </td>
    <td valign="top">
    
    Displays the XPath expression for the node which can be used in Cloud Integration version of the message before pre-processing.
    
    </td>
    <td valign="top">
    
    No

    You can copy this XPath expression using the copy <span class="SAP-icons-V5"></span> button provided next to it.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    IA Format
    
    </td>
    <td valign="top">
    
    Displays the XPath expression for the node which can be used in Integration Advisor version of the message after pre-processing.
    
    </td>
    <td valign="top">
    
    No

    You can copy this XPath expression using the copy <span class="SAP-icons-V5"></span> button provided next to it.
    
    </td>
    </tr>
    </table>
    

*Notes Tab*

You can use this tab to enter notes specific to that node.

1.  To add a note, choose *Add*. The *Create Note* dialog box appears.

2.  Choose a *Category* for the note. The different types of notes that can be added to a node are:

    -   Comment
    -   Constraint
    -   Example
    -   Usage
    -   Technical Information

3.  Provide a number for the note type that you are creating under the *Number* field.

4.  Enter the text under the *Text* field. If you want to format the text, select the checkbox next to *Formatted Text*.
5.  Choose *Apply*.
6.  You can also sort the notes under each category based on the number using the <span class="SAP-icons-V5"></span> button.

*Status Tab*

You can use the *Status* tab to set the review entry for a node. This helps to identify nodes that you want to work on later.

This tab can also be used for multi-user review.

*Codelist Tab*

This tab is available only for leaf nodes.

To know how to create and assign codelist to a leaf node, see [Codelists](codelists-a7a84b0.md)

Read this [blog](https://blogs.sap.com/2022/02/09/integration-advisor-extended-semantic-validation-options-for-mig-structures/) to know more about the extended semantic validation options for MIG structures.

