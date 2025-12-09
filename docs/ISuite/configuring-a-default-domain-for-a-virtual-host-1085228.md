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

If you want to configure a mutual TLS, see [Configuring Mutual TLS for Default Domain Virtual Host](configuring-mutual-tls-for-default-domain-virtual-host-9faf7ce.md). This process enables you to establish a more secure connection between your API proxy and the client, ensuring that both parties can trust each other's identities.

Using the procedure below, you can perform the following operations:

-   Create a new virtual host with a default domain.
-   Update the alias, keystore, key alias, and truststore for an existing virtual host.
-   Delete an existing virtual host.

To request a custom domain with one-way TLS, perform the following steps:



<a name="loio1085228c10814bc5b1ab135814459538__steps_xzq_hr4_dmb"/>

## Procedure

1.  Run the service using a standard REST client or test console.

    To create a virtual host:

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
        > To enable client authentication \(mutual TLS\) while configuring the virtual host with default domain, see [Configuring Mutual TLS for Default Domain Virtual Host](configuring-mutual-tls-for-default-domain-virtual-host-9faf7ce.md).


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


2.  To update a virtual host:

    1.  Navigate to the SAP BTP Cockpit and create a service instance using the apiportal-apiaccess plan.

    2.  Assign the `APIManagement.SelfService.Administrator` role to your user.

    3.  Create a service key for the instance.

    4.  From the service key, retrieve the base URL and append the following path to it:`/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests`


    You can now use this full URL along with the below details to invoke the service using a standard REST client. For detailed instructions on how to create a service instance and a service key, see[Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).

    You can update the virtualHostUrl, trustStore, and the isDefaultVirtualHostRequest flag.

    You can also convert your default domain virtual host to custom domain by refering to the update section of the [Configuring a Custom Domain for a Virtual Host](configuring-a-custom-domain-for-a-virtual-host-6b9e5a3.md) topic.

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
        > To enable client authentication \(mutual TLS\) while configuring the virtual host with default domain, see [Configuring Mutual TLS for Default Domain Virtual Host](configuring-mutual-tls-for-default-domain-virtual-host-9faf7ce.md).


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


    > ### Note:  
    > After the virtual host is updated, APIs associated to a product using the updated virtual host must be redeployed and republished.

