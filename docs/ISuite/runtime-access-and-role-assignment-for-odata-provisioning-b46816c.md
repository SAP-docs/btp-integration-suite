<!-- loiob46816c20e02415597d5546b1e277e23 -->

# Runtime Access and Role Assignment for OData Provisioning

Steps to complete the activation of the OData Provisioning capability by providing runtime access and assigning roles.





### Before you begin:

-   You've subscribed to SAP Integration Suite. You have the*Integration\_Provisioner*role and can access the SAP Integration Suite. See [Subscribing and Configuring Initial Access to SAP Integration Suite](10-InitialSetup/subscribing-and-configuring-initial-access-to-sap-integration-suite-8a3c8b7.md).
-   You've activated the OData Provisioning capability. See [Activating and Managing Capabilities](activating-and-managing-capabilities-2ffb343.md).
-   You additionally need the role of org member and space developer in the Cloud Foundry space in which SAP Integration Suite is provisioned.

After you activate the OData Provisioning capability, you need to:

-   Create a service instance to get runtime access to registered services
-   Create a service key for the service instance
-   Assign required roles



<a name="loiob46816c20e02415597d5546b1e277e23__section_hjm_4sx_ncc"/>

## Creating a Service Instance and Service Key

> ### Tip:  
> If you created a service instance and service key when using OData Provisioning as a part of the SAP BTP, serverless runtime service, you can reuse them if you've subscribed to SAP Integration Suite on the same subaccount.



### Service Instance Creation

After subscribing to the SAP Integration Suite, and activating the OData Provisioning capability, you can create the service instance as follows:

1.  Navigate to your subaccount in the SAP BTP cockpit.
2.  From the left navigation panel, navigate to *Services* \> *Instances and Subscriptions*.
3.  Choose *Create*.
4.  Choose *Serverless Runtime* \(xfs-runtime\) as the service, and then choose the odpruntime plan and Cloud Foundry space.

    > ### Remember:  
    > If you already have a service instance of the Serverless Runtime \(xfs-runtime\) created under the default plan, please continue to use that same instance.

5.  Enter an instance name, then choose *Next*.
6.  Choose *Create*.

    > ### Note:  
    > The service does not support any parameters.




### Service Key Creation

To create the service key, do the following:

1.  Choose the service instance that you created.
2.  In the right-hand pane, navigate to *Service Keys* \> *Create Service Key*.
3.  In the *Create Service Key* dialog, provide a *Name*.
4.  In the *Configure Binding Parameters* field, choose *JSON* and enter one of the following payloads as per your requirement:

    ****


    <table>
    <tr>
    <th valign="top">

    To create a service key of type:
    
    </th>
    <th valign="top">

    Use payload...
    
    </th>
    <th valign="top">

    Security
    
    </th>
    <th valign="top">

    Sample of generated credentials
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Binding Secret
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Low
    
    </td>
    <td valign="top">
    
    > ### Sample Code:  
    > ```
    > {
    >     "credentials": {
    >         "xsappname": "xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx!xxxxxxx|xxx-service-broker!xxxxxxx",
    >         "client_id": "xx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxx!xxxxxxx|xxx-service-broker!xxxxxxx",
    >         "client_secret": "xxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx=",
    >         "grant_type": "client_credentials",
    >         "token_url": "https://<sub account>.authentication.<region>.hana.ondemand.com/oauth/token"
    >     },
    >     "uri": "https://services.odp.cfapps.<region>.hana.ondemand.com"
    > }
    > ```


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    MTLS
    
    </td>
    <td valign="top">
    
    ```
    	{
        "xsuaa": {
            "credential-type": "x509",
            "x509": {
                "key-length": 2048,
                "validity": 65,
                "validity-type": "DAYS"
            }
        }
    }
    ```

    > ### Note:  
    > The validity of the service key depends on the number of days mentioned in the payload. You must rotate the credentials just before the validity of the key expires, by creating a new service key.

    > ### Note:  
    > If the x509 based service key creation fails, you see the following error:
    > 
    > > ### Sample Code:  
    > > ```
    > > "Service" broker xxxx-broker-xxxxxxx-xxxx-xxx-xxx-xxxxxx failed with: "Failed" to obtain UAA cloning binding information. Status code: "400". Body: {
    > >   "error": "Unsupported credential type"
    > > }
    > > ```
    > 
    > Please raise a support ticket to resolve this issue. Provide the service instance ID for the Serverless Runtime instance which can be obtained from the Instances section of the BTP Cockpit. See [Troubleshooting for OData Provisioning](troubleshooting-for-odata-provisioning-cdcbaa2.md) 


    
    </td>
    <td valign="top">
    
    High
    
    </td>
    <td valign="top">
    
    > ### Sample Code:  
    > ```
    > 
    > {
    >     "credentials": {
    >         "xsappname": "xxxx-xxxx-xxxx-xxxx-xxxxxxxx!xxxx|xxx-service-broker!xxxx",
    >         "certificate": "-----BEGIN CERTIFICATE-----\nxxxx\n-----END CERTIFICATE-----\n-----BEGIN CERTIFICATE-----\nxxxx\n-----END CERTIFICATE-----\n-----BEGIN CERTIFICATE-----\nxxxx\n-----END CERTIFICATE-----\n-----BEGIN CERTIFICATE-----\nxxxx\n-----END CERTIFICATE-----\n",
    >         "certurl": "https://xxxx.authentication.cert.xxxx.hana.ondemand.com",
    >         "client_id": "sb-xxxx-xxxx-xxxx-xxxx-xxxxxxxx!xxxx|xxx-service-broker!xxxx",
    >         "privateKey": "-----BEGIN RSA PRIVATE KEY-----\nxxxx\n-----END RSA PRIVATE KEY-----\n"
    >     },
    >     "uri": "https://services.odp.cfapps.<region>.hana.ondemand.com"
    > }
    > ```


    
    </td>
    </tr>
    </table>
    
