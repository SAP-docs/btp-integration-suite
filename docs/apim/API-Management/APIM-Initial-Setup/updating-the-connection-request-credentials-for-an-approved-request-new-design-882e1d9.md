<!-- loio882e1d96edc04a069ad99d466ff8a9ff -->

# Updating the Connection Request Credentials for an Approved Request \[New Design\]

There can be instances where you have to update the credentials once the connection request is approved by the API business hub enterprise admin.



<a name="loio882e1d96edc04a069ad99d466ff8a9ff__prereq_unb_5nc_tpb"/>

## Prerequisites

To update the API portal access credentials, you must first generate it. To generate the credentials from the API Portal, you must have the *APIPortal. Administrator* role assigned to you.

1.  Log in to the .

2.  Choose the navigation icon on the left and choose *Settings* \> *APIs*.

3.  Choose the *Connection* tab.

4.  Choose *Regenerate Credentials* and *Copy* the API portal access credentials.


> ### Note:  
> The client credentials get generated for *APIPortal .Service.CatalogIntegration* role.



<a name="loio882e1d96edc04a069ad99d466ff8a9ff__context_xmh_dsd_tpb"/>

## Context

To establish the connection between the API portal and the API business hub enterprise, the client Id and client secret created for the API portal is shared during the connection request process.

If you encounter one of the following situations after the connection request has already been approved by the API business hub enterprise admin, you have to update the credentials:

-   The service instance, or the service key gets deleted after the connection between the API portal and the API business hub enterprise was established. In this case, the credentials you were using before the service instance or the service key got deleted becomes invalid.

-   Similarly, if the destination that fetches the API content from the API portal workspace gets deleted, the credentials you were using before the destination got deleted becomes invalid.


> ### Note:  
> This document describes the new design of the API business hub enterprise. To view the documentation for the classic design, see [Updating the Connection Request Credentials for an Approved Request \[Classic Design\]](updating-the-connection-request-credentials-for-an-approved-request-classic-des-b583b7a.md).



<a name="loio882e1d96edc04a069ad99d466ff8a9ff__steps_ymh_dsd_tpb"/>

## Procedure

1.  Log on to the *API Business Hub Enterprise*.

2.  Navigate to the *Enterprise Manager* \> *API Management Connections* and choose *Approved Requests*.

    The connection requests that are pending for approval are listed on the *Approved Requests* page.

3.  Go to the *Actions* column and select the approved connection request that you want to edit and choose *Re-establish Connection*.

4.  On the *Re-establish Connection* page, enter the access credentials that you copied earlier from the API portal in the *\*API Portal Access Credentials :* text box.

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
    > These credentials will remain valid for a period of 65 days. Please make sure to regenerate them and reestablish the connection within this timeframe.

5.  Choose *Submit*.




<a name="loio882e1d96edc04a069ad99d466ff8a9ff__result_yk3_ng1_x4b"/>

## Results

You’ve updated the Integration Suite API portal access credentials successfully.

