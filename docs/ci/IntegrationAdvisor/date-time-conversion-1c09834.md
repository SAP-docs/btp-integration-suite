<!-- loio1c0983456eae4b3dbcf314096a9ae52c -->

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


*Conflict in using N:1 Mapping*

There could be scenarios where multiple source nodes provide the same input to the target node. In such cases, conflict of data could arise. Say for example, you have mapped 2 source nodes with one target node. The source nodes node1 and node2 both contain the format *MMYY* and the target date time format is also *MMYY*. This could result in a conflict. To resolve this, the application displays two seperate fields below the *Target DateTime Format*:

-   *Month\(MM\)* 

-   *Year\(YY\)*

You can now choose which of the 2 source nodes will contribute to the MM part and which will contribute to the YY part using the drop-down list provided for the two fields mentioned above.

In other case, if node1 is of type *MM* and node2 is of type *DD* and the target node type is only *MM*, then only the data from node1 is picked and node2 will be ignored.

