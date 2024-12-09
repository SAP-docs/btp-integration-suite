<!-- loio217fed141b6f43a2ace418fc12fa4e6a -->

# Plan Your Setup of Edge Integration Cell

Things to consider before you start setting up Edge Integration Cell.



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_fpm_rt1_mvb"/>

## On Which Data Center or Cloud Environment must Edge Integration Cell Be Installed?

When selecting a deployment target, plan the Kubernetes \(K8s\) deployments in their respective environments. For information about supported versions, see SAP Note [3247839](https://me.sap.com/notes/3247839). As an optional runtime, consider colocation with the data center where your SAP Integration Suite tenant is located.



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_dp1_st1_mvb"/>

## Which Storage Setups are Required for Running Edge Integration Cell?

Edge Integration Cell requires different kinds of persistent storage:

-   Automatic provisioning of persistent volumes \(RWO, RWX\) in the K8s cluster.

-   A container registry for local image replication \(optional\). As a best practice, you can use a local container registry to decouple from SAP’s Repository-Based Shipment Channel \(RBSC\), which is SAP’s Container Registry.




<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_pgp_wkz_xyb"/>

## Which External services are required?

For a production environment, you need to provide a PostgreSQL database and a Redis data store outside the Edge Integration Cell deployment.

For test and demo purposes, you can deploy an internal PostgreSQL database and a Redis data store as part of Edge Integration Cell, but these built-in services aren't highly available, nor scalable as required for a production environment.

You require a load balancer integrated with your Kubernetes infrastructure to expose Edge Integration Cell endpoints and load balance traffic across K8s nodes and services. On cloud platforms, you can choose between using an external load balancer exposed to Internet or an internal load balancer for private networks. For more information, see

[https://learn.microsoft.com/en-us/azure/aks/internal-lb%20\(Azure\)](https://learn.microsoft.com/en-us/azure/aks/internal-lb%20(Azure)) or

[https://docs.aws.amazon.com/eks/latest/userguide/network-load-balancing.html%20\(AWS\)](https://docs.aws.amazon.com/eks/latest/userguide/network-load-balancing.html%20(AWS)).

To use client IP filtering policies, you require a Network Load Balancer that preserves the client IP address. For more information, see [https://istio.io/latest/docs/tasks/security/authorization/authz-ingress/\#network](https://istio.io/latest/docs/tasks/security/authorization/authz-ingress/#network).



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_ny1_st1_mvb"/>

## Which network connectivity and network protocols must be established?

We recommend planning the network layout for an Edge Integration Cell setup in combination with the systems that you want to connect. Make sure that network communication is possible for the required protocols \(such as firewall rules, network routes, etc.\). We recommend that you use properly encrypted communication for all channels, in particular, leveraging Transport Layer Security \(TLS\).



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_hf4_z4z_xyb"/>

## Can I use a private cluster?

On cloud platforms, you can use a private Kubernetes cluster. A private cluster in Azure means that the control plane or API server have internal IP addresses. By using a private cluster, you can ensure that network traffic between API server, and node pools remains on the private network only.

On AWS, you can configure cluster endpoint access to enable private access to the Kubernetes API server so that all communication between nodes and the API server stays within a VPC. Additionally, you can control if the API server endpoint is public to the internet.



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_ofb_st1_mvb"/>

## Can the Kubernetes cluster be shared with other applications?

Each Edge Integration Cell solution must be deployed on a K8s cluster. For future productive setups, we strongly recommend using this K8s cluster exclusively for this purpose. Don't coinstall any other applications with higher resource requirements on this cluster. Do joint deployment only be done if mechanisms are used to ensure that the Edge Integration Cell is carefully isolated from other applications in terms of resources \(for example, by using dedicated node pools for each application\). A shared usage can be problematic, as Edge Lifecycle Management requires high-privileged Kubernetes access for deploying custom resource definitions and shared resources like Istio. You can deploy the required PostgreSQL database and Redis data store into the same Kubernetes cluster \(as explained in the external services section\).

It's possible to deploy the required PostgreSQL database and Redis data store into the same Kubernetes cluster \(see external services before\).



<a name="loio217fed141b6f43a2ace418fc12fa4e6a__section_fgc_st1_mvb"/>

## Can one Kubernetes cluster host multiple Edge Integration Cell deployments ?

The Edge Integration Cell deployment uses a fixed K8s namespace \(`edge-icell`\). Therefore, multiple deployments in the same cluster aren't possible.

