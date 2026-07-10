<!-- loio53db5fb382b54bba86abb413bd3711a7 -->

# Importing Content from SAP Process Orchestration System

Import content from an SAP Process Orchestration system and reuse in the cloud world.



<a name="loio53db5fb382b54bba86abb413bd3711a7__section_rd1_tcb_wxb"/>

## What Is System Settings

This setting enables you to connect to an SAP Process Orchestration system so that you reuse the integration content that you already have and avoids the overhead of creating that content again in SAP Integration Suite.

To enable this setting, you've to configure the connectivity to Integration Directory and Enterprise Services Repository. Since these systems are on-premise systems, you must connect to them via Cloud Connector. For more information on *Cloud Connector*, see [SAP Cloud Connector documentation](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/cloud-connector?version=Cloud).



<a name="loio53db5fb382b54bba86abb413bd3711a7__section_qvr_vcb_wxb"/>

## What Are the Steps Involved

API endpoints and subpaths are used to extract data from your SAP Process Orchestration system. Make sure that SAP Destination service can access the following endpoints. See [Destination Service](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/eeb0ec2318fb4dda87830a09ac7a02fa.html).

-   Directory Content

    -   `/CommunicationChannelInService`
    -   `/IntegratedConfigurationInService`
    -   `/SenderAgreementInService`
    -   `/AlertRuleInService`
    -   `/IntegratedConfiguration750InService`
    -   `/ValueMappingInService`
    -   `/ConfigurationScenarioInService`
    -   `/BPMFacadeBeanImplService`
    -   `/ReceiverAgreementInService`
    -   `/InterfaceDeterminationInService`
    -   `/ReceiverDeterminationInService`

-   Enterprise Services Repository \(ESR\) Content

    -   `/rep/read/ext`
    -   `/dir/read/ext`
    -   `/rep/support/SimpleQuery`
    -   `/rep/query/ext`

-   For Message mapping: `/rep/query/`

-   For Value mapping: `/dir/query/`


The endpoints are constructed according in the pattern `<protocol>://<hostname>:<port><endpoint>`. For example, `https://po75-systema.sap:443/AlertRuleInService`. You must use Cloud Connector to securely expose these endpoints:

-   Ensure that Cloud Connector is connected to your subaccount. See [Establish Connections to SAP BTP](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/db9170a7d97610148537d5a84bf79ba2.html?locale=en-US&version=Cloud#establish-connections-to-sap-btp).
-   Create a new HTTP destination \(cloud to on-premise\) with back-end type *SAP Process Integration*. See [Configure Access Control \(HTTP\)](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/e7d4927dbb571014af7ef6ebd6cc3511.html?locale=en-US&version=Cloud).
-   Limit access to the previously mentioned endpoints and subpaths by changing *Access Policy* to *Path And All Sub-Paths*.



<a name="loio53db5fb382b54bba86abb413bd3711a7__section_wp3_ddb_wxb"/>

## How Does This Setting Benefit You

By configuring the connectivity using SAP Integration Suite *System* setting, you avoid creating destinations in your SAP BTP subaccount. This setting in SAP Integration Suite, based on the inputs you provide about your SAP PO system, automatically creates the destination for you in your SAP BTP subaccount. With the connectivity to an SAP PO system in place, you can import content like message mappings, function libraries, and message types. Also, you can migrate your Integrated Configuration Objects \(ICO\) to SAP Integration Suite.

After configuring connectivity to an SAP PO system, you can test the connectivity to the system using the *Test Connection* option.

You can configure connectivity to more than one SAP PO system so that you import content from all of them in one SAP Integration Suite tenant.



<a name="loio53db5fb382b54bba86abb413bd3711a7__section_i4n_52h_yxb"/>

## Changes to Already Configured ES Repository

Until the 2304 release of SAP Integration Suite, this tab was named *ES Repository* where you could configure connectivity to one ES Repository \(ESR\) only. If you had configured an ESR in the past, the same would now appear in the renamed tab. Upon first time editing of the previously configured ESR, you're prompted to enter the user ID and password of the technical user from your SAP PO system.

