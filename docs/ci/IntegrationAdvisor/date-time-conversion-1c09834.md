<!-- loio1c0983456eae4b3dbcf314096a9ae52c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Date Time Conversion

This chapter explains how the Date Time Conversion works.

You can map source and target nodes of type *Date*, *Time* and *DateTime* in the message structure of an MAG. To know more about this data type, see [Primitive Data Types](primitive-data-types-72a8e9e.md).

The following mapping cardinalities are supported for Date Time mapping:

-   1:1 : You can map one node from the source structure with one node of the target structure.

-   N:1 : You can map multiple nodes from the source structure with one node of the target structure. The values of all the mapped source nodes will be merged into one datetime input and will be fed into the target node.

*Date Time Conversion* feature has the following feature variations based on the type of format:

-   If the format differs between the nodes, the format of the source node can be converted to the format of the target node during the mapping. To do so, you need to set the format of the nodes. Select the element and navigate to the *Functions* tab and choose *Switch to DateTime Mapping*.

    > ### Note:  
    > Switching to DateTime mapping will delete the existing function. Choose *OK* to confirm.
    > 
    > If you want to implement your own function, you can do so using a XSLT code. To know more, see [Functions](functions-2ea22d0.md).

    Navigate to the *Date Time Conversion* tab and set the values of *Source DateTime Format* and *Target DateTime Format* and choose *Save*. For N:1 mapping, you need to maintain the *Source DateTime Format* value for each of the source nodes that are mapped.

    The format used in these two fields are displayed below them in detail. This helps in identifying the values entered during simulation. Choose *Simulate* and select your relevant option to see the simulation data split according to the DateTime format.

-   If source and target nodes are both Date, Time, or DateTime fields then the *DataTime Conversion* tab is displayed automatically. You see the default DateTime format of the source as well as of the target node which is set while defining the corresponding message implementation guidelines.


*Handling Missing DateTime Values*

When you map a source node with a target node of type DateTime with different format, the source node might not contain all the inputs needed for the format on the target side. Say for example, a source node with format *MMDD* is mapped with the target node format *DDMMCCYY*. Here, the values for MM and DD can be picked from the source node value but the values for CC and YY are missing. In such cases, you can set pre-fixed values to the missing fields in the *Date Time Conversion* tab. You can set the value as:

-   *Current Date/Time*: This option will set the current date/time value for the missing part at the time of mapping execution.

-   *Fixed Value*: This option allows you to provide a constant value for the missing parts of the target format.

If no values are mentioned, then *Default Value* is set for the fields with the following default set by the system for the respective missing part.

**DateTime Default Values**


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Default Value

</th>
</tr>
<tr>
<td valign="top">

YEAR

</td>
<td valign="top">

1970

</td>
</tr>
<tr>
<td valign="top">

MONTH

</td>
<td valign="top">

1

</td>
</tr>
<tr>
<td valign="top">

MONTH

</td>
<td valign="top">

1

</td>
</tr>
<tr>
<td valign="top">

DAY\_OF\_MONTH

</td>
<td valign="top">

1

</td>
</tr>
<tr>
<td valign="top">

HOUR, MINUTE, SECOND, MILLISECOND

</td>
<td valign="top">

0

</td>
</tr>
<tr>
<td valign="top">

Timezone-Offset

</td>
<td valign="top">

0

</td>
</tr>
<tr>
<td valign="top">

Century

</td>
<td valign="top">

Two digit years are interpreted by adjusting dates to be within 80 years before and 20 years after the time of the execution of the mapping.

</td>
</tr>
</table>

*Conflict in using N:1 Mapping*

There could be scenarios where multiple source nodes provide the same input to the target node. In such cases, conflict of data could arise. Say for example, you have mapped 2 source nodes with one target node. The source nodes node1 and node2 both contain the format *MMYY* and the target date time format is also *MMYY*. This could result in a conflict. To resolve this, the application displays two seperate fields below the *Target DateTime Format*:

-   *Month\(MM\)* 

-   *Year\(YY\)*

You can now choose which of the 2 source nodes will contribute to the MM part and which will contribute to the YY part using the drop-down list provided for the two fields mentioned above.

In other case, if node1 is of type *MM* and node2 is of type *DD* and the target node type is only *MM*, then only the data from node1 is picked and node2 will be ignored.

*Adding Global Parameters for the Source Node*

You can also add global parameters for the source node. Suppose let us say you have created global parameters in the *Global Parameters* tab of your MAG that you wish to use in your datetime conversion. To do so , follow the procedure below:

> ### Note:  
> To know how to add global parameters in a MAG, see [Defining Global Parameters](defining-global-parameters-62fe053.md).

1.  In the *Date Time Conversion* tab, choose *Add Global Parameter* below the source node detail.

2.  A pop-up dialog opens listing down the global parameters that you defined in your MAG. Select one from the list.
3.  Set the value for *Date Time Format* field for this newly added parameter.

    Depending on the format set for the source node and this parameter, the values for the corresponding fields in the target node will get adjusted.

4.  To delete the parameter from the date time conversion, select the delete :wastebasket: button next to it.

