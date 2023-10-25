<!-- loio61884b932c2643a4b29bd25e24c3f0c5 -->

# Run the Edge Lifecycle Management Bridge





<a name="loio61884b932c2643a4b29bd25e24c3f0c5__prereq_nbs_lth_vlb"/>

## Prerequisites

-   Download the Edge Lifecycle Management Bridge executable from [https://support.sap.com/en/my-support/software-downloads.html](https://support.sap.com/en/my-support/software-downloads.html) .

-   You' ve access to the Kubernetes cluster and to the container registry \(optional\).

    In order to enable access to AWS services, execute the `aws configure` command from the command line.




## Context

Run the Edge Lifecycle Management Bridge to establish the connection between the Edge Lifecycle Management and the Edge Node using the Cloud Connector.

Edge Lifecycle Management Bridge deploys Kubernetes resources under namespace `edgelm`.



## Procedure

Follow the Edge Lifecycle Management procedure [Running the Edge Lifecycle Management Bridge to Initiate the Cloud Connector](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/65c60063aaa448bcbf9a9ee148205120.html?q=aws).



<a name="loio61884b932c2643a4b29bd25e24c3f0c5__result_oys_hz4_fvb"/>

## Results

After running the Edge Lifecycle Management Bridge successfully, you have accomplished the following:

-   You see the new Edge Node displayed in Edge Lifecycle Management UI.

-   Additional Kubernetes resources are deployed automatically before the status of the Edge Node shows *Available*.


