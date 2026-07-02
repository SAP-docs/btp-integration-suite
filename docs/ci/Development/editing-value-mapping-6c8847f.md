<!-- loio6c8847fe8dcc459580a63194fc55d5b3 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Editing Value Mapping

You use this procedure to perform various functions in a value mapping.



<a name="loio6c8847fe8dcc459580a63194fc55d5b3__prereq_xlr_zjd_2cb"/>

## Prerequisites

You have created a value mapping artifact. For more information, see [Creating Value Mapping](creating-value-mapping-25eff9b.md).



## Context

You create a value mapping artifact to act as a bi-directional look up table. Value mapping offers the distinct advantage of giving you bi-directional look up capabilities which is used quite often in productive mapping scenarios. You can also import CSV files exported from process integration \(PI\) systems in your value mapping.



## Procedure

1.  Open your value mapping artifact in edit mode.

2.  In the *Bi-Directional mapping* section, choose *Add* to add a bi-directional mapping.

    > ### Note:  
    > Alternatively, you can also import a CSV file that contains value mappings. Choose *Import* and select the CSV file you want to import. Also see [Formatting Guidelines for CSV Files used in Value Mapping](formatting-guidelines-for-csv-files-used-in-value-mapping-8fa8203.md).

3.  In the *Value mappings for* section, choose *Add* to add a value mapping.

    There are scenarios in which values in the Source Agency are unique but the values in the Target Agency are repetitive for different source values. For such cases, the default values are generated and auto-assigned by the application. In case you want to modify the default value, then choose the *Default Values* tab and select the *Target Value* to set the default value for the Source agency.

4.  Provide values for the agency and identifier in the respective fields.

5.  Choose :wastebasket: to remove a bi-directional or value mapping.

    You can choose *Delete All* to remove all bi-directional and value mappings from the respective sections.

6.  Choose *Save* to keep the changes.

7.  Choose *Save as version* to retain a copy of the current artifact.

    You can view the version history of an artifact by choosing the current version mentioned along with it.

8.  Choose *Cancel* to revert the changes.

    > ### Note:  
    > Deploying a value mapping with details copied from another deployed value mapping artifact is not recommended.


