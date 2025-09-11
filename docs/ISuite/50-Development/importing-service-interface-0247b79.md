<!-- loio0247b79c46b240ed9f65f19def7b3bd0 -->

# Importing Service Interface

You can import service interfaces from the Enterprise Services \(ES\) Repository and view in Cloud Integration.

<a name="task_qjy_45j_pfc"/>

<!-- task\_qjy\_45j\_pfc -->

## Import Service Interface from Enterprise Service Repository



<a name="task_qjy_45j_pfc__prereq_yct_s5j_pfc"/>

## Prerequisites

-   You’ve created an integration package and opened it in edit mode. For more information, see [Packaging Integration Content in SAP Integration Suite](packaging-integration-content-in-sap-integration-suite-89da0a2.md).
-   You've configured connection to ES Repository. For more information, see [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).



## Procedure

1.  Navigate to the *Artifacts* tab and choose *Add* \> *Service Interface*.

    The import wizard opens up.

2.  In the *Process Orchestration System* tab, *ES Repository* appears as the *Source*. In the *Name* list, select an ES Repository from the list of connected systems.

    The *Address* and *Location ID* is automaticaly populated.

3.  Choose *Connect*. A list of available service interfaces in ES repository appears.

4.  Select the service interfaces that you wish to import.

    > ### Recommendation:  
    > To avoid conflicts while proxy generation, maintain one to one mapping that is, you must import only one service interface in a package to avoid duplicate objects.

5.  Choose *Next Step*.

6.  Select the *Dependent Resources* to include the dependent objects like data type, message type etc while importing the selected service interface.

7.  Choose *View Summary* to view a summary of all the artifacts to be imported. From the list of objects, you can view the following object status in the *Status* column:

    -   *To be created*: Means that this object will be created for the first time.
    -   *Skips; version already exists*: Means that the selected version of this object already exists in an integration package, which can be reused. Hence, object import is skipped. Duplicate object isn't created.
    -   *Adds new version:* Means that a version of this object already exists in an integration package. But, it is not the latest version, which is being imported from the ES repository. So, latest version of the object is created.
    -   *Error; ID already exists:* Means that an artifact with the same ID as the selected service interface already exists in an integration package. Choose *Resolve*, to assign another ID for this artifact. Then, choose *View Summary*.

8.  Choose *Add*.

    The artifact is added to the *Artifacts* tab. To further view the service interface, see [Viewing Service Interface](viewing-service-interface-53d5c97.md).


