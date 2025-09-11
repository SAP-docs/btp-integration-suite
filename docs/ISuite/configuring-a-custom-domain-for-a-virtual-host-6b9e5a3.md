<!-- loio6b9e5a3430b84fecaac1c994fff6c3ee -->

# Configuring a Custom Domain for a Virtual Host

The API Management capability enables you to personalize the virtual host URL by configuring a custom domain of your choice. This means that you can have all your APIs displayed as "https://api.bestrun.com/..." if desired. Additionally, you have the option to set up multiple virtual hosts using the same custom domain, such as "https://api1.bestrun.com," "https://api2.bestrun.com," and so on.



<a name="loio6b9e5a3430b84fecaac1c994fff6c3ee__prereq_lmj_lkg_rz"/>

## Prerequisites

-   You must have a service key for the `APIManagement.SelfService.Administrator` role.

    To know more about creating a service key for accessing APIs in the API portal, see the **Creating a Service Key** section in [Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).

-   You have fetched a valid bearer token. To know more about obtaining a bearer token, see the **Obtaining a Bearer Token** section in [Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).



<a name="loio6b9e5a3430b84fecaac1c994fff6c3ee__context_tcd_t2b_yyb"/>

## Context

The advantage of establishing your own custom domain with a virtual host is that it protects you from future changes, such as those that may occur when rehosting your APIs.

In addition, you have the option to secure your custom domain with a default one-way TLS or a mutual TLS. A one-way TLS validates only the secure identity of the API proxy, providing encryption and authentication for the server. On the other hand, a mutual TLS validates the identities of both the API proxy and the client, providing mutual authentication.

If you want to configure a mutual TLS, see [Configuring Mutual TLS for Default Domain Virtual Host](configuring-mutual-tls-for-default-domain-virtual-host-9faf7ce.md). This process enables you to establish a more secure connection between your API proxy and the client, ensuring that both parties can trust each other's identities.

