<!-- loio88bac3b622854484a1d1e4353aa8ac73 -->

# Enabling System Landscape in SAP BTP Cockpit for SAP Integration Suite

Learn to include various SAP systems into a formation and thus combine diverse SAP solutions for extended business scenarios.

A registered SAP S/4HANA Cloud system in the SAP BTP cockpit can expose consumption bundles that contain APIs and events. You can easily discover and consume the APIs exposed by the SAP S/4HANA Cloud systems in your system landscape when you develop and extend applications on SAP BTP, Cloud Foundry environment, using SAP Integration Suite. To do this, first you must enable connectivity between your system landscape in SAP BTP cockpit and SAP Integration Suite. The integration requires performing several configuration steps starting with configuration on a global account level, and then, configuration on a subaccount level.



<a name="loio88bac3b622854484a1d1e4353aa8ac73__section_dbc_bbl_xbc"/>

## Prerequisites

You must have a subscription to SAP Integration Suite. For instructions, see [Subscribing and Configuring Initial Access to SAP Integration Suite](../10-InitialSetup/subscribing-and-configuring-initial-access-to-sap-integration-suite-8a3c8b7.md).



<a name="loio88bac3b622854484a1d1e4353aa8ac73__section_npx_bbl_xbc"/>

## Enabling System Landscape

The following procedure outlines the steps you need to perform to consume the APIs of registered SAP S/4HANA Cloud systems within SAP Integration Suite.

1.  Add and then register an SAP system of type **SAP S/4HANA Cloud** in the **System Landscape** page of SAP BTP cockpit.

    To expose information about its APIs and events and show this information on the **System Landscape** page, an SAP system of type **SAP S/4HANA Cloud** must be registered in the SAP BTP cockpit. Only when registered, the system communicates information about its APIs and other technical details across the landscape. See [Extending SAP S/4HANA Cloud in the Cloud Foundry and Kyma Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/extending-sap-s-4hana-cloud-in-cloud-foundry-and-kyma-environment).

2.  Create a formation of type **Integration with SAP Integration Suite** and include the SAP S/4HANA Cloud systems you want to expose to SAP Integration Suite. See [Including Systems in a Formation](https://help.sap.com/docs/btp/sap-business-technology-platform/including-sap-systems-in-formation?version=Cloud).

    > ### Note:  
    > In the formation type **Integration with SAP Integration Suite**, you can include only SAP systems of type **SAP S/4HANA Cloud**.


