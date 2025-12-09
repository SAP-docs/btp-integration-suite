<!-- loio217fed141b6f43a2ace418fc12fa4e6a -->

# Plan Your Setup of Edge Integration Cell

Things to consider before you start setting up Edge Integration Cell.



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_fpm_rt1_mvb"/>

## On which data center or cloud environment must Edge Integration Cell be installed?

When selecting a deployment target, plan the Kubernetes \(K8s\) deployments in their respective environments. For information about supported versions, see SAP Note [3247839](https://me.sap.com/notes/3247839). As an optional runtime, consider colocation with the data center where your SAP Integration Suite tenant is located.



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_dp1_st1_mvb"/>

## Which storage setups are required for running Edge Integration Cell?

Edge Integration Cell requires different kinds of persistent storage:

-   Automatic provisioning of persistent volumes \(RWO mandatory, RWX optional\) in the K8s cluster.

-   A container registry for local image replication \(optional\). As a best practice, you can use a local container registry to decouple from SAP’s Repository-Based Shipment Channel \(RBSC\), which is SAP’s Container Registry.




<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_pgp_wkz_xyb"/>

## Which external services are required?

For a production environment, you need to provide a database \(PostgreSQL or SAP HANA database\) and a datastore \(Redis or SAP HANA datastore\) that are deployed separately from the Edge Integration Cell.

When using SAP HANA database, both the database and datastore can share the same SAP HANA database instance.

> ### Note:  
> The SAP HANA database license is not included with the Edge Integration Cell.

For test and demo purposes, you can deploy an internal PostgreSQL database and a Redis data store as part of Edge Integration Cell, but these built-in services aren't highly available, nor scalable as required for a production environment.

You require a load balancer integrated with your Kubernetes infrastructure to expose Edge Integration Cell endpoints and load balance traffic across K8s nodes and services. On cloud platforms, you can choose between using an external load balancer exposed to Internet or an internal load balancer for private networks. For more information, see

[Use an internal load balancer with Azure Kubernetes Service \(AKS\)](https://learn.microsoft.com/en-us/azure/aks/internal-lb?tabs=set-service-annotations) or

[Route TCP and UDP traffic with Network Load Balancers](https://docs.aws.amazon.com/eks/latest/userguide/network-load-balancing.html).

To use client IP filtering policies, you require a Network Load Balancer that preserves the client IP address. For more information, see [Network Load Balancer](https://istio.io/latest/docs/tasks/security/authorization/authz-ingress/#network).



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_ny1_st1_mvb"/>

## Which network connectivity and network protocols must be established?

We recommend planning the network layout for an Edge Integration Cell setup in combination with the systems that you want to connect. Make sure that network communication is possible for the required protocols \(such as firewall rules, network routes, etc.\). We recommend that you use properly encrypted communication for all channels, in particular, leveraging Transport Layer Security \(TLS\).



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_hf4_z4z_xyb"/>

## Can I use a private cluster?

On cloud platforms, you can use a private Kubernetes cluster. A private cluster in Azure means that the control plane or API server have internal IP addresses. By using a private cluster, you can ensure that network traffic between API server, and node pools remains on the private network only.

On AWS, you can configure cluster endpoint access to enable private access to the Kubernetes API server so that all communication between nodes and the API server stays within a VPC. Additionally, you can control if the API server endpoint is public to the internet.



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_ofb_st1_mvb"/>

## Can the Kubernetes cluster be shared with other applications?

Each Edge Integration Cell is deployed on a K8s cluster. For standard onboarding of a K8s cluster as an Edge Node, Edge LM requires a high-privileged kubeconfig, because cluster admin privileges are required to perform CRUD operations on namespaces, CRDs, and admission webhooks. This must be taken into account when the cluster is shared with other applications. Workloads should be carefully isolated, for example by assigning dedicated nodes or node pools to each application. Different applications may have different Kubernetes version requirements, which needs to be considered during onboarding.

The alternative onboarding method, the Restricted Access to Kubernetes Cluster option, uses a security model that requires fewer privileges than the standard onboarding process. For more information, see SAP Note [3618713](https://me.sap.com/notes/3618713) and section [Provide Edge Node Details](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/0a222b9c99d94f56abdcfe27f5be0afa.html#1---provide-edge-node-details).

It's possible to deploy the required PostgreSQL database and Redis data store on the same Kubernetes cluster \(as explained in the External Services section\).



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_fgc_st1_mvb"/>

## Can one Kubernetes cluster host multiple Edge Integration Cell deployments ?

The Edge Integration Cell deployment uses a fixed K8s namespace \(`edge-icell`\). Therefore, multiple deployments in the same cluster aren't possible.

