<!-- loio1a3bfbcb4b7d48fbbd394d3e4a09fc62 -->

# What Is Migration Tooling?

Learn more about Migration Tooling.

Migration Tooling is a pattern-based feature in the Cloud Integration capability of the SAP Integration Suite that helps you migrate integration artifacts from SAP Process Orchestration to SAP Integration Suite. Before you migrate an integration artifact, evaluate the migration possibility using the Migration Assessment capability of SAP Integration Suite. For more information, see: [Migration Assessment](migration-assessment-5c5e50e.md).

> ### Note:  
> This information is relevant only when you use the Cloud Integration capability as a part of SAP Integration Suite. Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_y1m_zyb_lxb"/>

## Prerequisites

To get started with migration, you must:

-   Connect your SAP Process Orchestration System with the Cloud Integration capability of SAP Integration Suite using SAP BTP destinations. See: [Connecting an SAP Process Orchestration System](connecting-an-sap-process-orchestration-system-4120ecb.md).

-   Though this step is optional, we recommend you to [Create a Scenario Evaluation Request](create-a-scenario-evaluation-request-435ec61.md) using the Migration Assessment capability to identify if your ICO can be migrated.




<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_n22_ppj_dvb"/>

## Features

-   Migrate integration artifacts from your SAP Process Orchestration system to SAP Integration Suite as Integration Flows. Currently, migration of Integrated Configuration Objects \(ICO\) is supported.

-   Migration is currently supported for the following versions of SAP Process Orchestration:

    -   7.31 SP28 and above

    -   7.40 SP23 and above

    -   7.50 SP06 and above


-   The possible migration statuses for ICOs are: *Evaluation required*, *Adjustment required*, and *Ready to migrate*. For details about each status, see [Concepts](concepts-324507c.md). In the current scope, migration is supported only for ICOs that are in *Adjustment required* and *Ready to migrate* statuses.




<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_qnb_q5j_dvb"/>

## Usage of Patterns

The migration tooling analyses an migratable ICO and maps it with an integration pattern. It's based on these patterns, the migration tooling creates equivalent integration flows in the SAP Integration Suite.

To know more about patterns, see: [Supported Patterns](supported-patterns-ad867ae.md#loioad867aea1fc749a99abc2cf643c94038).



<a name="loio1a3bfbcb4b7d48fbbd394d3e4a09fc62__section_cwg_qtj_dvb"/>

## Supported Components

In the current scope, migration tooling supports the migration of ICOs that contain certain communication channels, flow steps, and events. See: [Supported Components](supported-components-46b27d1.md).

