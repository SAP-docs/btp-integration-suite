<!-- loio24532330bc1c4092ae461913084864af -->

# Configuring Mutual TLS for Custom Domain Virtual Host

You can configure mutual TLS \(mTLS\) for a custom domain virtual host, which validates the identities of both the web server and the web client.



<a name="loio24532330bc1c4092ae461913084864af__context_qxp_l3f_j1c"/>

## Context

> ### Note:  
> Since client certificate chains are used in the authentication process to establish the identity of clients accessing the API Management service, it is important to ensure that these chains have sufficient security measures in place. Weak client certificate chains lack the necessary security measures and are therefore vulnerable to attacks. As a result, weak client certificate chains have been deprecated. For more detailed information, please [3418201 - Deprecation of Weak Client Certificate Chains in API Management \(sap.corp\)](https://i7p.wdf.sap.corp/sap(bD1lbiZjPTAwMQ==)/bc/bsp/sno/ui_entry/entry.htm?param=69765F6D6F64653D3030312669765F7361706E6F7465735F6E756D6265723D3334313832303126).



<a name="loio24532330bc1c4092ae461913084864af__steps_xzq_hr4_dmb"/>

## Procedure

Run the service using a standard REST client or test console.

Execute the following steps to configure client authenticaton for a new or existing virtual host:

1.  Navigate to the SAP BTP Cockpit and create a service instance using the apiportal-apiaccess plan.

2.  Assign the `APIManagement.SelfService.Administrator` role to your user.

3.  Create a service key for the instance.

4.  From the service key, retrieve the base URL and append the following path to it:`/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests`


You can now use this full URL along with the below details to invoke the service using a standard REST client. For detailed instructions on how to create a service instance and a service key, see [Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).

-   Service URL: https://<url-from-service-key\>/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests
-   Method: POST
-   Request Header: Authentication Bearer <token\>
-   Content Type: application/json
-   Accept: application/json
-   Request Body:

    Create

    > ### Sample Code:  
    > ```
    > {
    >     "accountId" : "subdomain of your subaccount",  
    >     "virtualHostUrl": "prod-apis",
    >     "isDefaultVirtualHostRequest" : false,
    >     "isClientAuthEnabled": true,
    >     "keyStore": "ref://<reference_name>" or "<key_store_name>",
    >     "operation" : "CREATE"
    > }
    > 
    > ```

    Update

    > ### Sample Code:  
    > ```
    > {
    >     "accountId" : "subdomain of your subaccount",  
    >     "virtualHostUrl": "prod-apis",
    >     "isDefaultVirtualHostRequest" : false,
    >     "isClientAuthEnabled": true,
    >     "keyStore": "ref://<reference_name>" or "<key_store_name>",
    >     "virtualHostId":"c269915f-7adc-4f78-bdd0-dd39ffcb079f",
    >     "operation" : "UPDATE"
    > }
    > 
    > ```

    > ### Note:  
    > -   isClientAuthEnabled: This field must be set to "true" to enable mutual TLS.
    > 
    > -   keyStore: This refers to the name of the keystore that should contain the custom domain's public and private key, or the name of the certificate store reference pointing to the keystore. To learn how to create a keystore and upload certificates, see [Manage Certificates](../manage-certificates-c665875.md). Alternatively, you can use a certificate store reference name that points to the keystore containing the custom domain's public and private keys. For more information, see [Working with References](../working-with-references-6f96b64.md).

    > ### Note:  
    > For enabling client authentication \(mutual TLS\) for custom domain virtual host, append `isClientAuthEnabled` and `keyStore` fields to the create/update virtual host request.


> ### Note:  
> After the virtual host is updated, APIs associated to a product using the updated virtual host must be redeployed and republished.

**Related Information**  


[Configuring a Default Domain for a Virtual Host](configuring-a-default-domain-for-a-virtual-host-1085228.md "After successful onboarding, API proxies are assigned a default virtual host URL. Currently, this URL uses the domain &quot;ondemand.com,&quot; which is the common domain for the Business Technology Platform. It’s prefixed with the subdomain consisting of the subaccount name and the data center where the tenant is onboarded. For example, the default host alias could be https://myaccount....eu10.hana.ondemand.com.")

[Configuring a Custom Domain for a Virtual Host](configuring-a-custom-domain-for-a-virtual-host-6b9e5a3.md "The API Management capability enables you to personalize the virtual host URL by configuring a custom domain of your choice. This means that you can have all your APIs displayed as &quot;https://api.bestrun.com/...&quot; if desired. Additionally, you have the option to set up multiple virtual hosts using the same custom domain, such as &quot;https://api1.bestrun.com,&quot; &quot;https://api2.bestrun.com,&quot; and so on.")

[Configuring Mutual TLS for Default Domain Virtual Host](configuring-mutual-tls-for-default-domain-virtual-host-9faf7ce.md "You can configure mutual TLS (mTLS) for default domain virtual host, which validates the identities of both the web server and the web client.")

