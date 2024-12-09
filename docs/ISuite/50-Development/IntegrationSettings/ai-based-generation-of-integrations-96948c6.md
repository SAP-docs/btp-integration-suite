<!-- loio96948c6b9dff4c2e852e7938f16cb5f9 -->

# AI-Based Generation of Integrations

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



<a name="loio96948c6b9dff4c2e852e7938f16cb5f9__section_wc2_q2c_wbc"/>

## What is AI-Based Generation of Integrations

SAP Integration Suite, specifically the Cloud Integration capability, provides a feature to create integration flows using Generative AI. After you activate the feature, an integration developer has a choice to generate integrations with the assistance from AI. The integration developer must describe the integration scenario when asked. Based on the descriptions and inputs, the Generative AI tool creates an integration flow.



<a name="loio96948c6b9dff4c2e852e7938f16cb5f9__section_nfp_nfc_wbc"/>

## Prerequisites

For the Generative AI tool to create integration flows, you must first enable connectivity between your system landscape in the SAP BTP cockpit and SAP Integration Suite. By doing so, your registered SAP applications can expose APIs and events to SAP Integration Suite, which in turn, the Generative AI tool use to create integrations. For more information on how to achieve this, see [Enabling System Landscape for SAP Integration Suite](https://help.sap.com/docs/btp/sap-business-technology-platform/enabling-system-landscape-for-sap-integration-suite?version=Cloud).

The Generative AI tool can create integration flows without the system landscape in place too. But in such cases, the tool creates an integration flow with HTTP adapters on the sender and receiver sides. You must still manually enter most of the parameters that would otherwise be automatically populated by the Generative AI tool.

For information about generating integrations using AI, see [Creating an Integration Flow](../creating-an-integration-flow-da53d93.md).

