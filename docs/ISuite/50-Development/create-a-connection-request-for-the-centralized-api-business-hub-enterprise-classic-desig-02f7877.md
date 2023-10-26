<!-- loio02f7877360a64c6b8d853fed9b2d9cc6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Connection Request for the Centralized API business hub enterprise \[Classic Design\]

To publish the API portal content on the API business hub enterprise, you must create a request to connect the API portal to the API business hub enterprise.



<a name="loio02f7877360a64c6b8d853fed9b2d9cc6__prereq_wnz_n4r_f4b"/>

## Prerequisites

-   To establish connections between the API business hub enterprise and API portals, a Cloud Foundry space should be created in the sub-account from where the API business hub enterprise is hosted.

-   To establish a connection between an API portal and the centralised API business hub enterprise which is available in a different sub-account, you must ensure that the API business hub enterprise capability is not enabled in the same sub-account as that of the API portal.

-   Raise an offline request to the API business hub enterprise administrator for assigning the *AuthGroup.APIPortalRegistration* role to you.

    > ### Note:  
    > You can't create a connection request, without the *AuthGroup.APIPortalRegistration* role.

-   Generate the access credentials to establish the connection. To generate the credentials from the API Portal, you must have the *APIPortal. Administrator* role assigned to you.

    1.  Log in to the Integration Suite.

    2.  Choose the navigation icon on the left and choose *Settings* \> *APIs*.

    3.  Choose the *Connection* tab.

    4.  Follow the onscreen instructions under *Connect the API Portal to the centralized API Business Hub Enterprise* to generate the Integration Suite API portal access credentials.

        ![](images/ABHE_Connection_a5eb276.png)


    > ### Note:  
    > The client credentials get generated for the *APIPortal .Service.CatalogIntegration* role.




## Context

The API business hub enterprise administrator identifies which existing or new API business hub enterprise application can accept content from multiple API portals.

> ### Note:  
> Only new API Management subscriptions are allowed to set up a connection with the centralized API business hub enterprise.

> ### Note:  
> You can connect a maximum number of 3 API portals to the centralized API business hub enterprise.

Create a new subaccount in Cloud Foundry and set up only the API portal.

For the newly set up API portal, you can request for the API Business Hub Enterprise connection to be established.

> ### Note:  
> The option to disconnect an API portal from an existing API business hub enterprise isn’t supported currently.

> ### Note:  
> Once this connection is set up, you can't place a request to severe this connection and establish a new connection with any other centralized API business hub enterprise.

> ### Note:  
> This document describes the classic design of the API business hub enterprise. To view the documentation for the new design, see [Create a Connection Request for the Centralized API business hub enterprise \[New Design\]](create-a-connection-request-for-the-centralized-api-business-hub-enterprise-new-design-c7bda8c.md).



## Procedure

1.  Log on to the *API Business Hub Enterprise*.

2.  Navigate to the *Manage* tab and choose *Establish API Portal Connectivity with API Business Hub Enterprise* tile.

3.  Choose :heavy_plus_sign: icon to create a request to connect the API portal to the centralized API business hub enterprise.

    > ### Note:  
    > Once this connection is set up, you can't place a request to severe this connection and establish a new connection with any other centralized API business hub enterprise.

    Choose *OK* on the *Confirmation* screen to proceed.

4.  Fill in the following details on the *Submit Connection Request* page.


    <table>
    <tr>
    <th valign="top">

    Parameters
    
    </th>
    <th valign="top">

    Values
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    API Portal Alias Name
    
    </td>
    <td valign="top">
    
    Enter the API portal name that gets displayed on the API Business Hub Enterprise. This name is used to distinguish products that are published from the API portal and likewise for applications created for the product.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    API Portal Access Credentials
    
    </td>
    <td valign="top">
    
    Enter the API portal access credentials that you generated earlier. These credentials are used by the API Business Hub Enterprise to establish the connection.

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


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Comment
    
    </td>
    <td valign="top">
    
    Provide the details to the approver about the need for the connection request.
    
    </td>
    </tr>
    </table>
    
5.  Choose *Submit*.




<a name="loio02f7877360a64c6b8d853fed9b2d9cc6__result_s4c_yrs_f4b"/>

## Results

You've submitted the connection request to the API business hub enterprise administrator. Once the connection request is approved by the administrator, you can start publishing the API portal content to the API business hub enterprise.

> ### Note:  
> You can log on to the API Portal and check the connection status. Navigate to :gear: and choose *Connection*.
> 
> You can also choose *Test Connection* to get the details about the connectivity status once your connection request is approved. You will get a connection error, if the destination is deleted or configured incorrectly. In case of an error, retry after revalidating the destination configuration.

**Related Information**  


[Approve the Pending Connection Requests \[Classic Design\]](approve-the-pending-connection-requests-classic-design-b4e6f56.md "As an API business hub enterprise administrator, you must approve or reject the connection request after you receive them.")

