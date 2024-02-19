<!-- loioa7b91e5aca32497ca2b17c671ed2bb42 -->

# Requesting an Additional Virtual Host in Cloud Foundry Environment

Create a new virtual host or update an alias for an existing virtual host in the Cloud Foundry environment.



<a name="loioa7b91e5aca32497ca2b17c671ed2bb42__prereq_lmj_lkg_rz"/>

## Prerequisites

-   You must have a service key for the `APIManagement.SelfService.Administrator` role.

    To know more about creating a service key for accessing APIs in the API portal, see the **Creating a Service Key** section in [Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).

-   You have fetched a valid bearer token. To know more about obtaining a bearer token, see the **Obtaining a Bearer Token** section in [Accessing API Management APIs Programmatically](accessing-api-management-apis-programmatically-24a2c37.md).



<a name="loioa7b91e5aca32497ca2b17c671ed2bb42__context_wzq_hr4_dmb"/>

## Context

Virtual hosts are the base URLs of an API Proxy. They include the protocol \(http or https\), along with the hostname of the API proxy, which maps to a router address and port through DNS. You can configure multiple virtual hosts for a given subscription using the following steps:

-   You can create a new virtual host.
-   You can update an alias of an existing virtual host.

> ### Note:  
> The maximum number of virtual hosts that can be configured for each subaccount through the API portal is 20.



<a name="loioa7b91e5aca32497ca2b17c671ed2bb42__steps_xzq_hr4_dmb"/>

## Procedure

1.  Run the services using a standard REST console.

2.  Service to create a new virtual host:

    -   Service URL: https://<url-from-service-key\>/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests
    -   Method: POST
    -   Request Header: bearer token: fetch
    -   Content Type: application/json
    -   Request Body:

        > ### Sample Code:  
        > ```
        > {
        >     "accountId" : "subdomain of your subaccount",  
        >  
        >     "virtualHostUrl": "testvh12",
        >     "isDefaultVirtualHostRequest" : false,
        >     "operation" : "CREATE"
        > }
        > <!–– accountId - your subdomain account ID
        >       Note: Ensure that the sub-account ID is entered in lowercase.
        > 	  virtualHostUrl -  virtual host alias e.g prod-apis , testapi
        > 	  isDefaultVirtualHostRequest - Value is true, If you want the new virtual host to be
        >                                     the default virtual host, else value is false
        > -->
        > 
        > ```


    -   Response: 201

        > ### Sample Code:  
        > ```
        > {
        >     "d": {
        >         "__metadata": {
        >             "id": "",
        >             "url": "",
        >             "type": "apimgmtconfiguration.VirtualHostRequest"
        >         },
        >         "accountId": "",
        >         "allocatedPort": ,
        >         "allocationStatus": "COMPLETE",
        >         "certStore": null,
        >         "clusterName": "",
        >         "id": "",
        >         "isDefaultVirtualHostRequest": false,
        >         "isForCustomDomain": false,
        >         "isForNonSni": false,
        >         "keyStoreAlias": null,
        >         "keyStoreName": null,
        >         "life_cycle": {
        >             "__metadata": {
        >                 "type": "apimgmtconfiguration.History"
        >             },
        >             "changed_at": "",
        >             "changed_by": "",
        >             "created_at": "",
        >             "created_by": ""
        >         },
        >         "operation": "CREATE",
        >         "virtualHostId": "",
        >         "virtualHostUrl": ""
        >     }
        > }
        > ```

    -   Create an incident on the component OPU-API-OD-OPS by navigating to https://support.sap.com to complete the configuration. Provide the VirtualHostRequest ID details in the ticket. You can retrieve the VirtualHostRequest ID from the location header.

