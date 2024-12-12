<!-- loio95366b2757d64a89aaa4efa6027a8fb4 -->

# Preparatory Steps

Before you can perform the onboarding steps that are specific to Data Space Integration, you must be onboarded to SAP Integration Suite and have enabled Cloud Integration.



<a name="loio95366b2757d64a89aaa4efa6027a8fb4__prereq_qdm_pnh_41c"/>

## Prerequisites

You've set up your global account and at least one subaccount on SAP BTP. For an overview of the required steps, see [Getting Started in the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/getting-started-in-cloud-foundry-environment?version=Cloud).



## Context

Before you can continue with the onboarding steps that are specific to Data Space Integration, check that you've completed the following steps. Depending on your experience with SAP Integration Suite and Cloud Integration, you might have already completed them and can continue with [Activating the Capability](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/be375cb46b4a4fada37e62b90efcf0d8.html "Learn how to activate the Data Space Integration capability within SAP Integration Suite.") :arrow_upper_right:. Still, to avoid complications later on, check that you meet the following conditions.



## Procedure

-   You must add the entitlement from the global account to your subaccount. In SAP BTP cockpit, go to *Entitlements*, choose *Add Service Plans*, and assign an entitlement with *service* `di-api` and *plan* `api`. Don't forget to save your changes. Note that you must be **global account administrator** to edit entitlements.

-   Data Space Integration is a capability within SAP Integration Suite. Therefore, you first need to **activate Integration Suite** on your SAP Business Technology Platform account. For an overview of the required steps, see [Initial Setup of SAP Integration Suite](10-InitialSetup/initial-setup-of-sap-integration-suite-3dcf507.md) of SAP Integration Suite.

-   Data Space Integration leverages functionalities of the Integration Suite's **Cloud Integration capability**. Activate the capability by following the instructions at [Activating and Managing Capabilities](https://help.sap.com/docs/integration-suite/sap-integration-suite/activating-and-managing-capabilities) for Cloud Integration.




<a name="loio95366b2757d64a89aaa4efa6027a8fb4__result_v1y_n4h_41c"/>

## Results

You're onboarded to SAP Integration Suite with Cloud Integration enabled.



<a name="loio95366b2757d64a89aaa4efa6027a8fb4__postreq_jyr_gph_41c"/>

## Next Steps

Now that you meet all conditions outlined here, continue with [Activating the Capability](https://help.sap.com/viewer/fd99f220bba84308b411ea62c86ff31e/CLOUD/en-US/be375cb46b4a4fada37e62b90efcf0d8.html "Learn how to activate the Data Space Integration capability within SAP Integration Suite.") :arrow_upper_right:.

