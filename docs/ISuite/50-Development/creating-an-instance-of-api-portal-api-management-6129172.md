<!-- loio6129172da707433fb2fe3168421a3742 -->

# Creating an Instance of API portal, API Management

Create an instance of API portal, API Management in your source subaccount and create a service key. The service key details are needed while creating the **APIManagement** destination.



<a name="loio6129172da707433fb2fe3168421a3742__prereq_cst_znj_v4b"/>

## Prerequisites

Create an API portal, API Management subaccount and subscribe to it. Set it as your source subaccount, from where you can start exporting the API Management content. For more information, see [Set Up API Portal Application](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/29c281b4a002404eba44e91c6fad0d34.html "To create APIs, products, import policy templates, and view applications, set up the API portal application.") :arrow_upper_right:.



<a name="loio6129172da707433fb2fe3168421a3742__steps_qlq_gqs_44b"/>

## Procedure

1.  Create a service instance for API Management, API portal.

    Follow the steps described in "Creating a Service Instance in the API Management,API portal" section in [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).

    > ### Note:  
    > If you don't see the API Management, API portal instance under the *Instances* tab on the *Instances and Subscription* page, then you must add the entitlement.
    > 
    > To add the entitlement:
    > 
    > 1.  Choose the *Entitlements* tab from the left pane and choose *Configure Entitlements* \> *Add Service Plans*.
    > 
    > 2.  Under *Entitlements available for this subaccount*, select API Management,API portal.
    > 
    > 3.  On the right pane, select the available plans for API Management,API portal and choose *Add \( \) Service Plan*.
    > 
    > 4.  On the *Entitlements* page, choose *Save*.

2.  Create a service key for API portal, API Management.

    Follow the steps described in "Creating a Service Key" section in [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).

    > ### Note:  
    > While configuring JSON, only the *APIportal.Administrator* role must be assigned to you and not the "APIPortal.Guest" and "APIManagement.SelfService.Administrator" roles as mentioned in [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).

    Once the service key is created, make a note of the url, clientid, clientsecret, and token as these details would be needed while creating HTTP destination *APIManagement*. To copy the details, perform the following steps:

    1.  Choose the API portal, API Management service instance that you created recently, to expand the right-pane.

    2.  To view the credentials, choose the *<Service Key Name\>*.

    3.  Choose the *JSON* tab and copy the details.

        > ### Sample Code:  
        > ```
        > {
        > 	"url": "https://<apiportal application name>.cfapps.sap.hana.ondemand.com",
        > 	"tokenUrl": "https://<Space name>.authentication.sap.hana.ondemand.com/oauth/token",
        > 	"clientId": "sb-apiaccessxxxxxxxx!xxxx|api-portal-xsuaa!bxxxx",
        > 	"clientSecret": "xxxxxxxxxxxxxxxxxxxxxxx="
        > }
        > 
        > ```





<a name="loio6129172da707433fb2fe3168421a3742__result_ksq_fgv_n4b"/>

## Results

You've created an instance and a service key of API portal, API Management in the source subaccount.

