<!-- loioc7bda8c2466143ea9675ef93e23b5147 -->

# Create a Connection Request for the Centralized Developer Hub

Create a request to connect the SAP Integration Suite API Management tenant to Developer Hub. You need to establish this connection to publish the content of the SAP Integration Suite API Management tenant on Developer Hub.



<a name="loioc7bda8c2466143ea9675ef93e23b5147__prereq_wnz_n4r_f4b"/>

## Prerequisites

-   To establish connections between the Developer Hub and SAP Integration Suite API Management tenants, a Cloud Foundry space should be created in the sub-account from where Developer Hub is hosted.

-   To establish a connection between an SAP Integration Suite API Management tenant and the centralised Developer Hub which is available in a different sub-account, you must ensure that the Developer Hub capability is not enabled in the same sub-account as that of the API portal.

-   The following role collections should be assigned to you:
    -   AuthGroup.API.Admin

    -   APIPortal.Administrator: To generate the access credentials from the SAP Integration Suite API Management tenant, you must have the *APIPortal. Administrator* role assigned to you.

    -   AuthGroup.APIPortalRegistration: You need this role to create a connection request and update the connection request credentials.

    -   APIPortal Service.CatalogIntegration: You need to have this role assigned to you as the client credentials is generated for this role.


-   Generate the access credentials to establish the connection.

    1.  Log on to SAP Integration Suite.

    2.  Choose the navigation icon on the left and choose *Settings* \> *APIs*.

    3.  Choose the *Connection* tab.

    4.  Follow the onscreen instructions under **Connect the API Portal to the centralized Developer Hub** to generate the SAP Integration Suite API Management tenant access credentials.


    > ### Note:  
    > The client credentials get generated for the *APIPortal .Service.CatalogIntegration* role.




<a name="loioc7bda8c2466143ea9675ef93e23b5147__context_qgy_2ph_k5b"/>

## Context

The Developer Hub administrator identifies which existing or new Developer Hub application can accept content from multiple SAP Integration Suite API Management tenants.

> ### Note:  
> Only new SAP Integration Suite subscriptions with API Management capability enabled with the SAP Integration Suite are allowed to set up a connection with the centralized Developer Hub.

> ### Note:  
> You can connect a maximum number of three SAP Integration Suite API portals to the centralized Developer Hub.

Create a new subaccount in Cloud Foundry and set up only the SAP Integration Suite API Management tenant.

For the newly set up SAP Integration Suite API Management tenant, you can request for the Developer Hub connection to be established.

> ### Note:  
> The option to disconnect an SAP Integration Suite API Management tenant from an existing Developer Hub isn’t supported currently.

> ### Note:  
> Once this connection is set up, you can't place a request to severe this connection and establish a new connection with any other centralized Developer Hub.

To create a request to connect the SAP Integration Suite API Management tenant to the centralized Developer Hub.



<a name="loioc7bda8c2466143ea9675ef93e23b5147__steps_rgy_2ph_k5b"/>

## Procedure

1.  Log on to **Developer Hub**.

2.  Navigate to the *Admin Center* \> *Manage Connections* and choose *Approved Requests*.

3.  Choose *Add New Connection*.

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
    
    Enter the SAP Integration Suite API Management tenant name that gets displayed on Developer Hub. This name is used to distinguish products that are published from the API portal and likewise for applications created for the product.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    API Portal Access Credentials
    
    </td>
    <td valign="top">
    
    Enter the SAP Integration Suite API Management tenant access credentials that you generated earlier. These credentials are used by Developer Hub to establish the connection.

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
    <tr>
    <td valign="top">
    
    Once this connection is set up, you can't place a request to severe this connection and establish a new connection with any other centralized Developer Hub.
    
    </td>
    <td valign="top">
    
    Select the checkbox to confirm.
    
    </td>
    </tr>
    </table>
    
5.  Choose *Submit*.




<a name="loioc7bda8c2466143ea9675ef93e23b5147__result_s4c_yrs_f4b"/>

## Results

You've submitted the connection request to the Developer Hub administrator. Once the connection request is approved by the administrator, you can start publishing the SAP Integration Suite API Management tenant content to Developer Hub.

> ### Note:  
> You can log on to the SAP Integration Suite API Management tenant and check the connection status. Navigate to *Settings* \> *APIs* and choose *Connection*.
> 
> You can also choose *Test Connection* to get the details about the connectivity status once your connection request is approved. You will get a connection error, if the destination is deleted or configured incorrectly. In case of an error, retry after revalidating the destination configuration.

