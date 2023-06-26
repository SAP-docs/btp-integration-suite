<!-- loio80c0519ebf1449d9bed37fccf7ba127a -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Set Up API business hub enterprise Application Using the Standalone Tile

To discover, consume and monitor API from a centralized API catalog, set up the API business hub enterprise application.



<a name="loio80c0519ebf1449d9bed37fccf7ba127a__prereq_jsv_11n_w5b"/>

## Prerequisites

-   You already have a subaccount and have enable the Cloud Foundry environment in this subaccount.

-   An *API Management, API Business Hub Enterprise* entitlement has been created for your subaccount.

-   You have already set up and configured API portal. For instructions, see [Setting Up API Portal Application Using API Management Standalone Tile](setting-up-api-portal-application-using-api-management-standalone-tile-9d8c7ae.md).




<a name="loio80c0519ebf1449d9bed37fccf7ba127a__context_ytl_tx5_s4b"/>

## Context

Depending upon the license you hold, you can use the *API Management, API Business Hub Enterprise* stand-alone tile to subscribe to the application, or you can set up the API business hub enterprise capability from the **Integration Suite** launchpad. To set up API business hub enterprise from **Integration Suite**, see [Setting Up API Management Capability from Integration Suite](setting-up-api-management-capability-from-integration-suite-f6eb433.md).

> ### Note:  
> Ensure that you don’t have an instance of a starter plan created in the same subaccount where you plan to create an API business hub enterprise subscription. Also, note that the API Management capabilities from Integration Suite and API Management subscriptions using the stand-alone tile can’t coexist in the same subaccount.



<a name="loio80c0519ebf1449d9bed37fccf7ba127a__steps_oyn_hsk_bmb"/>

## Procedure

1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

2.  Navigate to *Services* \> *Instances and Subscriptions*, and choose *Create*.

3.  On the *New Instances and Subscriptions* dialog, choose *API Management, API Business Hub Enterprise* as the *Service*, select the *Plan* from the dropdown list, and choose *Create*.

    Wait for the subscription to complete successfully.

4.  To access the API business hub enterprise, you must first assign the *AuthGroup.SelfService.Admin* role to yourself.

    > ### Note:  
    > If you choose *Go to Application* without assigning the *AuthGroup.SelfService.Admin* role, an application authentication error appears. If the error persists after assigning the role, clear your web browser cache, and log out of the application and log on again.

    To assign the role:

    1.  On the navigation pane, under *Security*, choose *Users*.

    2.  Select your username and under *Role Collections* section, choose *Assign Role Collection*.

    3.  In the resulting dialog box, select the *AuthGroup.SelfService.Admin* role and choose *Assign Role Collection*.


5.  Navigate back to the *Instances and Subscriptions* page, choose *API Management, API Business Hub Enterprise*, select <span class="SAP-icons"></span> Actions , and choose *Go To Application*.

    You’re navigated to the *API Business Hub Enterprise*.

6.  Log on to the API business hub enterprise application with your IDP user credentials. To register to the API business hub enterprise as an Application developer, see [Register on API business hub enterprise](../APIM-Development/register-on-api-business-hub-enterprise-c85fafe.md).




<a name="loio80c0519ebf1449d9bed37fccf7ba127a__result_kgs_fnq_qpb"/>

## Results

You’re registered as an application developer on the API business hub enterprise. You can now view the products available in the catalog store.

**Related Information**  




[Configure the API business hub enterprise \[Classic Design\]](../APIM-Development/configure-the-api-business-hub-enterprise-classic-design-7b71b16.md "You can configure the API business hub enterprise to personalize it for your organization.")

[Create an Application \[Classic Design\]](../APIM-Development/create-an-application-classic-design-7b4e71b.md "Create an Application to consume the required APIs.")

[Assign User Roles](assign-user-roles-911ca5a.md "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.")

