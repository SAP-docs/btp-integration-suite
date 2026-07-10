<!-- loio882e1d96edc04a069ad99d466ff8a9ff -->

# Updating the Connection Request Credentials for an Approved Request

There can be instances where you have to update the credentials once the connection request is approved by the Developer Hub admin.



<a name="loio882e1d96edc04a069ad99d466ff8a9ff__prereq_unb_5nc_tpb"/>

## Prerequisites

To update the API portal access credentials, you must first generate it. To generate the credentials from the SAP Integration Suite API Management tenant , you must have the APIPortal.Administrator role assigned to you.

1.  Log on to SAP Integration Suite.

2.  Choose the navigation icon on the left and choose *Settings* \> *APIs*.

3.  Choose the *Connection* tab.

4.  Choose *Regenerate Credentials* and *Copy* the access credentials.


> ### Note:  
> The client credentials get generated for *APIPortal .Service.CatalogIntegration* role.



<a name="loio882e1d96edc04a069ad99d466ff8a9ff__context_xmh_dsd_tpb"/>

## Context

To establish the connection between the SAP Integration Suite API Management tenant and Developer Hub, the client Id and client secret created for the SAP Integration Suite API Management tenant is shared during the connection request process.

If you encounter one of the following situations after the connection request has already been approved by the Developer Hub admin, you have to update the credentials:

-   The service instance, or the service key gets deleted after the connection between the SAP Integration Suite API Management tenant and Developer Hub was established. In this case, the credentials you were using before the service instance or the service key got deleted becomes invalid.

-   Similarly, if the destination that fetches the API content from the SAP Integration Suite API Management tenant workspace gets deleted, the credentials you were using before the destination got deleted becomes invalid.




<a name="loio882e1d96edc04a069ad99d466ff8a9ff__steps_ymh_dsd_tpb"/>

## Procedure

1.  Log on to **Developer Hub**.

2.  Navigate to the *Admin Center* \> *API Management Connections* and choose *Approved Requests*.

    The connection requests that are pending for approval are listed on the *Approved Requests* page.

3.  Go to the *Actions* column and select the approved connection request that you want to edit and choose *Re-establish Connection*.

4.  On the *Re-establish Connection* page, enter the access credentials that you copied earlier from the SAP Integration Suite API Management tenant in the *\*API Portal Access Credentials :* text box.

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

5.  Choose *Submit*.




<a name="loio882e1d96edc04a069ad99d466ff8a9ff__result_yk3_ng1_x4b"/>

## Results

You’ve updated the SAP Integration Suite API Management tenant access credentials successfully.

