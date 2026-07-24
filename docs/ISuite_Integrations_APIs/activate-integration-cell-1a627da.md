<!-- loio1a627da7b7c5471481fabf6db1e6567b -->

# Activate Integration Cell

Activate Integration Cell runtime in SAP Integration Suite.



<a name="loio1a627da7b7c5471481fabf6db1e6567b__prereq_nbs_lth_vlb"/>

## Prerequisites

-   You have subscribed to SAP Integration Suite in your SAP Business Technology Platform subaccount and have assigned the **Integration\_Provisioner** role collection to yourself. For more information, see [Subscribing and Configuring Initial Access to SAP Integration Suite](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/CLOUD/en-US/8a3c8b7a6b1c4f249bb81d11644ef806.html "Subscribe to the SAP Integration Suite in SAP BTP cockpit and assign the Integration_Provisioner role to gain access.") :arrow_upper_right:.

-   You have activated the API Management capability. For more information, see [Activate and Configure the API Management Capability and Access Developer Hub](activate-and-configure-the-api-management-capability-and-access-developer-hub-2111650.md).




<a name="loio1a627da7b7c5471481fabf6db1e6567b__context_krs_mck_dcc"/>

## Context

Integration Cell is a cloud-based runtime included in the SAP Integration Suite. Before starting the actual deployment of this runtime, you need to activate the Integration Cell option in SAP Integration Suite.

> ### Note:  
> The Integration Cell runtime can be activated within designated SAP BTP regions and Cloud Service Providers.
> 
> For more information, including the full list of supported regions and the future availability schedule, see [3754563](https://me.sap.com/notes/3754563).



<a name="loio1a627da7b7c5471481fabf6db1e6567b__steps_lrs_mck_dcc"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Settings* \> *Runtime*.

3.  Choose *Activate* next to Integration Cell to activate the runtime.

    Once the Integration Cell is activated, the URL to manage the virtual host is displayed. You require the **PI\_Administrator** role collection to access this page. To manage virtual hosts, navigate to *Monitor* \> *Manage Virtual Hosts*. For more information, see [View and Edit Virtual Host for API Artifacts](view-and-edit-virtual-host-for-api-artifacts-a87d799.md).

    To create, design, and monitor integration and API artifacts, ensure that the **PI\_Integration\_Developer** role collection is assigned to you.


