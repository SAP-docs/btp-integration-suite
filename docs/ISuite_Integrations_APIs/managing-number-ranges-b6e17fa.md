<!-- loiob6e17fa17a70491da4a54216db298f84 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Managing Number Ranges

The topic provides an overview of number ranges related artifacts.

You choose the *Number Ranges* tile in the *Manage Stores* area to view the artifacts with the corresponding status.



## Number Ranges Overview

While sending out a document in case of EDI processing, a unique interchange number must be added to each document. In order to add such an interchange number you can use the Number Range Object. In case of EDIFACT the outgoing EDIFACT messages should have Interchange Control Reference with length 1 to 9 digits, with minmum length being 1 digit and maximum length ranging to 9 digits.

Visit the [blog](https://blogs.sap.com/2018/06/26/cloud-integration-working-with-number-ranges/), to understand how to consume Number Ranges in EDI message processing.

> ### Note:  
> If your tenant has one or more Edge Integration Cell nodes configured, the page includes a **Runtime** dropdown above the number ranges list. Selecting a value from the dropdown scopes the list and all available operations to that specific runtime.

A list of number ranges is displayed in a table. For each artifact, the following attributes are displayed:

**Attributes of Number Ranges Artifacts**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name* 

</td>
<td valign="top">

Displays name of the artifact

</td>
</tr>
<tr>
<td valign="top">

*Minimum Value* 

</td>
<td valign="top">

Minimum value of the artifact should be greater than or equal to 0.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Value* 

</td>
<td valign="top">

Maximum value of the artifact should be less than 15 digit.

</td>
</tr>
<tr>
<td valign="top">

*Next Value* 

</td>
<td valign="top">

Displays a value that can be used the next time you invoke this artifact.

> ### Note:  
> The **Next Value** shown in the UI corresponds to the **Current Value** in the API. The difference is only in terminology.



</td>
</tr>
<tr>
<td valign="top">

*Field Length* 

</td>
<td valign="top">

Displays the number of digits for the current value. If the value of **maximum value** attribute is 100 then the field length should be greater than 2, if the value of **maximum value** attribute is 99999 then the field length should be greater than 4 and so on.

If the value of this attribute is 4 and the value of **current value** attribute is 7, then the number range is reflected as 0007 and not just 7. This refers to the concept of padding '0's to the value.

If the value of this attribute is 0 then the value of **current value** attribute is flashed as it is with no padding on the number range.

The maximum value allowed for this attribute is 14.

</td>
</tr>
<tr>
<td valign="top">

*Rotate* 

</td>
<td valign="top">

If this attribute is set and the number range reaches specified **maximum value**, then the **current value** resets to specified **minimum value**.

</td>
</tr>
<tr>
<td valign="top">

*Deployed By* 

</td>
<td valign="top">

Displays the user id of the user who deployed the artifact.

</td>
</tr>
<tr>
<td valign="top">

*Deployed On* 

</td>
<td valign="top">

Displays the time when the artifact was deployed.

</td>
</tr>
</table>

To sort and filter the content of the table, choose *Table Settings* \(:gear:\). On the subsequent screen, you can define how the table entries are to be sorted \(by specifying an attribute and whether the entries are to be sorted for that attribute in ascending or descending order\). You can also filter the table entries for certain attributes.



## Actions

-   To create or deploy a new artifact, choose *Add*.

-   To edit and redeploy an existing artifact, select the artifact in the table and choose *Edit*.

-   To undeploy an artifact, select the artifact in the table and choose *Undeploy*.




## Adding a Number Range

-   To create or deploy a new artifact, choose *Add* and in the *Add Number Ranges* dialog, provide the following:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name* 
    
    </td>
    <td valign="top">
    
    A unique name for the number range artifact. Must not already exist on any of the selected runtimes.

    > ### Note:  
    > The following name validation rules apply when deploying to multiple runtimes:
    > 
    > -   If you select runtimes first and then enter a name, the system checks whether the name already exists on any of the selected runtimes. If a conflict is found, a duplication error is displayed.
    > 
    > -   If you enter a name first and then open the **Runtimes** dropdown, any runtime on which that name already exists is greyed out and cannot be selected.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description* 
    
    </td>
    <td valign="top">
    
    An optional description of the artifact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Runtimes* 
    
    </td>
    <td valign="top">
    
    One or more runtime nodes to deploy the artifact to. The field is pre-filled with the runtime currently selected from the dropdown on the page. You can add further runtimes, including Cloud Integration and any active Edge Integration Cell nodes.

    > ### Note:  
    > Edge Integration Cell nodes that use HANA Database are not supported. Although the option to add a number range object remains visible for these nodes, but the operation fails when you proceed.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Maximum Value* 
    
    </td>
    <td valign="top">
    
    The maximum value of the number range. Must be fewer than 15 digits.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Minimum Value* 
    
    </td>
    <td valign="top">
    
    The minimum value of the number range. Must be greater than or equal to 0.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Rotate* 
    
    </td>
    <td valign="top">
    
    If selected, the current value resets to the minimum value when the maximum value is reached.
    
    </td>
    </tr>
    </table>
    
-   Choose *Add*.