3.  To delete a virtual host:

    > ### Note:  
    > Before deleting a virtual host, ensure the following conditions are met:
    > 
    > -   No proxies are deployed on the virtual host targeted for deletion.
    > -   No proxies \(including those in draft state\) refer to the virtual host.
    > -   No existing proxy revisions are linked to the virtual host.
    > -   The virtual host is not marked as the **Default**.

    1.  Navigate to the SAP BTP Cockpit and create a service instance using the apiportal-apiaccess plan.

    2.  Assign the `APIManagement.SelfService.Administrator` role to your user.

    3.  Create a service key for the instance.

    4.  From the service key, retrieve the base URL and append the following path to it:`/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests`


    You can now use this full URL along with the below details to invoke the service using a standard REST client. For detailed instructions on how to create a service instance and a service key, see[Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).

    -   Service URL: https://<url-from-service-key\>/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests
    -   Method: POST
    -   Request Header: Authentication Bearer <token\>
    -   Content Type: application/json
    -   Request Body:

        > ### Sample Code:  
        > ```
        > {     "virtualHostId":"fa90e5ab-287f-466a-ba9e-5f6f4becc74c",
        >      "operation" : "DELETE"
        > }
        > 
        > ```

        > ### Note:  
        > virtualHostId: This is the unique ID of the virtual host you are trying to delete.
        > 
        > The `virtualHostId` can be retrieved from the following API endpoint: https://<url-from-service-key\>/apiportal/api/1.0/Management.svc/VirtualHosts


    -   Response: 201

        > ### Sample Code:  
        > ```
        > <?xml version="1.0" encoding="utf-8"?>
        > <entry
        >        xmlns="http://www.w3.org/2005/Atom"
        > xmlns:m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"
        > xmlns:d="http://schems.microsoft.com/ado/2007/08dataservics" xml:base="https://apiportalurl:443/apiportal/operations/1.0/Configuration.svc">
        >        <id>htps://apiportalurl:443/apiportal/operations/1.0/Configuration.svc/VirualHostRequests('9406b886-4dba-4931-8bd9-972070162821')</id>
        >        <title type="text">VirtualHostRequests</title>
        >        <updated>2025-09-18T05:07:18.571Z</updated>
        >        <category term="apimgmtconfiguration.VirtualHostRequest" scheme="http://schemas.microsoft.com/ado/2007/08/dataservices/scheme"></category>
        >        <link href="VirtualHostRequests('9406b886-4dba-493-8bd9-972070162821')" rel="edit" title="VirtualHostRequest">/link>
        >        <content type="application/xml">
        >                       <m:properties>
        >                                     <d:accountId>parsec</d:accountId>
        >                                     <d:allocatedPort>0</d:allocatedPort>
        >                                     <d:allocationStatus m:null="true"></d:allocationStatus>
        >                              <d:clusterName>APIRUNTIME_TEST</d:clusterName>
        >                                     <d:id>9406b886-4dba-4931-8bd9-972070162821</d:id>
        >                              <d:isClientAuthEnabled>false</d:isClientAuthEnabled>
        >                       <d:isDefaultVirtualHostRequest>false</d:isDefaultVirtualHostRequest>
        >                              <d:isForCustomDomain>false</d:isForCustomDomain>
        >                                     <d:isForNonSni>false</d:isForNonSni>
        >                                     <d:isTLS>false</d:isTLS>
        >                                     <d:keyStoreAlias m:null="true"></d:keyStoreAlias>
        >                                     <d:keyStoreName m:null="true"></d:keyStoreName>
        >                                     <d:life_cycle m:type="apimgmtconfiguration.History">
        >                                                   <d:changed_at>2025-09-18T05:07:17.976</d:changed_at>
        >                                                   <d:changed_by>sb-apiaccess_1710353586252!b86999|api-portal-xsuaa!b11864</d:changed_by>
        >                                                   <d:created_at>2025-09-18T05:07:17.976</d:created_at>
        >                                                   <d:created_by>sb-apiaccess_1710353586252!b86999|api-portal-xsuaa!b11864</d:created_by>
        >                                     </d:life_cycle>
        >                                     <d:operation>DELETE</d:operation>
        >                                     <d:trustStore m:null="true"></d:trustStore>
        >                                     <d:virtualHostId>262553bf-8d37-4619-9014-761ae184de66</d:virtualHostId>
        >                                     <d:virtualHostUrl m:null="true"></d:virtualHostUrl>
        >                                     <d:lbHost m:null="true"></d:lbHost>
        >                       </m:properties>
        >        </content>
        > </entry>
        > 
        > ```

        > ### Note:  
        > To enable client authentication \(mutual TLS\) while configuring the virtual host with default domain, see [Configuring Mutual TLS for Default Domain Virtual Host](configuring-mutual-tls-for-default-domain-virtual-host-9faf7ce.md).



**Related Information**  


[Configuring a Custom Domain for a Virtual Host](configuring-a-custom-domain-for-a-virtual-host-6b9e5a3.md "The API Management capability enables you to personalize the virtual host URL by configuring a custom domain of your choice. This means that you can have all your APIs displayed as &quot;https://api.bestrun.com/...&quot; if desired. Additionally, you have the option to set up multiple virtual hosts using the same custom domain, such as &quot;https://api1.bestrun.com,&quot; &quot;https://api2.bestrun.com,&quot; and so on.")

[Configuring Mutual TLS for Default Domain Virtual Host](configuring-mutual-tls-for-default-domain-virtual-host-9faf7ce.md "You can configure mutual TLS (mTLS) for default domain virtual host, which validates the identities of both the web server and the web client.")

[Configuring Mutual TLS for Custom Domain Virtual Host](configuring-mutual-tls-for-custom-domain-virtual-host-2453233.md "You can configure mutual TLS (mTLS) for a custom domain virtual host, which validates the identities of both the web server and the web client.")

