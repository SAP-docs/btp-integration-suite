<!-- loio6c8847fe8dcc459580a63194fc55d5b3 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configuring Value Mappings

You use this procedure to perform various functions in a value mapping.



<a name="loio6c8847fe8dcc459580a63194fc55d5b3__prereq_xlr_zjd_2cb"/>

## Prerequisites

-   You have created a value mapping artifact. For more information, see [Creating Value Mapping](creating-value-mapping-25eff9b.md).
-   You are editing the value mapping artifact.



## Context

You create a value mapping artifact to act as a bi-directional look up table. Value mapping offers the distinct advantage of giving you bi-directional look up capabilities which is used quite often in productive mapping scenarios. You can also import CSV files exported from process integration \(PI\) systems in your value mapping.



## Procedure

1.  If you want to import a CSV file that contains value mappings, choose *Import* and select the CSV file you want to import.

2.  In the *Bi-Directional mapping* section, choose *Add* to add a bi-directional mapping.

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
    > If you edit a web edited value mapping in eclipse, then you get a default value for 1:N, M:,1 and M:N mappings. SAP recommends that all groups should contain only one agency identifier and value pair.
    > 
    > Some of the function names in web UI differ from the ones in Eclipse.
    > 
    > Editing of the Value Mapping will no longer be possible if it is configured and saved by choosing the *Configure* option from the Actions <span class="SAP-icons-V5"></span> button provided for the Value Mapping under the *Artfiacts* tab.
    > 
    > Deployment of a Value Mapping with configuration details copied from another deployed Value Mapping is not recommended.


