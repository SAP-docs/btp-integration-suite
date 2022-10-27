<!-- loio1c0983456eae4b3dbcf314096a9ae52c -->

# Date Time Conversion

This chapter explains how the Date Time Conversion works..

You can map source and target nodes of type *Date*, *Time* and *DateTime* in the message structure of an MAG. To know more about this data type, see [Primitive Data Types](primitive-data-types-72a8e9e.md).

*Date Time Conversion* feature has the following feature variations based on the type of format:

-   If the format differs between the nodes, the format of the source node can be converted to the format of the target node during the mapping. To do so, you need to set the format of the nodes. Select the element and navigate to the *Functions* tab and choose *Switch to DateTime Mapping*.

    > ### Note:  
    > Switching to DateTime mapping will delete the existing function. Choose *OK* to confirm.

    Navigate to the *Date Time Conversion* tab and set the values of *Source DateTime Format* and *Target DateTime Format* and choose *Save*.

    The format used in these two fields are displayed below them in detail. This helps in identifying the values entered during simulation. Choose *Simulate* and select your relevant option to see the simulation data split according to the DateTime format.

-   If source and target nodes are both Date, Time, or DateTime fields then the *DataTime Conversion* tab is displayed automatically. You see the default DateTime format of the source as well as of the target node which is set while defining the corresponding message implementation guidelines.


