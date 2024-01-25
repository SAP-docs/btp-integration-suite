<!-- loioe609a3efe6d64e1781cbf81ae5592071 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Route Service plan

The API Management as route service plan helps you in managing Cloud Foundry applications by including policies like rate limit, quota, and so on.



<a name="loioe609a3efe6d64e1781cbf81ae5592071__section_njp_xwj_blb"/>

## About the Plan

The service instance you create through this plan allows you to bind to the route service and creates an API Proxy. This API Proxy serves in establishing a secure connection with your Cloud Foundry application and all the calls made to the Cloud Foundry application are routed via*API Management, API portal*.



<a name="loioe609a3efe6d64e1781cbf81ae5592071__section_tvr_2gh_blb"/>

## Prerequisites

-   You've enabled API Management capability using Integration suite and have completed the setup. For more information, refer [Subscribing to Integration Suite](https://help.sap.com/docs/SAP_INTEGRATION_SUITE/51ab953548be4459bfe8539ecaeee98d/8a3c8b7a6b1c4f249bb81d11644ef806.html?version=CLOUD) and [Activating Capabilities](https://help.sap.com/docs/SAP_INTEGRATION_SUITE/51ab953548be4459bfe8539ecaeee98d/2ffb343c163c48a4b3a90f9f3c487328.html?version=CLOUD).

-   You have the `space developer` role assigned to you.




<a name="loioe609a3efe6d64e1781cbf81ae5592071__CreatingAPIMInstance"/>

## Creating an API Management, API portal Service Instance

Create a service instance in *API Management, API portal* to start managing your Cloud Foundry applications.

Follow the below procedure to create a service instance on Cloud Foundry:

1.  In your web browser, open the [SAP BTP Cockpit](https://eu-access.cockpit.btp.cloud.sap).
2.  From your *Subaccount*, navigate to *Spaces* in your Cloud Foundry environment and choose *Services* \> *Service Marketplace.*
3.  Choose *API Management, API portal* \> *Instances* \> *New Instance*.
4.  In the *Create Instance* dialog, choose *apim-as-route-service* plan.
5.  Choose *Next* until you reach the *Confirm* section.
6.  In the section *Confirm*, enter a unique *Instance Name* and choose *Finish*.

> ### Note:  
> The *apim-as-route-service* plan allows you to create multiple service instances and connect to many Cloud Foundry applications using the same Subaccount.



<a name="loioe609a3efe6d64e1781cbf81ae5592071__section_lqb_dck_blb"/>

## Deleting an API Management, API portal Service Instance

Delete an *API Management, API Portal* service instance.

**Prerequisites**

-   You have the `space developer` role assigned to you.
-   You have created a service instance under *API Management, API portal*.

Use the following procedure to delete an API Management service instance on Cloud Foundry.

**Procedure**

1.  In your Web browser, open the*SAP BTP Cockpit*.
2.  In the provider account, choose *Services* \> *Service Marketplace* \> *Instances*.
3.  Select the*API Management, API portal* tile.
4.  Choose *Instances* from the left pane.
5.  From the list of instances visible, select the instance that you want to delete and choose :wastebasket: .
6.  Choose *OK*.



<a name="loioe609a3efe6d64e1781cbf81ae5592071__Binding"/>

## Binding a Cloud Foundry Application to an API Management, API portal Service Instance

Create a service instance and bind the Cloud Foundry application to *API management, API portal* service. When you bind an application, an API proxy is created and a new route is added to the application. The route initially redirects all calls to the proxy URL and then to the application.

**Prerequisites**

-   You have the `space developer` role assigned to you.
-   You have created a service instance under *API Management, API portal*.

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
> *API Management, API portal* supports only English alpha numerics, hyphens \(-\) and underscores \(\_\) characters for "api\_name".
> 
> You can bind an application to a service only from the command-line interface and not from SAP BTP Cockpit.
> 
> Providing a value for the parameter during binding is optional. If you provide a value for api\_name, then the API proxy created in *API Management, API portal* for current binding gets the given name. Also, if an API with the same name exists in the API portal, then the same API proxy is used for the binding. That is, the API proxy end point is registered as the route service URL for the current binding.



<a name="loioe609a3efe6d64e1781cbf81ae5592071__unbinding"/>

## Unbinding a Cloud Foundry Application from an API Management, API portal Service Instance

When you unbind a Cloud Foundry application from an *API Management, API portal* service instance , an API proxy is undeployed and the connection between the route service and the Cloud Foundry application is removed.

**Prerequisites**

-   You have logged on as a `space developer`.
-   You have bound an application to service instance under *API Management, API portal*.

In order to unbind, open the command prompt and enter the following command:

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

