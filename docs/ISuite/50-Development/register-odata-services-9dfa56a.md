<!-- loio9dfa56ab7337457b8b97bc175a7bfaa3 -->

# Register OData Services

You can register OData services in the SAP Integration Suite to access back-end services from SAP Business Suite .



<a name="loio9dfa56ab7337457b8b97bc175a7bfaa3__prereq_wxb_fhx_cfb"/>

## Prerequisites

-   You’ve activated the OData Provisioning capability, and have completed the steps needed for runtimes access and role assignment. See [Activating and Managing Capabilities](../activating-and-managing-capabilities-2ffb343.md) and [Runtime Access and Role Assignment for OData Provisioning](../runtime-access-and-role-assignment-for-odata-provisioning-b46816c.md).
-   You have the *ODPAPIAccess* and *ODPManage* roles assigned, see [Configuring User Access to SAP Integration Suite](../configuring-user-access-to-sap-integration-suite-2c6214a.md).
-   You have installed a Cloud Connector and perform the necessary configurations for connecting to the on-premise back-end system. For more information, see [Cloud Connector](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/cloud-connector?version=Cloud).
-   You have creates a HTTP destination to the service you want to register. See [Create an HTTP destination](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/783fa1c418a244d0abb5f153e69ca4ce.html). While adding the destination, make sure to choose *New Property* and provide an additional `odc` property with the value `true`.

    > ### Note:  
    > The destination URL must be of the SAP Business Suite system where the service implementations are present. The generic URL is `https://<hostname>:<port>/sap/iwbep?sap-client=<client number>`. Hostname, port, and client number depend on the system you’re using.
    > 
    > To get the destination URL:
    > 
    > 1.  In transaction SICF, choose *Execute* \([F8\]\) to display the service tree hierarchy.
    > 2.  Expand the default host and navigate to the IWBEP node \(*default\_host* \> *sap* \> *iwbep*\).
    > 3.  You can register services by exposing SAP Business Suite data as an OData service on SAP Integration Suite. In the context menu of the *iwbep* node, choose *Test Service* \> *Allow*. The URL that you get in the address bar of the browser is the destination URL.
    > 
    > Destinations are used for the outbound communication between a cloud application and an SAP system. The destination contains connection details for remote communication of an application. Use the Destinations editor in the cockpit to configure HTTP destinations to connect your Web application to the Internet or consume an on-premise back-end system via HTTP\(S\)




## Procedure

1.  In the Integration Suite, navigate to *Configure* \> *OData Services*.

2.  Choose *Register*.

3.  In the *Register Service* dialog box, select a destination and look for the service name.

4.  Select the service and choose *Register*.Open the *Service Name* URL to view details of the registered service.

5.  Choose the service, and in the Service Details page, you can do the following:

    -   Add additional destinations by choosing *Add* and then choosing a new destination. This destination is then displayed in the*Destinations* table.

        Delete a destination as long as it isn't set as the default.

    -   Turn the status of the service *ON* or *OFF*. The service can only be deleted if it's status is *OFF*.
    -   Turn the *Error Tolerance for Multi-origin* for the service *ON* or *OFF*. For more information about error tolerance, see [Multiple-Origin Composition](multiple-origin-composition-d16fd96.md).

6.  Choose *Open Service Document* to view the service metadata.


**Related Information**  


[Create a Destination](https://help.sap.com/docs/btp/sap-business-technology-platform/create-destination)

[Multiple-Origin Composition](multiple-origin-composition-d16fd96.md "Multiple-Origin Composition (MOC) is the ability to collect data from different back-end systems, aggregate them in a single service, and update different back-end systems, while using the same user. You can also execute a $batch request with MOC.")

[Monitor Errors from OData Provisioning](monitor-errors-from-odata-provisioning-e0aeecf.md "Analyze the root cause for errors and where they originated.")

[Manage Metadata Validation and Cache Settings for OData Services](manage-metadata-validation-and-cache-settings-for-odata-services-dd4df7a.md "Enable or disable metadata validation for a registered OData service. You can also allow caching of metadata, which significantly improves performance of the OData service calls. Additionally, you can view the list of services which has cached metadata. You can clear the metadata cache of the selected service or all the services.")

