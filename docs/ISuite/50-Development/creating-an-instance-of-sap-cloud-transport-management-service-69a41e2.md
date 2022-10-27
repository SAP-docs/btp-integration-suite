<!-- loio69a41e21b6374f3b9c9076abb1d85e53 -->

# Creating an Instance of SAP Cloud Transport Management Service

Create a service instance and a service key of SAP Cloud Transport Management service in your transport subaccount. The service keys details are needed while creating the **TransportManagement** destination.



<a name="loio69a41e21b6374f3b9c9076abb1d85e53__prereq_o5l_1ys_44b"/>

## Prerequisites

Create a **Transport** subaccount and subscribe to SAP Cloud Transport Management service. Set up and subscribe to SAP Cloud Transport Management service as described in [Set Up the Environment to Transport Content Archives directly in an Application](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/8d9490792ed14f1bbf8a6ac08a6bca64.html).

To view and access the SAP Cloud Transport Management service, assign TMS\_ADMIN and TMS\_VIEWER roles to yourself. To set the roles, scroll down to "Steps to Assign User Roles and Permissions" section in [Set Up the Environment to Transport Content Archives directly in an Application](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/8d9490792ed14f1bbf8a6ac08a6bca64.html).



<a name="loio69a41e21b6374f3b9c9076abb1d85e53__steps_qlq_gqs_44b"/>

## Procedure

1.  Create a service instance for SAP Cloud Transport Management service.

    To create the service instance, follow step 9 described in [Set Up the Environment to Transport Content Archives directly in an Application](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/8d9490792ed14f1bbf8a6ac08a6bca64.html).

    > ### Note:  
    > If you don't see the *Cloud Transport Management*, instance under the *Instances* tab on the *Instances and Subscription* page, then you must add the entitlement.
    > 
    > To add the entitlement:
    > 
    > 1.  Choose the *Entitlements* tab from the left pane and choose *Configure Entitlements* \> *Add Service Plans*.
    > 
    > 2.  Under *Entitlements available for this subaccount*, search and select *Cloud Transport Management*.
    > 
    > 3.  On the right pane, select the available plans for Cloud Transport management and choose *Add \( \) Service Plan*.
    > 
    > 4.  On the *Entitlements* page, choose *Save*.

2.  Create a service key for SAP Cloud Transport Management service. To create the service key, follow step 10 described in [Set Up the Environment to Transport Content Archives directly in an Application](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/8d9490792ed14f1bbf8a6ac08a6bca64.html).

    Once the service key is created, make a note of the url, clientid, clientsecret, and token as these details would be needed while creating HTTP destination *TransportManagement*. To copy the details, perform the following steps:

    1.  Choose the service instance *<API Portal, API Management\>* that you created recently, to expand the right-pane.

    2.  To view the credentials, choose the *<Service Key Name\>*.

    3.  Choose the *JSON* tab and copy the details.

        > ### Sample Code:  
        > ```
        > {
        > "uaa": {
        > "clientid": "sb-ebxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx!bxxxx|alm-ts-backend!bxxx",
        > "clientsecret": "xxxxxxxxxxxxxxxxxxxxxxx=",
        > "url": "https://<Space name>.authentication.sap.hana.ondemand.com",
        > "identityzone": "<Space name>",
        > "identityzoneid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        > "tenantid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        > "tenantmode": "dedicated",
        > "sburl": "https://internal-xsuaa.authentication.sap.hana.ondemand.com",
        > "apiurl": "https://api.authentication.sap.hana.ondemand.com",
        > "verificationkey": "-----BEGIN PUBLIC KEY-----xxxxxxxxxx-----END PUBLIC KEY-----",
        > "xsappname": "xxxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx!bxxxxx|alm-ts-backend!bxxx",
        > "subaccountid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        > "uaadomain": "authentication.sap.hana.ondemand.com",
        > "zoneid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
        > },
        > "uri": "https://transport-service-app-backend.ts.cfapps.sap.hana.ondemand.com"
        > ```





<a name="loio69a41e21b6374f3b9c9076abb1d85e53__result_ksq_fgv_n4b"/>

## Results

You've created an instance and a service key of SAP Cloud Transport Management service in the transport subaccount.

