<!-- loiobb564867c7dd45b495e21c0a4c1d1a39 -->

# High Availability

High Availability \(HA\) is a key requirement for production environments. In a nutshell, HA aims to minimize downtime of a system or service.

Kubernetes as a platform offers a number of resiliency features, like restarting failed containers, removing containers that don't respond to defined health checks, already improving availability to a certain level. Additionally, it can take care of scaling and failover of applications, or handle node failures gracefully.





### Edge Integration Cell Kubernetes Cluster Topology

Basic Kubernetes cluster setup for HA:

-   Three control plane nodes handled implicitly on managed K8s platforms \(Azure AKS, Amazon EKS\)

-   Three worker nodes

You can enable HA mode for an Edge Node, during onboarding, see [Add an Edge Node](add-an-edge-node-d96772f.md).



### Multiple Availability Zones \(Multi-AZ\)

On cloud platforms, multiple availability zones are provided for Kubernetes deployments. For an HA setup with a minimum of three worker nodes, you require 3 availability zones if Multi-AZ is to be supported with Edge Integration Cell.



### Auto-Scaling

Scalability and reliability are key features of Kubernetes. Horizontal Pod Autoscaler \(HPA\) is a standard K8s feature provided by the core. For Edge Integration Cell, we'll gradually support auto-scaling for selected components.

> ### Note:  
> HPA is using the Metrics API which is provided by the Metrics Server. Make sure that a Metrics Server is deployed on your K8s cluster. For example, on Amazon EKS, a Metrics Server is not deployed by default.

