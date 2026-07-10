<!-- loio1a3bfbcb4b7d48fbbd394d3e4a09fc62 -->

# What Is Migration Tooling?

Learn more about Migration Tooling.

Migration Tooling is a pattern-based feature in the Cloud Integration capability of the SAP Integration Suite that helps you migrate integration objects from SAP Process Orchestration and SAP Process Integration to SAP Integration Suite. Before you migrate an integration objects, evaluate the migration possibility using the Migration Assessment capability of SAP Integration Suite. For more information, see: [Migration Assessment](https://help.sap.com/viewer/37c02ad991d24d33b1472b00c1a05378/CLOUD/en-US/5c5e50ee2d644cc59d864409d5b7871c.html "Find out how to migrate your existing integration scenarios to SAP Integration Suite with Migration Assessment.") :arrow_upper_right:.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_y1m_zyb_lxb"/>

## Prerequisites

To get started with migration, you must:

-   Connect your SAP Process Orchestration System with the Cloud Integration capability of SAP Integration Suite using SAP BTP destinations. See: [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).

-   Though this step is optional, we recommend you to [Create a Scenario Evaluation Request](https://help.sap.com/viewer/37c02ad991d24d33b1472b00c1a05378/CLOUD/en-US/435ec6196a9f4007910b69bcab90937a.html "Assess your integration scenarios using the information from data extraction requests.") :arrow_upper_right: using the Migration Assessment capability to identify if your integration object can be migrated.




<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_n22_ppj_dvb"/>

## Features

-   Migrate integration artifacts from your SAP Process Orchestration and SAP Process Integration systems to SAP Integration Suite as Integration Flows.

-   Currently, migration of Integrated Configuration Objects \(ICO\) and Receiver Determination objects are supported.

-   Migration is currently supported for the following versions of the on-premises software:

    -   7.31 SP28 and above

    -   7.40 SP23 and above

    -   7.50 SP06 and above


-   In Migration Assessment, the possible migration statuses are: *Evaluation required*, *Adjustment required*, and *Ready to migrate*. For details about each status, see [Concepts](https://help.sap.com/viewer/37c02ad991d24d33b1472b00c1a05378/CLOUD/en-US/324507c7c50c45afb822ae5e95af6a9c.html "Get to know the most important concepts used in Migration Assessment.") :arrow_upper_right:.




<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_qnb_q5j_dvb"/>

## Usage of Patterns

The migration tooling analyses a migratable object and maps it with an integration pattern. It's based on these patterns, the migration tooling creates equivalent integration flows in the SAP Integration Suite.

To know more about patterns, see: [Supported Patterns](supported-patterns-ad867ae.md#loioad867aea1fc749a99abc2cf643c94038).



<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_cwg_qtj_dvb"/>

## Supported Components

In the current scope, migration tooling supports the migration of objects that contain certain communication channels, flow steps, and events. See: [Supported Components](supported-components-46b27d1.md).

