<!-- loio425db2bb73e74783801df7a1d81cacfc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enabling Content Transport, Neo Environment

All the tasks mentioned here are one-time activities. It’s recommended that the tenant administrator performs these tasks to make content transport possible.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

> ### Note:  
> To use the automatic transport options \(CTS+ or Cloud Transport Management\), you need to enable an additional service – Solutions Lifecycle Management. This service is responsible for packaging the integration content objects \(integration packages with their artifacts\) into MTA files and handing them over to the transport mechanism. This service is always needed independently of the transport mechanism, whether CTS+ or Cloud Transport Management.



<a name="loio425db2bb73e74783801df7a1d81cacfc__section_cbb_gbq_3qb"/>

## **Enabling Solutions Lifecycle Management**

You enable the *Solutions Lifecycle Management* service in the subaccounts where your source and target tenants are hosted. This step is a one-time activity. You can do that by performing the following steps:

1.  Log in to your SAP BTP account.
2.  Choose *Services* \> *Solutions Lifecycle Management*.
3.  Choose *Enable*.



<a name="loio425db2bb73e74783801df7a1d81cacfc__section_jvb_jbq_3qb"/>

## Selecting the Transport Mode

The content transport mechanism provides you the flexibility of directly exporting integration content to CTS+ system and Cloud Transport Management, or exporting the content as an MTAR file to a local file system. To use one of these transport modes, you must enable the *Transport Mode* found in the *Settings* \(:gear:\) of your source tenant.

1.  Navigate to *Tenant Settings* \(:gear:\) in the Web UI.

2.  Select the *Transport* tab and choose *Edit*.

3.  In the *Transport Mode* list, select one among *CTS+*, *Transport Management Service*, and *MTAR Download* based on your requirement.


> ### Remember:  
> -   Note that this step needs to be performed on the tenant from which you want to export content. For example, if you're exporting content from your **Test** tenant, you need to perform this step only in the **Test** tenant.
> -   *Transport Settings* are available for you only if you have the tenant administrator role assigned to your account. Assign the role to your user if you don't see the *Settings*\(:gear:\) icon. *Transport Settings*.



<a name="loio425db2bb73e74783801df7a1d81cacfc__section_y5w_mbq_3qb"/>

## Next Steps

You must create HTTP destinations to make connections between your tenant, Solutions Lifecycle Management service, and the CTS+/Cloud Transport Management systems. If you want to use:

-   *MTAR Download* option – create an HTTP destination in Solutions Lifecycle Management.
-   *CTS+* option – create 3 HTTPS destinations and use Cloud Connector to connect your CTS+ system with your Cloud Integration source tenant. Then, create transport nodes and routes.
-   *Cloud Transport Management* option – create 2 HTTP destinations in Solutions Lifecycle Management and 1 HTTP destination each in your SAP BTP Neo and Cloud Foundry subaccounts. Then, create transport nodes and routes.

For detailed information about these destinations, see [Creating HTTP Destinations and Transport Route](creating-http-destinations-and-transport-route-270f353.md).

