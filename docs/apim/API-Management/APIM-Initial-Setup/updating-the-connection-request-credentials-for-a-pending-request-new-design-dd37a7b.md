<!-- loiodd37a7b07a7c438c980c788981f3ea73 -->

# Updating the Connection Request Credentials for a Pending Request \[New Design\]

Update the credentials you've used to establish a connection between the API portal and the API business hub enterprise.



<a name="loiodd37a7b07a7c438c980c788981f3ea73__prereq_unb_5nc_tpb"/>

## Prerequisites

-   Only the users who submitted the connection request and has the *AuthGroup.APIPortalRegistration* role assigned to themselves can edit the credentials.

-   To update the API portal access credentials, you must first generate it. To generate the credentials from the API Portal, you must have the *APIPortal. Administrator* role assigned to you.

    1.  Log in to the API portal.

    2.  Choose the navigation icon on the left and choose *Onboarding Settings*.

    3.  Choose the *Connection* tab.

    4.  Choose *Generate Credentials* under *Connect the API Portal to the centralized API Business Hub Enterprise* and *Copy* the API portal access credentials.


    > ### Note:  
    > The client credentials get generated for the *APIPortal .Service.CatalogIntegration* role.




<a name="loiodd37a7b07a7c438c980c788981f3ea73__context_pd3_h2h_k5b"/>

## Context

To establish the connection between the API portal and the API business hub enterprise, the API Portal client Id and the client secret is shared during the connection request process.

If you encounter one of the following situations when your connection request is in the pending request state, you have to update the credentials:

-   You have submitted incorrect credentials while raising a connection request, and your request is in pending approval state.

-   You've deleted the service instance, or the service key, after the connection request was submitted. In this case, the credentials you used before deleting the service instance or the service key becomes invalid.


> ### Note:  
> This document describes the new design of the API business hub enterprise. To view the documentation for the classic design, see [Updating the Connection Request Credentials for a Submitted Request \[Classic Design\]](updating-the-connection-request-credentials-for-a-submitted-request-classic-des-eb84854.md).



<a name="loiodd37a7b07a7c438c980c788981f3ea73__steps_hp3_1fh_k5b"/>

## Procedure

1.  Log on to the *API Business Hub Enterprise*.

2.  Navigate to the *Enterprise Manager* \> *Manage Connections* and choose *Pending Requests*.

3.  Go to the *Actions* column of the connection request that you want to edit and choose *Edit Credentials*.

4.  On the *Edit Credentials for <API Portal Alias Name \>* popup, enter the mandatory *\*API Portal Access Credentials* that you copied earlier from the API portal.

    Sample credentials:

    ```
    {
      "url": "https://<application name>.cfapps.sap.hana.ondemand.com",
      "tokenUrl": "https://<name>.authentication.sap.hana.ondemand.com/oauth/token",
      "clientId": "sb-apiaccessxxxxxxxx!xxxx|api-portal-xsuaa!bxxxx",
      "clientSecret": "xxxxxxxxxxxxxxxxxxxxxxx="
    }
    ```

5.  Choose *Save*.




<a name="loiodd37a7b07a7c438c980c788981f3ea73__result_idm_rfh_k5b"/>

## Results

You've successfully updated the credentials of the connection request that is pending.

