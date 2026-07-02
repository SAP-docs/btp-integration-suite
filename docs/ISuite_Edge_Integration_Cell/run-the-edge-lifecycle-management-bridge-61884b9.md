<!-- loio61884b932c2643a4b29bd25e24c3f0c5 -->

# Run the Edge Lifecycle Management Bridge





<a name="loio61884b932c2643a4b29bd25e24c3f0c5__prereq_nbs_lth_vlb"/>

## Prerequisites

-   Download the Edge Lifecycle Management Bridge executable from the [SAP Software Download Center](https://support.sap.com/en/my-support/software-downloads.html).

-   Ensure that you have access to the target Kubernetes cluster.

-   Ensure that your local environment is configured to communicate with the cluster \(for example, via a valid kubeconfig context\).

-   If required for your environment, ensure access to the container registry used for the deployment. If you deploy on AWS infrastructure, configure your AWS credentials using: `aws configure`




## Context

Run the Edge Lifecycle Management Bridge to establish the connection between the Edge Lifecycle Management and the Edge Node.

The bridge executes the onboarding of the Kubernetes-based Edge Node and deploys the required resources into the namespace `edgelm`.

The bridge can be used in the following connectivity scenarios:

-   With the embedded Cloud Connector, which is automatically started and managed by Edge Lifecycle Management.
-   With an external Cloud Connector, which is operated outside Edge Lifecycle Management.

For an overview of these connection models, see [Key Concepts](https://help.sap.com/docs/edge-lifecycle-management/documentation/key-concepts?q=cloud+connector).



## Procedure

1.  Decide which Cloud Connector setup you are using: *embedded* or *external*.

2.  Follow the corresponding procedure:

    -   If you use an embedded Cloud Connector, see [Running the Edge Lifecycle Management Bridge to Initiate the Cloud Connector](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/65c60063aaa448bcbf9a9ee148205120.html?q=aws).
    -   If you use an external Cloud Connector, see[Initializing an Edge Node with an External Cloud Connector](https://help.sap.com/docs/edge-lifecycle-management/documentation/initializing-edge-node-with-external-cloud-connector?q=aws) and complete the additional configuration described in [Configure an External Cloud Connector for Edge Integration Cell](configure-an-external-cloud-connector-for-edge-integration-cell-dbc29bb.md).




<a name="loio61884b932c2643a4b29bd25e24c3f0c5__result_oys_hz4_fvb"/>

## Results

After the Edge Lifecycle Management Bridge has run successfully:

-   The Edge Node is registered in Edge Lifecycle Management.

-   The Edge Node appears in the Edge Lifecycle Management user interface.

-   The status of the Edge Node changes to *Available* after the required resources are deployed.

-   Kubernetes resources required for operation are created automatically in the namespace edgelm.


