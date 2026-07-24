<!-- loio789b3941acf04d8f87cf837f2f4b98d9 -->

# Creating Fault Message Type

Create new fault message type or import from the Enterprise Services \(ES\) Repository.

<a name="create_mt_dt"/>

<!-- create\_mt\_dt -->

## Create Fault Message Type Artifact



<a name="create_mt_dt__prereq_tcl_g2x_3xb"/>

## Prerequisites

You’ve created an integration package and opened it in edit mode. For more information, see [Packaging Integration Content in SAP Integration Suite](packaging-integration-content-in-sap-integration-suite-89da0a2.md).



## Procedure

1.  Navigate to the *Artifacts* tab and choose *Add* \> *Fault Message Type* to add fault message type artifact.

2.  In the dialog box, choose *Create*.

3.  Enter all the mandatory information in the fields.

4.  Choose *Add* to just add the artifact or *Add and Open in Editor* to open the artifact in its editor. To further define the structure of a data type, see [Configuring Fault Message Type](configuring-fault-message-type-6dfaa7a.md)


<a name="import_mt_dt"/>

<!-- import\_mt\_dt -->

## Import Fault Message Type Artifact from Enterprise Service Repository



<a name="import_mt_dt__prereq_tcl_g2x_3xc"/>

## Prerequisites

-   You’ve created an integration package and opened it in edit mode. For more information, see [Packaging Integration Content in SAP Integration Suite](packaging-integration-content-in-sap-integration-suite-89da0a2.md).
-   You've configured connection to ES Repository. For more information, see [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).



## Procedure

1.  Navigate to the *Artifacts* tab and choose *Add* \> *Fault Message Type* to add the fault message type artifact.

2.  In the dialog box, choose *Import from ES Repository*.

3.  *ES Repository* appears as the *Source*. In the *Name* list, select an ES Repository from the list of connected systems. The *Address* and *Location ID* are automatically populated.

4.  Choose *Connect*. A list of available fault message types in ES repository appears.

5.  Select the fault message type that you wish to import.

6.  Select the *Include Dependent Data Types* checkbox if you wish to include the dependent data type objects while importing the fault message type.

    > ### Note:  
    > If you include the dependent data type, these will be referenced as additional data in the fault message type structure. See [Configuring Fault Message Type](configuring-fault-message-type-6dfaa7a.md)

7.  Choose *View Summary* to view a summary of all the artifacts to be imported. From the list of objects, you can view the following object status in the *Information* column:

    -   *Create artifact*: Means that this object will be created for the first time.
    -   *Skips; version already exists*: Means that the selected version of this object already exists in an integration package, which can be reused. Hence, object import is skipped. Duplicate object isn't created.
    -   *Adds new version:* Means that a version of this object already exists in an integration package. But, it is not the latest version, which is being imported from the ES repository. So, latest version of the object is created.
    -   *Error; ID already exists:* Means that an artifact with the same ID as the selected primary fault message type already exists in an integration package. Choose *Resolve*, to assign another ID for this artifact. Then, choose *View Summary*.

8.  Choose *Add*. Import results with the details of created, skipped, failed artifacts appear.

    The artifact is added to the *Artifacts* tab. To further edit, open the artifact in its editor and see [Configuring Fault Message Type](configuring-fault-message-type-6dfaa7a.md)


