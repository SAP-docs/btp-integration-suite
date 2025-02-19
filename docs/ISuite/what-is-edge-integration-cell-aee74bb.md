<!-- loioaee74bb3ccd943a0837087d705e1ebc9 -->

# What Is Edge Integration Cell

Edge Integration Cell is an optional hybrid integration runtime offered as part of SAP Integration Suite, which enables you to manage APIs and run integration scenarios within your private landscape.



The hybrid deployment model of Edge Integration Cell enables you to:

-   Design and monitor your integration content in the cloud.

-   Deploy and run your integration content in your private landscape.


To learn more about how hybrid deployment works using Edge Integration Cell, see [Hybrid Deployment Using Edge Integration Cell](hybrid-deployment-using-edge-integration-cell-7a6c267.md).

To compare hybrid deployment with the standard deployment model of SAP Integration Suite, see [Standard Deployment in the Cloud](standard-deployment-in-the-cloud-ca5b233.md).



Edge Integration Cell supports the following use cases:

-   Security or compliance use cases

    In many enterprises, sensitive data must be managed and controlled inside the enterprise's firewall. In addition, there could be strict architectural restrictions and you want to keep your data within your private landscape.

-   Getting a migration path for SAP Process Integration customers

    SAP Process Integration is used by many customers for ground-to-ground integration scenarios. Edge Integration Cell allows these customers to benefit from the newest innovations that come with SAP Integration Suite, with the option to design and monitor integration content in the cloud, and deploy and run their scenarios exclusively in their private landscapes.

    > ### Note:  
    > If you want to use integration flows to integrate your on-premise applications, you can use SAP Process Orchestration in addition to SAP Integration Suite. SAP Integration Suite comes with a set of runtime profiles that make sure that the integration flow editor allows you to design only those features that are supported by the runtime components of a specific SAP Process Orchestration release.
    > 
    > For more information, see [Runtime Profiles](50-Development/IntegrationSettings/runtime-profiles-8007daa.md).
    > 
    > However, this option requires you to install a separate product, SAP Process Orchestration, for processing and monitoring messages.
    > 
    > Using Edge Integration Cell, you can manage all tasks – from integration design up to processing and monitoring the scenario – within one service: SAP Integration Suite.


In both cases, we recommend using a hybrid integration approach for enterprise-wide connectivity.

For more information about the supported features and limitations of Edge Integration Cell, see [Edge Integration Cell Runtime Scope](edge-integration-cell-runtime-scope-144c64a.md).

**Related Information**  


[Standard Deployment in the Cloud](standard-deployment-in-the-cloud-ca5b233.md "")

[Hybrid Deployment Using Edge Integration Cell](hybrid-deployment-using-edge-integration-cell-7a6c267.md "The Edge Integration Cell enables the processing of data within a private landscape. This allows sender and receiver systems to exchange data without passing through the internet, as the data is hosted exclusively in an on-premise environment. The cloud-based environment of SAP Integration Suitee is utilized to design integration content. This content is then deployed within the organization's firewall at a private runtime location. The runtime environment is realized as a Kubernetes container, facilitating secure, internal data exchange")

[Technical Landscape \(Edge Integration Cell\)](technical-landscape-edge-integration-cell-f60efc1.md "Get to know the system landscape and the components of Edge Integration Cell.")

[Edge Integration Cell Runtime Scope](edge-integration-cell-runtime-scope-144c64a.md)

