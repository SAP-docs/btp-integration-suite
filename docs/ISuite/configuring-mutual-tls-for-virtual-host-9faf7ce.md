<!-- loio9faf7cee8dc042569e6d539dc4879bf0 -->

# Configuring Mutual TLs for Virtual Host

You can configure mutual TLs for a virtual host, which validates the identities of both the web server and the web client.



<a name="loio9faf7cee8dc042569e6d539dc4879bf0__context_qxp_l3f_j1c"/>

## Context

> ### Note:  
> Since client certificate chains are used in the authentication process to establish the identity of clients accessing the API Management service, it is important to ensure that these chains have sufficient security measures in place. Weak client certificate chains lack the necessary security measures and are therefore vulnerable to attacks. As a result, weak client certificate chains have been deprecated. For more detailed information, please [3418201 - Deprecation of Weak Client Certificate Chains in API Management \(sap.corp\)](https://i7p.wdf.sap.corp/sap(bD1lbiZjPTAwMQ==)/bc/bsp/sno/ui_entry/entry.htm?param=69765F6D6F64653D3030312669765F7361706E6F7465735F6E756D6265723D3334313832303126).



<a name="loio9faf7cee8dc042569e6d539dc4879bf0__steps_xzq_hr4_dmb"/>

## Procedure

1.  Run the services using a standard REST console.

2.  Service to configure client authenticaton for a new or existing virtual host:

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
        >     "trustStore": "ref://<reference_name>" or "<trust_store_name>",
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
        >     "trustStore": "ref://<reference_name>" or "<trust_store_name>",
        >     "virtualHostId":"c269915f-7adc-4f78-bdd0-dd39ffcb079f",
        >     "operation" : "UPDATE"
        > }
        > 
        > ```

        > ### Note:  
        > -   isClientAuthEnabled: This field must be set to "true" to enable mutual TLS.
        > 
        > -   trustStore: This refers to the name of the truststore that holds the client certificate, or name of the certificate store reference that points to the trust store. To learn how to create a truststore and upload certificates, see [Manage Certificates](50-Development/manage-certificates-c665875.md). Alternatively, you can use a certificate store reference name instead of the truststore name. This reference name points to the truststore that contains the client certificate. For detailed instructions, see [Working with References](50-Development/working-with-references-6f96b64.md).


    > ### Note:  
    > For enabling client authentication \(mutual TLS\) for custom domain virtual host, apend `isClientAuthEnabled` and `trustStore` fields to the create/update virtual host request.

    > ### Note:  
    > After the virtual host is updated, APIs associated to a product using the updated virtual host must be redeployed and republished.


**Related Information**  


[Configuring a Custom Domain for a Virtual Host](configuring-a-custom-domain-for-a-virtual-host-6b9e5a3.md "The API Management capability enables you to personalize the virtual host URL by configuring a custom domain of your choice. This means that you can have all your APIs displayed as &quot;https://api.bestrun.com/...&quot; if desired. Additionally, you have the option to set up multiple virtual hosts using the same custom domain, such as &quot;https://api1.bestrun.com,&quot; &quot;https://api2.bestrun.com,&quot; and so on.")

[Configuring a Default Domain for a Virtual Host](configuring-a-default-domain-for-a-virtual-host-1085228.md "After successful onboarding, API proxies are assigned a default virtual host URL. Currently, this URL uses the domain &quot;ondemand.com,&quot; which is the common domain for the Business Technology Platform. It’s prefixed with the subdomain consisting of the subaccount name and the data center where the SAP Integration Suite tenant is onboarded. For example, the default host alias could be https://myaccount....eu10.hana.ondemand.com.")

