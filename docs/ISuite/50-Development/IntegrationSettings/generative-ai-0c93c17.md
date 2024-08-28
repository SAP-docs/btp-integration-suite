<!-- loio0c93c1713188448caa536bc99d175c2f -->

# Generative AI

As a tenant administrator, learn and activate the feature for AI-based generation of integration flows.

> ### Note:  
> This information is relevant only when you use the Cloud Integration capability as a part of SAP Integration Suite. Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Remember:  
> Currently, the feature is available only on few BTP regions. If your SAP Integration Suite tenant is hosted on one of these regions, you can use the feature:
> 
> -   Amazon Web Services – Japan \(Tokyo\)
> 
> -   Amazon Web Services – Europe \(Frankfurt\)
> 
> -   Amazon Web Services – Australia \(Sydney\)
> 
> -   Amazon Web Services – U.S. East \(VA\)



<a name="loio0c93c1713188448caa536bc99d175c2f__section_wc2_q2c_wbc"/>

## What is AI-Based Generation of Integrations

SAP Integration Suite, specifically the Cloud Integration capability, provides a feature to create integration flows using Generative AI. After you activate the feature, an integration developer has a choice to generate integrations with the assistance from AI. The integration developer must describe the integration scenario when asked. Based on the descriptions and inputs, the Generative AI tool creates an integration flow.



<a name="loio0c93c1713188448caa536bc99d175c2f__section_nfp_nfc_wbc"/>

## Prerequisites

For the Generative AI tool to create integration flows, you must first enable connectivity between your system landscape in the SAP BTP cockpit and SAP Integration Suite. By doing so, your registered SAP applications can expose APIs and events to SAP Integration Suite, which in turn, the Generative AI tool use to create integrations. For more information on how to achieve this, see [Enabling System Landscape for SAP Integration Suite](https://help.sap.com/docs/btp/sap-business-technology-platform/enabling-system-landscape-for-sap-integration-suite?version=Cloud).

The Generative AI tool can create integration flows without the system landscape in place too. But in such cases, the tool creates an integration flow with HTTP adapters on the sender and receiver sides. You must still manually enter most of the parameters that would otherwise be automatically populated by the Generative AI tool.



<a name="loio0c93c1713188448caa536bc99d175c2f__section_r13_4fc_wbc"/>

## Enable AI-Based Generation of Integrations

Follow these steps to enable or disable AI-based generation of integrations:

1.  Go to *Settings* \> *Integrations* \> *Generative AI*.

2.  Choose *Edit*.

3.  Enable the *Generative AI Based Integration Flow Generation* checkbox.

4.  Read and understand the terms and conditions for the usage of AI-based feature. Enable the checkbox at the bottom of the pop-up to provide your consent.

5.  Choose *Accept*.

6.  Choose *Save*.

    The identifier of the user who provided consent to the AI terms and conditions, and the timestamp of are shown on the screen for your reference.


For information about generating integrations using AI, see [Creating an Integration Flow](../creating-an-integration-flow-da53d93.md).

.

