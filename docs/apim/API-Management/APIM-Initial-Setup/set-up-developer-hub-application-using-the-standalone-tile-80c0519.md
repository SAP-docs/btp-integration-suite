<!-- loio80c0519ebf1449d9bed37fccf7ba127a -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Set Up Developer Hub Application Using the Standalone Tile

To discover, consume and monitor API from a centralized API catalog, set up the Developer Hub application.



<a name="loio80c0519ebf1449d9bed37fccf7ba127a__prereq_jsv_11n_w5b"/>

## Prerequisites

-   You already have a subaccount and have enable the Cloud Foundry environment in this subaccount.

-   An *API Management, API Business Hub Enterprise* entitlement has been created for your subaccount.

-   You have already set up and configured API portal. For instructions, see [Setting Up API Portal Application Using API Management Standalone Tile](setting-up-api-portal-application-using-api-management-standalone-tile-9d8c7ae.md).




<a name="loio80c0519ebf1449d9bed37fccf7ba127a__context_ytl_tx5_s4b"/>

## Context

Depending upon the license you hold, you can use the *API Management, API Business Hub Enterprise* stand-alone tile to subscribe to the application.

> ### Note:  
> Ensure that you don’t have an instance of a starter plan created in the same subaccount where you plan to create an Developer Hub subscription. Also, note that the API Management capabilities from Integration Suite and API Management subscriptions using the stand-alone tile can’t coexist in the same subaccount.



<a name="loio80c0519ebf1449d9bed37fccf7ba127a__steps_oyn_hsk_bmb"/>

## Procedure

1.  Log on to SAP BTP Cockpit and navigate to your subaccount.

2.  Navigate to *Services* \> *Instances and Subscriptions*, and choose *Create*.

3.  On the *New Instances and Subscriptions* dialog, choose *API Management, API Business Hub Enterprise* as the *Service*, select the *Plan* from the dropdown list, and choose *Create*.

    Wait for the subscription to complete successfully.

4.  To access the Developer Hub, you must first assign the *AuthGroup.SelfService.Admin* role to yourself.

    > ### Note:  
    > If you choose *Go to Application* without assigning the *AuthGroup.SelfService.Admin* role, an application authentication error appears. If the error persists after assigning the role, clear your web browser cache, and log out of the application and log on again.

    To assign the role:

    1.  On the navigation pane, under *Security*, choose *Users*.

    2.  Select your username and under *Role Collections* section, choose *Assign Role Collection*.

    3.  In the resulting dialog box, select the *AuthGroup.SelfService.Admin* role and choose *Assign Role Collection*.


5.  Navigate back to the *Instances and Subscriptions* page, choose *API Management, API Business Hub Enterprise*, select <span class="SAP-icons-V5"></span> Actions , and choose *Go To Application*.

    You’re navigated to the *API Business Hub Enterprise*.

6.  Log on to the Developer Hub application with your IDP user credentials. To register to the Developer Hub as an Application developer, see [Registering on Developer Hub](../registering-on-developer-hub-c85fafe.md).




<a name="loio80c0519ebf1449d9bed37fccf7ba127a__result_kgs_fnq_qpb"/>

## Results

You’re registered as an application developer on the Developer Hub. You can now view the products available in the catalog store.

**Related Information**  


[Assign User Roles in API Management](https://help.sap.com/viewer/de4066bb3f9240e3bfbcd5614e18c2f9/Cloud/en-US/911ca5a620e94ab581fa159d76b3b108.html "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.") :arrow_upper_right:

[Consume API Proxies](../consume-api-proxies-ea561e4.md "Consume API proxies via Developer Hub. In Developer Hub, an application developer registers, explores the API exposed by customers, creates applications, and tests API proxies.")

