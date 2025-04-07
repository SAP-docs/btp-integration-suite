<!-- loiod5bbbeea37c9401b8e635e8fd2fdad36 -->

# Creating Data Types and Message Types

Create new Data Type and Message Type artifacts or import from the Enterprise Services \(ES\) Repository.

> ### Note:  
> For visual instructions on how to create data types, refer the tutorial [Creating data types and message types.](https://developers.sap.com/tutorials/btp-integration-suite-creatingdatatype-messagetype.html)

<a name="create_mt_dt"/>

<!-- create\_mt\_dt -->

## Create Data Type and Message Type Artifacts



<a name="create_mt_dt__prereq_tcl_g2x_3xb"/>

## Prerequisites

You’ve created an integration package and opened it in edit mode. For more information, see [Packaging Integration Content in SAP Integration Suite](packaging-integration-content-in-sap-integration-suite-89da0a2.md).



## Procedure

1.  Navigate to the *Artifacts* tab and choose *Add* \> *Data Type* or *Add* \> *Message Type* to add a data type or message type artifact.

2.  In the dialog box, choose *Create*.

3.  Enter all the mandatory information in the fields.

4.  Choose *Add* to just add the artifact or *Add and Open in Editor* to open the artifact in its editor. To further define the structure of a data type, see [Configuring Data Types](configuring-data-types-97ad101.md).


<a name="import_mt_dt"/>

<!-- import\_mt\_dt -->

## Import Data Type and Message Type Artifacts from Enterprise Service Repository



<a name="import_mt_dt__prereq_tcl_g2x_3xc"/>

## Prerequisites

-   You’ve created an integration package and opened it in edit mode. For more information, see [Packaging Integration Content in SAP Integration Suite](packaging-integration-content-in-sap-integration-suite-89da0a2.md).
-   You've configured connection to ES Repository. For more information, see [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).



## Procedure

1.  Navigate to the *Artifacts* tab and choose *Add* \> *Data Type* or *Add* \> *Message Type* to add a data Type or message Type artifact.

2.  In the dialog box, choose *Import from ES Repository*.

3.  *ES Repository* appears as the *Source*.In the *Name* list, select an ES Repository from the list of connected systems. The *Address* is automaticaly populated.

4.  Choose *Connect*. A list of available data types or message types in ES repository appears.

5.  Select the data type or message type that you wish to import.

6.  Select the *Include Dependent Data Types* checkbox if you wish to include the dependent data type objects while importing the selected data type or message type.

7.  Choose *View Summary* to view a summary of all the artifacts to be imported. From the list of objects, you can view the following object status in the *Information* column:

    -   *Create artifact*: Means that this object will be created for the first time.
    -   *Skips; version already exists*: Means that the selected version of this object already exists in an integration package, which can be reused. Hence, object import is skipped. Duplicate object isn't created.
    -   *Adds new version:* Means that a version of this object already exists in an integration package. But, it is not the latest version, which is being imported from the ES repository. So, latest version of the object is created.
    -   *Error; ID already exists:* Means that an artifact with the same ID as the selected primary data type or message type already exists in an integration package. Choose *Resolve*, to assign another ID for this artifact. Then, choose *View Summary*.

8.  Choose *Add*. Import results with the details of created, skipped, failed artifacts appear.

    The artifact is added to the *Artifacts* tab. To further edit the data type, open the artifact in its editor and see [Configuring Data Types](configuring-data-types-97ad101.md).


