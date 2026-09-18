<!-- loio26dd264f42c948d48c4dc52f41b41ba8 -->

# Importing Value Mapping from Integration Directory

You can import value mappings from the Integration Directory and view in .



<a name="loio26dd264f42c948d48c4dc52f41b41ba8__prereq_yct_s5j_pfc"/>

## Prerequisites

-   You’ve created an integration package and opened it in edit mode. For more information, see [Packaging Integration Content in Cloud Integration](packaging-integration-content-in-cloud-integration-89da0a2.md).
-   You've configured connection to Integration Directory. For more information, see [Configuring Connectivity to an SAP Process Orchestration System](../IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> The supported service packs for importing a value mapping are SAP Process Orchestration 7.5 SP22 and onwards.



## Procedure

1.  Navigate to the *Artifacts* tab and choose *Add* \> *Value Mapping*.

2.  In the dialog box, choose *Import from Integration Directory*

    The import wizard opens up.

3.  In the *Process Orchestration Systems and Artifacts* tab, *Integration Directory* appears as the *Source*. In the *Name* list, select an Integration Directory from the list of connected systems.

    The *Address* and *Location ID* are automatically populated.

4.  Choose *Connect*. A list of available value mappings in integration directory appears.

5.  Select the value mapping that you wish to import.

6.  Choose *Next Step*.

7.  In the *Details* tab, you can view the value mapping you have selected to import. You can update the name and ID of the mapping. The name of value mapping in the table and in the tenant should be unique.

8.  Choose *Review*.

    In the *Review* tab, you can view the name and ID of the mapping.

9.  Choose *Add*.

    The artifact is added to the *Artifacts* tab. To further configure the value mapping, see [Configuring Value Mapping](configuring-value-mapping-40c1827.md).


