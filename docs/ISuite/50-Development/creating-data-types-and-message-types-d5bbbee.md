<!-- loiod5bbbeea37c9401b8e635e8fd2fdad36 -->

# Creating Data Types and Message Types

Data Type and Message Type artifacts can be imported from the Enterprise Services \(ES\) Repository.



<a name="loiod5bbbeea37c9401b8e635e8fd2fdad36__prereq_tcl_g2x_3xb"/>

## Prerequisites

-   You’ve created an integration package. For more information, see [Creating an Integration Package](creating-an-integration-package-9126d79.md).
-   You've configured connection to ES Repository. For more information, see [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).



## Context

You can use the Message Type artifacts in message mapping and integration flows once it's imported from the ES repository. See: [Consuming Message Types in Message Mapping](consuming-message-types-in-message-mapping-34f6345.md)



## Procedure

1.  Choose *Design* \> *Integrations and APIs* to view the list of integration packages.

2.  Select the integration package in which you want to add a Data Type or Message Type and choose *Edit*.

3.  Navigate to the *Artifacts* tab and choose *Add* \> *Data Type* or *Add* \> *Message Type* to add a data Type or message Type artifact.

4.  In the dialog box, *ES Repository* appears as the *Source*. You see the details populated in *Name* and *Address* fields.

5.  Choose *Connect*. A list of available data types or message types in ES repository appears.

6.  Select the data type or message type that you wish to import.

7.  Select the *Include Dependent Data Types* checkbox if you wish to include the dependent data type objects while importing the selected data type or message type.

8.  Choose *View Summary* to view a summary of all the artifacts to be imported. From the list of objects, you can view the following object status in the *Information* column:

    -   *Create artifact*: Means that this object will be created for the first time.
    -   *Skips; version already exists*: Means that the selected version of this object already exists in an integration package, which can be reused. Hence, object import is skipped. Duplicate object isn't created.
    -   *Adds new version:* Means that a version of this object already exists in an integration package. But, it is not the latest version, which is being imported from the ES repository. So, latest version of the object is created.
    -   *Error; ID already exists:* Means that an artifact with the same ID as the selected primary data type or message type already exists in an integration package. Choose *Resolve*, to assign another ID for this artifact. Then, choose *View Summary*.

9.  Choose *Add*. Import results with the details of created, skipped, failed artifacts appear.


