<!-- loiodd37a7b07a7c438c980c788981f3ea73 -->

# Updating the Connection Request Credentials for a Pending Request

Update the credentials you've used to establish a connection between the SAP Integration Suite API Management tenant and Developer Hub.



<a name="loiodd37a7b07a7c438c980c788981f3ea73__prereq_unb_5nc_tpb"/>

## Prerequisites

-   Only users who have submitted a connection request and have the AuthGroup.APIPortalRegistration role assigned to them can edit the credentials.

-   To update the SAP Integration Suite API Management tenant access credentials, you must first generate it. To generate the credentials from the SAP Integration Suite API Management tenant, you must have the *APIPortal. Administrator* role assigned to you.

    1.  Log on to SAP Integration Suite.

    2.  Choose the navigation icon on the left and choose *Settings* \> *APIs*.

    3.  Choose the *Connection* tab.

    4.  Choose *Generate Credentials* under **Connect the API Portal to the centralized Developer Hub** and *Copy* the access credentials.


    > ### Note:  
    > The client credentials get generated for the *APIPortal .Service.CatalogIntegration* role.




<a name="loiodd37a7b07a7c438c980c788981f3ea73__context_pd3_h2h_k5b"/>

## Context

The credentials required to access the SAP Integration Suite API Management tenant are shared during the connection request process.

If you encounter one of the following situations when your connection request is in the pending request state, you have to update the credentials:

-   You have submitted incorrect credentials while raising a connection request, and your request is in pending approval state.

-   You've deleted the service instance, or the service key, after the connection request was submitted. In this case, the credentials you used before deleting the service instance or the service key becomes invalid.




<a name="loiodd37a7b07a7c438c980c788981f3ea73__steps_hp3_1fh_k5b"/>

## Procedure

1.  Log on to **Developer Hub**.

2.  Navigate to the *Admin Center* \> *Manage Connections* and choose *Pending Requests*.

3.  Go to the *Actions* column of the connection request that you want to edit and choose *Edit Credentials*.

4.  On the *Edit Credentials for <API Portal Alias Name \>* popup, enter the mandatory *\*API Portal Access Credentials* that you copied earlier from the SAP Integration Suite API Management tenant.

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




<a name="loiodd37a7b07a7c438c980c788981f3ea73__result_idm_rfh_k5b"/>

## Results

You've successfully updated the credentials of the connection request that is pending.

