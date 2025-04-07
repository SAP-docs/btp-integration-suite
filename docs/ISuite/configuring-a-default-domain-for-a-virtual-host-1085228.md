<!-- loio1085228c10814bc5b1ab135814459538 -->

# Configuring a Default Domain for a Virtual Host

After successful onboarding, API proxies are assigned a default virtual host URL. Currently, this URL uses the domain "ondemand.com," which is the common domain for the Business Technology Platform. It’s prefixed with the subdomain consisting of the subaccount name and the data center where the SAP Integration Suite tenant is onboarded. For example, the default host alias could be https://myaccount....eu10.hana.ondemand.com.



<a name="loio1085228c10814bc5b1ab135814459538__prereq_lmj_lkg_rz"/>

## Prerequisites

-   You must have a service key for the `APIManagement.SelfService.Administrator` role.

    To know more about creating a service key for accessing APIs in the API portal, see the **Creating a Service Key** section in [Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).

-   You have fetched a valid bearer token. To know more about obtaining a bearer token, see the **Obtaining a Bearer Token** section in [Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).



<a name="loio1085228c10814bc5b1ab135814459538__context_tcd_t2b_yyb"/>

## Context

If you want to configure a mutual TLS, see [Configuring Mutual TLs for Virtual Host](configuring-mutual-tls-for-virtual-host-9faf7ce.md). This process enables you to establish a more secure connection between your API Proxy and the client, ensuring that both parties can trust each other's identities.

To request a custom domain with one-way TLS, perform the following steps:



<a name="loio1085228c10814bc5b1ab135814459538__steps_xzq_hr4_dmb"/>

## Procedure

1.  Run the services using a standard REST console.