3.  Service to update an alias of an existing virtual host:

    -   Service URL: https://<url-from-service-key\>/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests
    -   Method: POST
    -   Request Header: Bearer Token
    -   Content Type: application/json
    -   Request Body:

        > ### Sample Code:  
        > ```
        > {
        >     "accountId" : "<subdomain of your subaccount>",  
        >  
        >     "virtualHostUrl": "<virtual host alias>",
        >     "isDefaultVirtualHostRequest" : false,
        >     "operation" : "UPDATE",
        > 	 "virtualHostId" : "<id-of-an-existing-Virtual-Host-in-api-portal>"
        > }
        > <!–– accountId - your account ID
        >       Note: Ensure that the sub-account ID is entered in lowercase.
        > 	  virtualHostUrl -  virtual host alias e.g prod-apis , testapi
        > 	  isDefaultVirtualHostRequest - Value is true, If you want the new virtual host to be the default virtual host,
        >                                     else false
        > 	  virtualHostId : Access the API from your browser: https://<url-from-service-key>/apiportal/operations/1.0/Configuration.svc/VirtualHostRequests  
        >  
        > Alternatively, invoke this API using the api portal api acess with an admin service key. 
        > To know more about creating a service key for accessing APIs in the API portal, see the Creating a Service Key section in .
        > 
        > <!-– Example --> 
        > 	GET https://apiprotal-url/apiportal/api/1.0/Management.svc/VirtualHosts/
        > 
        > {
        > 	"d": {
        > 		"results": [
        > 		{
        > 			"__metadata": {
        > 				"id": "https://apiportalurl:443/apiportal/api/1.0/Management.svc/VirtualHosts('689333a2-2f6b-4029-8734-2b36a687e559')",
        > 				"url": "https://apiportalurl:443/apiportal/api/1.0/Management.svc/VirtualHosts('689333a2-2f6b-4029-8734-2b36a687e559')",
        > 				"type": "apiportal.VirtualHost"
        > 			},
        > 			"id": "689333a2-2f6b-4029-8734-2b36a687e559", <!–- required virtualHostId -->
        > 			"isDefault": false,
        > 			"isSSL": true,
        > 			"life_cycle": {
        > 				"__metadata": {
        > 					"type": "apiportal.History"
        > 				},
        > 				"changed_at": "/Date(1487244078853)/",
        > 				"changed_by": "X",
        > 				"created_at": "/Date(1487244078853)/",
        > 				"created_by": "X"
        > 			},
        > 			"name": "689333a2-2f6b-4029-8734-2b36a687e559",
        > 			"projectPath": null,
        > 			"virtual_host": "testvh12.dmzmo.sap.corp",
        > 			"virtual_port": 443
        > 		}]
        > 	}
        > }
        > 
        > -->
        > 
        > ```


    -   Response: 201
    -   Create an incident on the component OPU-API-OD-OPS by navigating to https://support.sap.com to complete the configuration. Provide the VirtualHostRequest ID details in the ticket. You can retrieve the VirtualHostRequest ID from the location header.

    > ### Note:  
    > After the virtual host is updated, APIs associated to a product using the updated virtual host must be redeployed and republished.


**Related Information**  


[Region-Specific IP Addresses Available for API Management Cloud Foundry Environment](region-specific-ip-addresses-available-for-api-management-cloud-foundry-environment-585d639.md "API Management protects your backend services. However, API Management needs to establish connectivity to your backend services during an API call execution.")

[Requesting a Custom Domain for a Virtual Host](requesting-a-custom-domain-for-a-virtual-host-6b9e5a3.md "A virtual host lets you host multiple domain names on API Management capability within Integration Suite.")

[Request for a Two-Way SSL Certificate](request-for-a-two-way-ssl-certificate-9faf7ce.md "Request a two-way SSL certificate for the default domain of the virtual host of your API Management service.")

[User Roles in API Management \(New\)](user-roles-in-api-management-new-911ca5a.md "Similar to other capabilities of the SAP Integration Suite, the API Management capability defines a set of technical roles that grant specific permissions to users. Users can be assigned roles through SAP BTP's role collection concept. While users have the option to create their own role collections, a set of predefined role collections is automatically created when the API Management capability is provisioned.")

[User Roles in API Management](user-roles-in-api-management-7010b58.md "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.")

[Cancel API Management Service Subscription](cancel-api-management-service-subscription-df6df2b.md "You can deactivate your API Management capability from Integration Suite to disable your account from the API Management service.")

