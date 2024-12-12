<!-- loio1a3bfbcb4b7d48fbbd394d3e4a09fc62 -->

# What Is Migration Tooling?

Learn more about Migration Tooling.

Migration Tooling is a pattern-based feature in the Cloud Integration capability of the SAP Integration Suite that helps you migrate integration objects from SAP Process Orchestration and SAP Process Integration to SAP Integration Suite. Before you migrate an integration objects, evaluate the migration possibility using the Migration Assessment capability of SAP Integration Suite. For more information, see: [Migration Assessment](migration-assessment-5c5e50e.md).

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_y1m_zyb_lxb"/>

## Prerequisites

To get started with migration, you must:

-   Connect your SAP Process Orchestration System with the Cloud Integration capability of SAP Integration Suite using SAP BTP destinations. See: [Configuring Connectivity to an SAP Process Orchestration System](50-Development/IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).

-   Though this step is optional, we recommend you to [Create a Scenario Evaluation Request](create-a-scenario-evaluation-request-435ec61.md) using the Migration Assessment capability to identify if your integration object can be migrated.




<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_n22_ppj_dvb"/>

## Features

-   Migrate integration artifacts from your SAP Process Orchestration and SAP Process Integration systems to SAP Integration Suite as Integration Flows.

-   Currently, migration of Integrated Configuration Objects \(ICO\) and Receiver Determination objects are supported.

-   Migration is currently supported for the following versions of the on-premises software:

    -   7.31 SP28 and above

    -   7.40 SP23 and above

    -   7.50 SP06 and above


-   In Migration Assessment, the possible migration statuses are: *Evaluation required*, *Adjustment required*, and *Ready to migrate*. For details about each status, see [Concepts](concepts-324507c.md).




<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_qnb_q5j_dvb"/>

## Usage of Patterns

The migration tooling analyses a migratable object and maps it with an integration pattern. It's based on these patterns, the migration tooling creates equivalent integration flows in the SAP Integration Suite.

To know more about patterns, see: [Supported Patterns](supported-patterns-ad867ae.md#loioad867aea1fc749a99abc2cf643c94038).



<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_cwg_qtj_dvb"/>

## Supported Components

In the current scope, migration tooling supports the migration of objects that contain certain communication channels, flow steps, and events. See: [Supported Components](supported-components-46b27d1.md).

