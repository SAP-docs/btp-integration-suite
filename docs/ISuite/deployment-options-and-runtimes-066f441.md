<!-- loio066f441d1da64173baaeafd7c25df174 -->

# Deployment Options and Runtimes

SAP Integration Suite supports different deployment options to meet your organizational, security, and latency requirements.

Depending on your choice, different runtime environments execute your integration scenarios:

-   **Integration Cell**

    Integration Cell is SAP's fully managed runtime foundation for SAP Integration Suite. It's designed to simplify operations through centralized governance, security, and monitoring. The cloud-native architecture ensures scalability, resilience, and a consistent tenant experience. This allows organizations to focus on their integration requirements rather than infrastructure management. To learn more about its setup and supported features, see [Integration Cell](https://help.sap.com/viewer/42631d23a21b4178b35c41f971cdd2c9/CLOUD/en-US/43dc6ef13058453a8d76e50b6201714e.html "Integration Cell extends the runtime capabilities of SAP Integration Suite by offering a fully managed, scalable, and Kubernetes-based environment. It is the next-generation runtime foundation designed to support the continued evolution of integration capabilities on a cloud-native architecture.") :arrow_upper_right:.

-   **Cloud Deployment**

    Runs entirely in the cloud. It uses the Cloud Integration Runtime, which is fully managed by SAP on SAP BTP. To learn more about how integration content is designed, deployed, and processed in the cloud, see [Standard Deployment in the Cloud](standard-deployment-in-the-cloud-ca5b233.md).

-   **Hybrid Deployment**

    Powered by the Edge Integration Cell in your own Kubernetes cluster, this deployment model allows you to run integration scenarios within your private landscape. This hybrid approach enables you to design and monitor your integration content in the cloud, while deploying and running it directly in your local environment. To learn more about hybrid deployment using Edge Integration Cell, how to set it up, security, and troubleshooting guidance, see [What is Edge Integration Cell](https://help.sap.com/docs/integration-suite/edge-integration-cell-test/what-is-edge-integration-cell?version=CLOUD).


