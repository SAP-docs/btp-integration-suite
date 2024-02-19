<!-- loiob583b7a62f3c4cfdb50a499250c25c15 -->

# Updating the Connection Request Credentials for an Approved Request \[Classic Design\]

There can be instances where you have to update the credentials once the connection request is approved by the API business hub enterprise admin.



<a name="loiob583b7a62f3c4cfdb50a499250c25c15__prereq_unb_5nc_tpb"/>

## Prerequisites

To update the API Management tenant access credentials, you must first generate it. To generate the credentials from theAPI Management tenants, you must have the *APIPortal. Administrator* role assigned to you.

1.  Log in to the Integration Suite.

2.  Choose the navigation icon on the left and choose *Settings* \> *APIs*.

3.  Choose the *Connection* tab.

4.  Choose *Regenerate Credentials* and *Copy* the access credentials.


> ### Note:  
> The client credentials get generated for *APIPortal .Service.CatalogIntegration* role.



<a name="loiob583b7a62f3c4cfdb50a499250c25c15__context_xmh_dsd_tpb"/>

## Context

To establish the connection between the API Management tenant and the API business hub enterprise, the Client ID and Client Secret created for the API Management tenant is shared during the connection request process.

If you encounter one of the following situations after the connection request has already been approved by the API business hub enterprise admin, you have to update the credentials:

-   The service instance, or the service key gets deleted after the connection between the API Management tenant and the API business hub enterprise was established. In this case, the credentials you were using before the service instance or the service key got deleted becomes invalid.

-   Similarly, if the destination that fetches the API content from theAPI Management tenant workspace gets deleted, the credentials you were using before the destination got deleted becomes invalid.


> ### Note:  
> This document describes the classic design of the API business hub enterprise. To view the documentation for the new design, see [Updating the Connection Request Credentials for an Approved Request \[New Design\]](updating-the-connection-request-credentials-for-an-approved-request-new-design-882e1d9.md).



<a name="loiob583b7a62f3c4cfdb50a499250c25c15__steps_ymh_dsd_tpb"/>

## Procedure

1.  Log on to the *API Business Hub Enterprise*.

2.  Navigate to the *Manage* tab and choose *Establish API Portal Connectivity with API Business Hub Enterprise* tile.

3.  Go to the *Actions* column and select the approved connection request that you want to edit and choose *Re-establish Connection*.

4.  On the *Submit Connection Request* page, enter the *Client ID* and *Client Secret* that you copied earlier from the API Portal.

    Sample credentials:

    ```
    {
      "url": "https://<application name>.cfapps.sap.hana.ondemand.com",
      "tokenurl": "https://<name>.authentication.sap.hana.ondemand.com/oauth/token",
      "certurl": "https://xxxxxx.authentication.cert.sap.hana.ondemand.com",
      "certificate": "xxxxxxxxxxxxxxxxxxx",
      "key": "xxxxxxxxxxxxxx"
    }
    ```

    > ### Note:  
    > The credentials required to establish the connection will be valid for 365 days. Please remember to regenerate them and reestablish the connection within this timeframe. However, any credentials generated prior to February 2024 with a validity of 65 days will remain valid for that specific duration. The 365-day timeframe will apply to all newly generated credentials.

5.  Choose *Save*.




<a name="loiob583b7a62f3c4cfdb50a499250c25c15__result_yk3_ng1_x4b"/>

## Results

You’ve updated the Integration Suite API portal access credentials successfully.

