<!-- loiof4bf46bd9dbe4d08b7ee3c66b55b15a3 -->

# Setting Up Content Transport

For the transport of integration content across different tenants, different options are available:

-   Manual export and import

-   Usage of CTS+

-   Usage of the cloud-based Transport Management


These options are identical independent of the environment \(Cloud Foundry or Neo\). However, setting up transport management using the cloud-based Transport Management service is different in both environments. Here's a brief summary of the differences.

-   In the Cloud Foundry environment: In order to set up content transport with Transport Management Service, you need to activate the Content Agent service. Furthermore, you need to define various destinations between source and target tenant of the content transport and Content Agent. For more information, see:

    [Enabling Content Transport, Cloud Foundry Environment](../Development/enabling-content-transport-cloud-foundry-environment-452c677.md)

    [Introducing SAP Content Agent service: Enhanced Transport Capabilities for SAP Cloud Integration Content](https://blogs.sap.com/2020/08/30/introducing-sap-cloud-platform-content-agent-enhanced-transport-capabilities-for-sap-cloud-platform-integration-suite-content/)

-   In the Neo environment: In order to set up content transport with Transport Management Service, you need to activate Lifecycle Management service. Furthermore, you need to define various destinations between source and target tenant of the content transport and Lifecycle Management. For more information, see:

    [Enabling Content Transport, Neo Environment](../Development/enabling-content-transport-neo-environment-425db2b.md)

    [Cloud Integration – Using Transport Management Service for a Simple Transport Landscape](https://blogs.sap.com/2018/05/24/cloud-integration-using-transport-management-service-beta-for-a-simple-transport-landscape/)


