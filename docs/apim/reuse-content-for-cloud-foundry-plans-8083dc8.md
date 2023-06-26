<!-- loio8083dc842da24e1d9416cbb3ae34f2c6 -->

# Reuse Content for Cloud Foundry Plans



<a name="loio8083dc842da24e1d9416cbb3ae34f2c6__section_dlm_vw4_cjb"/>

## Deleting an API Management Service Instance

Delete an API Management service instance.

**Prerequisites**

-   You have the space developer role assigned to you.
-   You have created an API Management service instance.

Use the following procedure to delete an API Management service instance on Cloud Foundry.

**Procedure**

1.  In your Web browser, open the SAP BTP Cockpit.
2.  In the provider account, choose *Services* \> *Service Marketplace* \> *Instances*
3.  Select the API Management service tile.
4.  From the list of instances visible, select the instance that you want to delete and choose ![](API-Management/APIM-Initial-Setup/images/delete_instance_8833fbd.png).
5.  Choose *OK*.



<a name="loio8083dc842da24e1d9416cbb3ae34f2c6__section_zlr_lz4_cjb"/>

## Updating an API Management Service Instance

Update user credentials for an API Management service instance.

**Prerequisites**

-   You have created an API Management service instance.
-   You have logged on as a space developer.

**Context**

Perform the following steps to update user credentials for an API Management service instance.

**Procedure**

Open the command-line interface for Cloud Foundry and enter the following command:

> ### Note:  
> You can update a service only from the command-line interface and not from SAP Cloud BTP cockpit.

> ### Sample Code:  
> ```
> 
> cf update-service apim-service-instance-name -c ‘{"apiportal_admin" : "<api portal admin id>", "apiportal_password" : "<api portal password>", "consent" : <value should be true>}’
> 
> <-- Example
> // For Linux/MAC system
> cf update-service apim-prod-instance -c ‘{"apiportal_admin" : "USER", "apiportal_password" : "PASSWORD, "consent" : true}’
> 
> // For Windows system
> cf update-service instance102 -c "{\"apiportal_admin\": \"user\", \"apiportal_password\": \"password\", \"consent\" : true}"
> -->
> ```

> ### Sample Code:  
> For more information on Updating a service, see [Update Service](http://cli.cloudfoundry.org/en-US/cf/update-service.html).



<a name="loio8083dc842da24e1d9416cbb3ae34f2c6__section_xbv_gbp_cjb"/>

## Binding a Cloud Foundry Application to an API Management Service Instance

Create a service instance and bind the Cloud Foundry application to API management. When you bind an application, an API proxy is created and a new route is added to the application. The route initially redirects all calls to the proxy URL and then to the application.

**Prerequisites**

-   You have created an API Management service instance.
-   You have logged on as a space developer.

Open the command-line interface for Cloud Foundry and enter the following command:

> ### Sample Code:  
> ```
> 
> cf bind-route-service sap-cf-domain.com apim-service-instance-name --hostname my-app -c '{"api_name" : ”custom_api_proxy_name”}'
> 
> <-- Example
> //Without parameters
> cf bind-route-service cfapps.sap.hana.ondemand.com apim-prod-instance --hostname taxapp
> 
> //Cloud foundry URL for the above example is https://taxapp.cfapps.sap.hana.ondemand.com
> 
> //With parameters for Linux/MAC system
> cf bind-route-service sap-cf-domain.com apim-service-instance-name --hostname my-app -c '{"api_name" : "test_api"}'
> 
> //With parameters for Windows system
> cf bind-route-service sap-cf-domain.com apim-service-instance-name --hostname my-app -c "{\"api_name\" : \"test_api\"}"
> 
> -->
>  
> ```

> ### Note:  
> API Management supports only English alpha numeric, hyphens \(-\) and underscores \(\_\) characters for "api\_name".
> 
> You can bind an application to a service only from the command-line interface and not from SAP BTP Cockpit.
> 
> Providing a value for the parameter during binding is optional. If you provide a value for api\_name, then the API proxy created in API portal for current binding gets the given name. Also, if an API with the same name exist in the API portal, then the same API proxy is used for the binding. That is, the API proxy end point is registered as the route service URL for the current binding.

For more information on binding an application, see [bind route service](http://cli.cloudfoundry.org/en-US/cf/bind-route-service.html).



<a name="loio8083dc842da24e1d9416cbb3ae34f2c6__section_lz1_kcp_cjb"/>

## Unbinding a Cloud Foundry Application from an API Management Service Instance

Unbind an application to an API Management by deleting the service instance. When you unbind an application, API proxy is eliminated from the application.

**Prerequisites**

-   You have logged on as a space developer
-   You have bound an application to an API Management service instance.

Open the command prompt and enter the following command:

> ### Sample Code:  
> ```
> 
> cf unbind-route-service sap-cf-domain.com apim-service-instance-name --hostname my-app
> 
> <-- Example
> cf unbind-route-service cfapps.sap.hana.ondemand.com apim-prod-instance --hostname taxapp
> -->
>  
> ```

> ### Note:  
> You can unbind an application from a service only from the command-line interface and not from SAP BTP Cockpit.

For more information on unbinding an application, see [Unbind route service](http://cli.cloudfoundry.org/en-US/cf/unbind-route-service.html).