> ### Note:  
> You cannot use the SAP Custom Domain Manager described in this [document](https://help.sap.com/docs/custom-domain/custom-domain-service/configuring-custom-domains) to create or update custom domains for virtual hosts.

To request a custom domain with one-way TLS, perform the following steps:



<a name="loio6b9e5a3430b84fecaac1c994fff6c3ee__steps_xzq_hr4_dmb"/>

## Procedure

1.  Run the service using a standard REST client or test console.

    To create a new virtual host:

    1.  Navigate to the SAP BTP Cockpit and create a service instance using the apiportal-apiaccess plan.

    2.  Assign the `APIManagement.SelfService.Administrator` role to your user.

    3.  Create a service key for the instance.

    4.  From the service key, retrieve the base URL and append the following path to it:`/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests`


    You can now use this full URL along with the below details to invoke the service using a standard REST client. For detailed instructions on how to create a service instance and a service key, see [Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).

    -   Service URL: https://<url-from-service-key\>/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests
    -   Method: POST
    -   Request Header: Authorization: Bearer <token\>
    -   Content Type: application/json
    -   Accept: application/json
    -   Request Body:

        > ### Sample Code:  
        > ```
        > {
        >     "accountId" : "subdomain of your subaccount",  
        >     "virtualHostUrl": "apis.customdomain.com",
        >     "isDefaultVirtualHostRequest" : false,
        >     "isForCustomDomain": true,
        >     "keyStoreName": "ref://<reference_name>" or "<key_store_name>",
        >     "keyStoreAlias": "key_store_alias",
        >     "operation" : "CREATE"
        > }
        > 
        > ```

        > ### Note:  
        > -   accountId: This is the subdomain of your subaccount.
        > 
        > -   virtualHostUrl - This is your virtual host URL which is used to access the deployed API proxies, e.g prod-apis.customdomain.com, testapi.customdomain.com.
        > 
        > -   isDefaultVirtualHostRequest -If you want the new virtual host to be the default virtual host, set the value to "true", else set it to "false".
        > 
        > -   isForCustomDomain - Ensure that the value is set to "true".
        > 
        > -   keyStoreName: The keyStoreName parameter refers to the name of the keystore that should contain the custom domain's public and private key, or the name of the certificate store reference pointing to the keystore. To learn how to create a keystore and upload certificates, see [Manage Certificates](50-Development/manage-certificates-c665875.md). Alternatively, you can use a certificate store reference name that points to the keystore containing the custom domain's public and private keys. For more information, see [Working with References](50-Development/working-with-references-6f96b64.md).
        > 
        > -   keyStoreAlias: The keyStoreAlias parameter refers to the name of the keystore certificate containing the custom domain's public and private key. To learn how to create a keystore certificate and upload certificates, see [Manage Certificates](50-Development/manage-certificates-c665875.md).

        > ### Note:  
        > To enable client authentication \(mutual TLS\) while configuring the virtual host with custom domain, see [Configuring Mutual TLS for Default Domain Virtual Host](configuring-mutual-tls-for-default-domain-virtual-host-9faf7ce.md).

    -   Response: 201

        > ### Sample Code:  
        > ```
        > {
        >     "d": {
        >         "__metadata": {
        >             "id": "https://apiportalurl:443/apiportal/api/1.0/Management.svc/VirtualHostRequest('1F02AD6A-A53C-43F4-BF95-F053A8A1469A')",
        >             "uri": "https://apiportalurl:443/apiportal/api/1.0/Management.svc/VirtualHostRequest('1F02AD6A-A53C-43F4-BF95-F053A8A1469A')",
        >             "type": "apimgmtconfiguration.VirtualHostRequest"
        >         },
        >         "accountId": "subdomain of your subaccount",
        >         "allocatedPort": 443,
        >         "allocationStatus": "COMPLETE",
        >         "clusterName": "",
        >         "id": "1F02AD6A-A53C-43F4-BF95-F053A8A1469A",
        >         "isClientAuthEnabled": false,
        >         "isDefaultVirtualHostRequest": false,
        >         "isForCustomDomain": true,
        >         "isForNonSni": false,
        >         "isTLS": false,
        >         "keyStoreAlias": "key_store_alias",
        >         "keyStoreName": "ref://<reference_name>" or "<key_store_name>",
        >         "life_cycle": {
        >             "__metadata": {
        >                 "type": "apimgmtconfiguration.History"
        >             },
        >             "changed_at": "/Date(1707380514905)/",
        >             "changed_by": "sb-apiaccess_1705298659201!b109482|api-portal-xsuaa!b11864",
        >             "created_at": "/Date(1707380504072)/",
        >             "created_by": "sb-apiaccess_1705298659201!b109482|api-portal-xsuaa!b11864"
        >         },
        >         "operation": "CREATE",
        >         "trustStore": null,
        >         "virtualHostId": "c269915f-7adc-4f78-bdd0-dd39ffcb079f",
        >         "virtualHostUrl": "apis.customdomain.com",
        >         "lbHost": "lbHost url"
        >     }
        > }
        >  
        > ```

        The "lbHost" field contains the host URL which is required for the custom domain DNS mapping.


2.  Service to update a virtual host:

    1.  Navigate to the SAP BTP Cockpit and create a service instance using the apiportal-apiaccess plan.

    2.  Assign the `APIManagement.SelfService.Administrator` role to your user.

    3.  Create a service key for the instance.

    4.  From the service key, retrieve the base URL and append the following path to it:`/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests`


    You can now use this full URL along with the below details to invoke the service using a standard REST client. For detailed instructions on how to create a service instance and a service key, see [Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).

    You can update the virtualHostUrl, keyStoreName, keyStoreAlias, trustStore, and the isDefaultVirtualHostRequest flag.

    -   Service URL: https://<url-from-service-key\>/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests
    -   Method: POST
    -   Request Header: Authentication Bearer <token\>
    -   Content Type: application/json
    -   Accept: application/json
    -   Request Body:

        > ### Sample Code:  
        > ```
        > {
        >     "accountId" : "subdomain of your subaccount",  
        >     "virtualHostUrl": "apisupdated.customdomain.com",
        >     "isDefaultVirtualHostRequest" : false,
        >     "isForCustomDomain": true,
        >     "keyStoreName": "ref://<reference_name>" or "<key_store_name>",
        >     "keyStoreAlias": "key_store_alias",
        >     "operation" : "UPDATE",
        >     "virtualHostId":"1F02AD6A-A53C-43F4-BF95-F053A8A1469A"
        > }
        > 
        > ```

        > ### Note:  
        > -   accountId: This is the subdomain of your subaccount.
        > 
        > -   virtualHostUrl - This is your virtual host URL which is used to access the deployed API proxies, e.g prod-apis.customdomain.com, testapi.customdomain.com.
        > 
        > -   isDefaultVirtualHostRequest -If you want the new virtual host to be the default virtual host, set the value to "true", else set it to "false".
        > 
        > -   isForCustomDomain - Ensure that the value is set to "true".
        > 
        > -   keyStoreName: The keyStoreName parameter refers to the name of the keystore that should contain the custom domain's public and private key, or the name of the certificate store reference pointing to the keystore. To learn how to create a keystore and upload certificates, see [Manage Certificates](50-Development/manage-certificates-c665875.md). Alternatively, you can use a certificate store reference name that points to the keystore containing the custom domain's public and private keys. For more information, see [Working with References](50-Development/working-with-references-6f96b64.md).
        > 
        > -   keyStoreAlias: The keyStoreAlias parameter refers to the name of the keystore certificate containing the custom domain's public and private key. To learn how to create a keystore certificate and upload certificates, see [Manage Certificates](50-Development/manage-certificates-c665875.md).
        > 
        > -   virtualHostId: This is the unique ID of the virtual host you are trying to update.

        > ### Note:  
        > To enable client authentication \(mutual TLS\) while configuring the virtual host with custom domain, see [Configuring Mutual TLS for Default Domain Virtual Host](configuring-mutual-tls-for-default-domain-virtual-host-9faf7ce.md).


    -   Response: 201

        > ### Sample Code:  
        > ```
        > {
        >     "d": {
        >         "__metadata": {
        >             "id": "https://apiportalurl:443/apiportal/api/1.0/Management.svc/VirtualHosts('689333a2-2f6b-4029-8734-2b36a687e559')",
        >             "uri": "https://apiportalurl:443/apiportal/api/1.0/Management.svc/VirtualHosts('689333a2-2f6b-4029-8734-2b36a687e559')",
        >             "type": "apimgmtconfiguration.VirtualHostRequest"
        >         },
        >         "accountId": "subdomain of your subaccount",
        >         "allocatedPort": 443,
        >         "allocationStatus": "COMPLETE",
        >         "clusterName": "",
        >         "id": "1F02AD6A-A53C-43F4-BF95-F053A8A1469A",
        >         "isClientAuthEnabled": false,
        >         "isDefaultVirtualHostRequest": false,
        >         "isForCustomDomain": true,
        >         "isForNonSni": false,
        >         "isTLS": false,
        >         "keyStoreAlias": "key_store_alias",
        >         "keyStoreName": "ref://<reference_name>" or "<key_store_name>",
        >         "life_cycle": {
        >             "__metadata": {
        >                 "type": "apimgmtconfiguration.History"
        >             },
        >             "changed_at": "/Date(1707380514905)/",
        >             "changed_by": "sb-apiaccess_1705298659201!b109482|api-portal-xsuaa!b11864",
        >             "created_at": "/Date(1707380504072)/",
        >             "created_by": "sb-apiaccess_1705298659201!b109482|api-portal-xsuaa!b11864"
        >         },
        >         "operation": "UPDATE",
        >         "trustStore": null,
        >         "virtualHostId": "c269915f-7adc-4f78-bdd0-dd39ffcb079f",
        >         "virtualHostUrl": "apisupdated",
        >         "lbHost": "lbHost url"
        >     }
        > }
        >  
        > ```

        > ### Note:  
        > The "lbHost" field contains the host URL that is required for the custom domain DNS mapping. If the "lbHost" field does not display any value, please raise a support ticket through the [SAP Support Portal](https://support.sap.com/en/index.html) using the component OPU-API-OD-OPS.


    > ### Note:  
    > After the virtual host is updated, APIs associated to a product using the updated virtual host must be redeployed and republished.


**Related Information**  


[Configuring a Default Domain for a Virtual Host](configuring-a-default-domain-for-a-virtual-host-1085228.md "After successful onboarding, API proxies are assigned a default virtual host URL. Currently, this URL uses the domain &quot;ondemand.com,&quot; which is the common domain for the Business Technology Platform. It’s prefixed with the subdomain consisting of the subaccount name and the data center where the SAP Integration Suite tenant is onboarded. For example, the default host alias could be https://myaccount....eu10.hana.ondemand.com.")

[Configuring Mutual TLS for Default Domain Virtual Host](configuring-mutual-tls-for-default-domain-virtual-host-9faf7ce.md "You can configure mutual TLS (mTLS) for default domain virtual host, which validates the identities of both the web server and the web client.")

[Configuring Mutual TLS for Custom Domain Virtual Host](configuring-mutual-tls-for-custom-domain-virtual-host-2453233.md "You can configure mutual TLS (mTLS) for a custom domain virtual host, which validates the identities of both the web server and the web client.")

[Configuring Additional Virtual Host in Cloud Foundry Environment](configuring-additional-virtual-host-in-cloud-foundry-environment-a7b91e5.md "A virtual host allows you to host multiple domain names on the API Management capability within SAP Integration Suite.")

