<!-- loio09fd33ac55e844d28b3deb385cca316a -->

# Unbinding a Multi-Cloud Foundation Application from an API Management, API portal Service Instance

When you unbind a multi-cloud foundation application from an API Management, API portal service instance, an API proxy is undeployed and the connection between the route service and the multi-cloud foundation application is removed.



<a name="loio09fd33ac55e844d28b3deb385cca316a__prereq_ayd_ym1_f1c"/>

## Prerequisites

-   You have logged on as a `space developer`.
-   You have bound an application to service instance under *API Management, API portal*.



## Procedure

In order to unbind, open the command prompt and enter the following command:

```

cf unbind-route-service sap-cf-domain.com apim-service-instance-name --hostname my-app

<-- Example
cf unbind-route-service cfapps.sap.hana.ondemand.com apim-prod-instance --hostname taxapp
-->
 
```

> ### Note:  
> You can unbind an application from a service only from the command-line interface and not from SAP BTP Cockpit.

