<!-- loio452c677debfc4fda904310560ab03743 -->

# Enabling Content Transport, Cloud Foundry Environment

All the tasks mentioned here are one-time activities. The tenant administrator performs these tasks to enable content transport.

> ### Note:  
> To use the automatic transport options \(CTS+ or Cloud Transport Management\), you must enable an additional service – *Content Agent Service*. This service is responsible for packaging the integration content objects \(integration packages with their artifacts\) into MTAR files and handing them over to the transport mechanism. This service is always needed independently of the transport mechanism, whether CTS+ or.

Enabling Content Transport involves the following major steps:



<a name="loio452c677debfc4fda904310560ab03743__section_hbk_zhh_vvb"/>

## Subscribing to Content Agent Service

You can follow one of the approaches to use the Content Agent Service:

-   Create a service instance of Content Agent Service – using which you trigger the transport from SAP Integration Suite but you must create an additional destination in SAP BTP cockpit. See [Create Instance](https://help.sap.com/docs/CONTENT_AGENT_SERVICE/ae1a4f2d150d468d9ff56e13f9898e07/1f45ddc3d6194886802924068724b59f.html) and [Create Service Key](https://help.sap.com/docs/CONTENT_AGENT_SERVICE/ae1a4f2d150d468d9ff56e13f9898e07/c0ec2ba3016644a19cd6322fbc72ea2a.html).

-   Create a subscription of Content Agent Service – using which you trigger the transport from Content Agent Service web UI \(instead of SAP Integration Suite UI\) while there's one less destination to be created. See [Subscribe to Content Agent Service](https://help.sap.com/docs/CONTENT_AGENT_SERVICE/ae1a4f2d150d468d9ff56e13f9898e07/fe2599a57535408ebf1596854fbe6043.html).

    > ### Note:  
    > The Content Agent Service UI method works only if you use Cloud Transport Management as the transport mechanism.


Irrespective of what choice you make, this action must be done in the SAP BTP subaccount where the source SAP Integration Suite tenant is hosted.



<a name="loio452c677debfc4fda904310560ab03743__section_nzz_krk_vvb"/>

## Subscribing to Process Integration Runtime

Follow the instructions mentioned in [Creating Service Instance and Service Key for Inbound Authentication](../40-RemoteSystems/creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md) for the service plan *api*.

When prompted to select a role for the service plan, choose the role *WorkspacePackagesTransport*.



<a name="loio452c677debfc4fda904310560ab03743__section_z44_4rk_vvb"/>

## Selecting the Transport Mode

The content transport mechanism provides you the flexibility of directly exporting integration content to CTS+ and Cloud Transport Management system, or exporting the content as an MTAR file to a local file system. To use either of the modes, you must enable *Transport Mode* found in *Settings*.

Navigate to *Tenant Settings* \> *Integrations* and move to the *Transport* tab. Based on your requirement, select either *CTS+*, or *Transport Management Service*, or *MTAR Download* from the dropdown list.

> ### Remember:  
> -   This step must be performed on the tenant from which you want to export content. For example, if you're exporting content from your **Test** tenant, you need to perform this step only in the **Test** tenant.
> -   You must have the administrator role assigned for Cloud Integration to access the *Transport Settings*. Else reach out to your administrator to enable transport.



<a name="loio452c677debfc4fda904310560ab03743__section_wmn_qrk_vvb"/>

## Next Steps

You must create HTTP destinations to ease connections between your source and target tenants to transport integration packages and artifacts. See [Creating HTTP Destinations and Transport Route](creating-http-destinations-and-transport-route-94057be.md).