2.  Service to create a new virtual host:

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
        >     "virtualHostUrl": "prod-apis",
        >     "isDefaultVirtualHostRequest" : false,
        >     "operation" : "CREATE"
        > }
        > 
        > ```

        > ### Note:  
        > -   accountId: This is the subdomain of your subaccount.
        > 
        > -   virtualHostUrl - This is your virtual host alias, for example, prod-apis, testapi.
        > 
        >     > ### Note:  
        >     > The virtual host alias allows a maximum of 63 characters.
        > 
        > -   isDefaultVirtualHostRequest -if you want the new virtual host to be the default virtual host, set the value to "true", else set it to "false".

        > ### Note:  
        > To enable client authentication \(mutual TLS\) while configuring the virtual host with default domain, see [Configuring Mutual TLs for Virtual Host](configuring-mutual-tls-for-virtual-host-9faf7ce.md).


    -   Response: 201

        > ### Sample Code:  
        > ```
        > {
        >     "d": {
        >         "__metadata": {
        >             "id": "https://apiportalurl:443/apiportal/api/1.0/Management.svc/VirtualHosts('1F02AD6A-A53C-43F4-BF95-F053A8A1469A')",
        >             "uri": "https://apiportalurl:443/apiportal/api/1.0/Management.svc/VirtualHosts('1F02AD6A-A53C-43F4-BF95-F053A8A1469A')",
        >             "type": "apimgmtconfiguration.VirtualHostRequest"
        >         },
        >         "accountId": "subdomain of your subaccount",
        >         "allocatedPort": 443,
        >         "allocationStatus": "COMPLETE",
        >         "clusterName": "",
        >         "id": "1F02AD6A-A53C-43F4-BF95-F053A8A1469A",
        >         "isClientAuthEnabled": false,
        >         "isDefaultVirtualHostRequest": false,
        >         "isForCustomDomain": false,
        >         "isForNonSni": false,
        >         "isTLS": false,
        >         "keyStoreAlias": null,
        >         "keyStoreName": null,
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
        >         "virtualHostUrl": "prod-apis.sapdefaultdomain",
        >         "lbHost": null
        >     }
        > }
        >  
        > ```


3.  Service to update a virtual host:

    You can update the virtualHostUrl, trustStore, and the isDefaultVirtualHostRequest flag.

    You can also convert your default domain virtual host to custom domain by refering to the update section \(Step 3\) of the [Configuring a Custom Domain for a Virtual Host](configuring-a-custom-domain-for-a-virtual-host-6b9e5a3.md) topic.

    -   Service URL: https://<url-from-service-key\>/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests
    -   Method: POST
    -   Request Header: Authentication Bearer <token\>
    -   Content Type: application/json
    -   Request Body:

        > ### Sample Code:  
        > ```
        > {
        >     "accountId" : "subdomain of your subaccount",  
        >     "virtualHostUrl": "prod-apis-updated",
        >     "isDefaultVirtualHostRequest" : false,
        >     "operation" : "UPDATE",
        >     "virtualHostId":"c269915f-7adc-4f78-bdd0-dd39ffcb079f"
        > }
        > <!–– 
        > -->
        > 
        > ```

        > ### Note:  
        > -   accountId: This is the subdomain of your subaccount.
        > 
        > -   virtualHostUrl - This is your virtual host alias, for example, prod-apis, testapi.
        > 
        >     > ### Note:  
        >     > The virtual host alias allows a maximum of 63 characters.
        > 
        > -   isDefaultVirtualHostRequest -if you want the new virtual host to be the default virtual host, set the value to "true", else set it to "false".
        > 
        > -   virtualHostId: This is the unique ID of the virtual host you are trying to update.

        > ### Note:  
        > To enable client authentication \(mutual TLS\) while configuring the virtual host with default domain, see [Configuring Mutual TLs for Virtual Host](configuring-mutual-tls-for-virtual-host-9faf7ce.md).


    -   Response: 201

        > ### Sample Code:  
        > ```
        > {
        >     "d": {
        >         "__metadata": {
        >             "id": "https://apiportalurl:443/apiportal/api/1.0/Management.svc/VirtualHostRequests('2F02AD6A-A53C-43F4-BF95-F053A8A1469B')",
        >             "uri": "https://apiportalurl:443/apiportal/api/1.0/Management.svc/VirtualHostRequests('2F02AD6A-A53C-43F4-BF95-F053A8A1469B')",
        >             "type": "apimgmtconfiguration.VirtualHostRequest"
        >         },
        >         "accountId": "subdomain of your subaccount",
        >         "allocatedPort": 443,
        >         "allocationStatus": "COMPLETE",
        >         "clusterName": "",
        >         "id": "2F02AD6A-A53C-43F4-BF95-F053A8A1469B",
        >         "isClientAuthEnabled": false,
        >         "isDefaultVirtualHostRequest": false,
        >         "isForCustomDomain": false,
        >         "isForNonSni": false,
        >         "isTLS": false,
        >         "keyStoreAlias": null,
        >         "keyStoreName": null,
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
        >         "virtualHostUrl": "prod-apis-updated.sapdefaultdomain",
        >         "lbHost": null
        >     }
        > }
        >  
        > ```

    -   Response: 201

    > ### Note:  
    > After the virtual host is updated, APIs associated to a product using the updated virtual host must be redeployed and republished.


**Related Information**  


[Configuring a Custom Domain for a Virtual Host](configuring-a-custom-domain-for-a-virtual-host-6b9e5a3.md "The API Management capability enables you to personalize the virtual host URL by configuring a custom domain of your choice. This means that you can have all your APIs displayed as &quot;https://api.bestrun.com/...&quot; if desired. Additionally, you have the option to set up multiple virtual hosts using the same custom domain, such as &quot;https://api1.bestrun.com,&quot; &quot;https://api2.bestrun.com,&quot; and so on.")

[Configuring Mutual TLs for Virtual Host](configuring-mutual-tls-for-virtual-host-9faf7ce.md "You can configure mutual TLs for a virtual host, which validates the identities of both the web server and the web client.")

