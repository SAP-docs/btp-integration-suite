<!-- loiod257fc3a8cc2494cbafce8b2789939de -->

# OData Provisioning

OData Provisioning, a capability of SAP Integration Suite, exposes business data and business logic as OData services on SAP Business Technology Platform, enabling you to run user-centric applications.

The capability supports registering services from SAP Business Suite where connectivity towards data sources is achieved via back-end enablement.

> ### Note:  
> The availability of the OData Provisioning capability is dependent on your SAP Integration Suite service plan. For more information about different service plans, their supported feature set, and regional availability see SAP Notes [2903776](https://help.sap.com/docs/link-disclaimer?site=https://me.sap.com/notes/2903776) and [3536982](https://me.sap.com/notes/3536982).

With this capability, you can gain access to these back-end services without having to install an on-premise SAP Gateway hub system. It is enough to install the non-modifying back-end enablement components of SAP Gateway. The services residing in the back end are enabled and published on the SAP Integration Suite.

The Open Data Protocol \(OData\) has become the standard protocol for releasing data stored in SAP Business Suite applications. It makes the data available for user-centric consumption on any device. The capability caters to the need for a simplified user experience and uses OData services to extract specific data that you can consume using applications.

Classic SAP Business Suite applications rely on SAP Gateway OData services to extract data from back-end systems. SAP Gateway consists of two parts:

-   SAP Gateway back-end enablement - an SAP Gateway component in SAP Business Suite systems
-   SAP Gateway hub \(front-end server\) - an SAP Gateway component in a dedicated SAP Gateway system

The SAP Gateway component in SAP Business Suite back-end systems gathers data from the back-end system. Whereas the SAP Gateway hub component converts the data from an SAP proprietary format to the OData standard. The conversion lets you consume data easily through the user interface.

This capability streamlines the way in which SAP Gateway OData services are exposed to SAP Business Technology Platform. It replaces the need for an SAP Gateway hub \(front-end server\) in the cloud and reduces the total cost of ownership and shifts the responsibility for maintenance and security tasks from you to the cloud provider.

> ### Remember:  
> You need to fulfill the following pre-requisites:
> 
> -   If your SAP back end is based on SAP NetWeaver 7.02, and the IW BEP component version is SP 06 or lesser, implement the note[1816779](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Flaunchpad.support.sap.com%2F%23%2Fnotes%2F1816779) Information published on SAP site. IW\_BEP 200 component is required to enable SAP Services as OData services on OData Provisioning.
> -   If your SAP back end is based on SAP NetWeaver 7.40, and the SAP\_GWFND component is on SP 02 or lesser, implement the note [1816779](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Flaunchpad.support.sap.com%2F%23%2Fnotes%2F1816779) Information published on SAP site.
> -   To register OData services from the SAP Business Suite you need to install a Cloud Connector and perform the necessary configurations for connecting to the on-premise back-end system. For more information, see [Cloud Connector](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/cloud-connector?version=Cloud).

OData Provisioning functionality has previously been offered as a service on Neo and as part of SAP BTP, serverless runtime. If you would like to continue using this functionality, this feature is now available as a capability ofSAP Integration Suite. To know about transitioning from either the service on Neo or SAP BTP, serverless runtime toSAP Integration Suite, see the [Transitioning Guide](https://help.sap.com/docs/integration-suite/transitioning-to-odata-provisioning-capability-in-sap-integration-suite/transitioning-to-odata-provisioning-capability-in-sap-integration-suite?version=CLOUD).

> ### Note:  
> Once you have transitioned from SAP BTP, serverless runtime toSAP Integration Suite, you can no longer access that service interface. If you transition to the SAP Integration Suite and then deactivate the OData Provisioning capability, you can no longer access your data on the previously existing service.

**Related Information**  


[Activating and Managing Capabilities](activating-and-managing-capabilities-2ffb343.md "Activate capabilities for SAP Integration Suite.")

[Runtime Access and Role Assignment for OData Provisioning](runtime-access-and-role-assignment-for-odata-provisioning-b46816c.md "Steps to complete the activation of the OData Provisioning capability by providing runtime access and assigning roles.")

[Feature Matrix for OData Provisioning](feature-matrix-for-odata-provisioning-f184bf1.md "Information on the feature matrix for OData Provisioning capability.")

[Register OData Services](50-Development/register-odata-services-9dfa56a.md "You can register OData services in the SAP Integration Suite to access back-end services from SAP Business Suite .")

[Monitor Errors from OData Provisioning](50-Development/monitor-errors-from-odata-provisioning-e0aeecf.md "Analyze the root cause for errors and where they originated.")

[Transitioning Guide](https://help.sap.com/docs/integration-suite/transitioning-to-odata-provisioning-capability-in-sap-integration-suite/transitioning-to-odata-provisioning-capability-in-sap-integration-suite?version=CLOUD)