5.  Click *Save*. The credentials generated as part of the service key creation can be used for the runtime access of the registered OData services.

    Make a note of these credentials as you will need them in the next steps to obtain a bearer token, in order to access the registered OData services.

    > ### Note:  
    > Once your client is setup you can use it to authenticate against the x509 endpoint by providing the client certificate and key.
    > 
    > Create the certificate.cer and certificate.key files based on the public and private keys obtained from the x509 credentials respectively.
    > 
    > For certificate.cer file:
    > 
    > 1.  Copy the "certificate" value starting from `-----BEGIN CERTIFICATE----- all the way to -----END CERTIFICATE-----\n` \(the certificate value might contain multiple certificates\). Make sure you copy all the certificates.
    > 
    > 2.  Paste it in a text editor. Find and replace all the occurrences of \\\\n by \\n.
    > 
    > 3.  Save the file as `certificate.cer`.
    > 
    > 
    > For certificate.key file:
    > 
    > 1.  Copy the "certificate" value starting from `-----BEGIN RSA PRIVATE KEY-----\n... all the way to ....-----END RSA PRIVATE KEY-----\n`
    > 
    > 2.  Paste it in a text editor. Find and replace all the occurrences of \\\\n by \\n.
    > 
    > 3.  Save the file as `certificate.key`.
    > 
    > 
    > Open a command prompt/terminal in the folder where you have saved the certificate files and execute the following curl command to get the response in the `my-oauth-response.json` file in the same folder. From this file, you can fetch the bearer token from the value of "access\_token".
    > 
    > ```
    > curl --cert certficate.cer --key certificate.key --location --request POST <https://<sub account>.authentication.cert.<region>.hana.ondemand.com">
    > --header 'Content-Type: application/x-www-form-urlencoded' \
    > --data-urlencode 'client_id=<clientId from the servicekey x509 credentials>' \
    > --cert certificate.cer \
    > --key certificate.key \
    >   > my-oauth-response.json
    > 
    > ```




<a name="loiob46816c20e02415597d5546b1e277e23__section_zq2_vdh_rcc"/>

## Assign Roles

You create a role collection and add roles for OData Provisioning, see [Define a Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/define-role-collection). Then assign this role collection to the users who have to access and work with the OData Provisioning capability.

1.  Navigate to the subaccount where you've subscribed to SAP Integration Suite on the SAP BTP Cockpit and add the following roles to a role collection:

    -   *ODPManage*: View and register OData services. Monitor errors, manage metadata validation and cache settings.
    -   *ODPAPIAccess*: Provides access to the service document. You can access the service document from a link against each of the registered OData services.
    -   *APIFullAccess*: Provides runtime access to the registered OData services.

    > ### Note:  
    > When you subscribe to the OData Provisioning capability, you can assign several associated roles. However, for the SAP Integration Suite, only the following roles should be assigned:*ODPManage*, *ODPAPIAccess*, *APIFullAccess*.

2.  To assign these roles:

    1.  Choose *Security* \> *Users* from the left navigation pane.
    2.  Select the username, and under the *Role Collections* section, choose *Assign Role Collection*.
    3.  In the dialog box that opens, select the role collection that you created, and choose *Assign Role Collection*.


