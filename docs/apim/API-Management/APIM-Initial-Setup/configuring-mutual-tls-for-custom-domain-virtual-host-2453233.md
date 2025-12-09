<!-- loio24532330bc1c4092ae461913084864af -->

# Configuring Mutual TLS for Custom Domain Virtual Host

You can configure mutual TLS \(mTLS\) for a custom domain virtual host, which validates the identities of both the web server and the web client.



<a name="loio24532330bc1c4092ae461913084864af__context_qxp_l3f_j1c"/>

## Context

> ### Note:  
> Since client certificate chains are used in the authentication process to establish the identity of clients accessing the API Management service, it is important to ensure that these chains have sufficient security measures in place. Weak client certificate chains lack the necessary security measures and are therefore vulnerable to attacks. As a result, weak client certificate chains have been deprecated. For more detailed information, please [3418201 - Deprecation of Weak Client Certificate Chains in API Management \(sap.corp\)](https://i7p.wdf.sap.corp/sap(bD1lbiZjPTAwMQ==)/bc/bsp/sno/ui_entry/entry.htm?param=69765F6D6F64653D3030312669765F7361706E6F7465735F6E756D6265723D3334313832303126).

Using the procedure below, you can perform the following operations:

-   Create a new virtual host with a custom domain.
-   Update the alias, keystore, key alias, and truststore for an existing virtual host.
-   Delete an existing virtual host.

To configure mutual TLS for custom domain virtual host, perform the following steps:



<a name="loio24532330bc1c4092ae461913084864af__steps_xzq_hr4_dmb"/>

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
    -   Request Header: Authentication Bearer <token\>
    -   Content Type: application/json
    -   Accept: application/json
    -   Request Body:

        > ### Sample Code:  
        > ```
        > {
        >     "accountId" : "subdomain of your subaccount",  
        >     "virtualHostUrl": "prod-apis",
        >     "isDefaultVirtualHostRequest" : false,
        >     "isClientAuthEnabled": true,
        >     "keyStore": "ref://<reference_name>" or "<key_store_name>",
        >     "trustStore": "ref://<reference_name>" or "<trust_store_name>",
        >     "operation" : "CREATE"
        > }
        > 
        > ```


2.  To update a virtual host:

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

        > ### Sample Code:  
        > ```
        > {
        >     "accountId" : "subdomain of your subaccount",  
        >     "virtualHostUrl": "prod-apis",
        >     "isDefaultVirtualHostRequest" : false,
        >     "isClientAuthEnabled": true,
        >     "keyStore": "ref://<reference_name>" or "<key_store_name>",
        >     "trustStore": "ref://<reference_name>" or "<trust_store_name>",
        >     "virtualHostId":"c269915f-7adc-4f78-bdd0-dd39ffcb079f",
        >     "operation" : "UPDATE"
        > }
        > 
        > ```

        > ### Note:  
        > -   isClientAuthEnabled: This field must be set to "true" to enable mutual TLS.
        > 
        > -   keyStore: This refers to the name of the keystore that should contain the custom domain's public and private key, or the name of the certificate store reference pointing to the keystore. To learn how to create a keystore and upload certificates, see [Manage Certificates](../manage-certificates-c665875.md). Alternatively, you can use a certificate store reference name that points to the keystore containing the custom domain's public and private keys. For more information, see [Working with References](../working-with-references-6f96b64.md).
        > 
        > -   trustStore: This refers to the name of the truststore that holds the client certificate, or name of the certificate store reference that points to the trust store. To learn how to create a truststore and upload certificates, see [Manage Certificates](../manage-certificates-c665875.md). Alternatively, you can use a certificate store reference name instead of the truststore name. This reference name points to the truststore that contains the client certificate. For detailed instructions, see [Working with References](../working-with-references-6f96b64.md).
        > 
        >     Please ensure that all your client, intermediate, and root certificates are uploaded to the trustStore.


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


    You can now use this full URL along with the below details to invoke the service using a standard REST client. For detailed instructions on how to create a service instance and a service key, see [Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).

    -   Service URL: https://<url-from-service-key\>/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests
    -   Method: POST
    -   Request Header: Authentication Bearer <token\>
    -   Content Type: application/json
    -   Accept: application/json
    -   Request Body:

        > ### Sample Code:  
        > ```
        > {     "virtualHostId":"fa90e5ab-287f-466a-ba9e-5f6f4becc74c",
        >      "operation" : "DELETE"
        > }
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
        > ```



**Related Information**  


[Configuring a Default Domain for a Virtual Host](configuring-a-default-domain-for-a-virtual-host-1085228.md "After successful onboarding, API proxies are assigned a default virtual host URL. Currently, this URL uses the domain &quot;ondemand.com,&quot; which is the common domain for the Business Technology Platform. It’s prefixed with the subdomain consisting of the subaccount name and the data center where the tenant is onboarded. For example, the default host alias could be https://myaccount....eu10.hana.ondemand.com.")

[Configuring a Custom Domain for a Virtual Host](configuring-a-custom-domain-for-a-virtual-host-6b9e5a3.md "The API Management capability enables you to personalize the virtual host URL by configuring a custom domain of your choice. This means that you can have all your APIs displayed as &quot;https://api.bestrun.com/...&quot; if desired. Additionally, you have the option to set up multiple virtual hosts using the same custom domain, such as &quot;https://api1.bestrun.com,&quot; &quot;https://api2.bestrun.com,&quot; and so on.")

[Configuring Mutual TLS for Default Domain Virtual Host](configuring-mutual-tls-for-default-domain-virtual-host-9faf7ce.md "You can configure mutual TLS (mTLS) for default domain virtual host, which validates the identities of both the web server and the web client.")

