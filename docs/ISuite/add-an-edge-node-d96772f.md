<!-- loiod96772ff6f7644df870ebbfb861e75fd -->

# Add an Edge Node

Add an Edge Node that contains a Kubernetes cluster.



<a name="loiod96772ff6f7644df870ebbfb861e75fd__prereq_nbs_lth_vlb"/>

## Prerequisites

-   Create a technical user in SAP Repositories Management at [https://ui.repositories.cloud.sap/](https://ui.repositories.cloud.sap/), log in with your S-User and choose *Add New User*. For more information, see [Manage Technical Users in SAP Repositories Management](https://help.sap.com/docs/RBSC/0a64be17478d4f5ba45d14ab62b0d74c/7e83dfc309834942b441fc2106c5b7f5.html).

-   You have created a technical user \(P-User\) to automatically manage Cloud Connector. For more information, see [Creating a Technical User \(P-User\) Account](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/edcd1a455afb4cb0b6b1b3d148256468.html).

-   \(optional step\) To enable central system monitoring, set up your Identity Authentication Service \(IAS\) tenant . For more information, see [Configuring Single Sign-On for your Identity Authentication Tenant](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/2c4e91eb250a45819086b6c2a956f72f.html).

-   Get the `kubeconfig` file of a cluster via the command-line interfaces. You need to upload this file as one step in the configuration wizard.

-   To check that the required prerequisites for adding an Edge Node are configured properly, see [Prerequisite Validation Procedures](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/b71d5ab83a454ff9a5ed95c1ee8408e2.html).




## Procedure

1.  On the SAP Integration Suite homepage, choose the URL for accessing Edge Lifecycle Management UI.

2.  Choose *Add Edge Node* to start the configuration wizard, where you go through several steps to add an Edge Node that contains a Kubernetes cluster.

3.  Follow the Edge Lifecycle Management procedure [Adding an Edge Node](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/0a222b9c99d94f56abdcfe27f5be0afa.html). Enable High Availability Mode if you want to use the Edge Integration Cell with an HA configuration.




<a name="loiod96772ff6f7644df870ebbfb861e75fd__result_oys_hz4_fvb"/>

## Results

You have downloaded the bootstrapping configuration file `context.cfg`, which is required to run the ELM Bridge.

