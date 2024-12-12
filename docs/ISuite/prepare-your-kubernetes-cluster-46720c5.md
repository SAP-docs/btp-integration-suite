<!-- loio46720c5f00494102b4d1b036045dc20a -->

# Prepare Your Kubernetes Cluster

Get to know the requirements for installing Edge Integration Cell on a Kubernetes cluster.

To successfully set up the Edge Integration Cell, your cluster setup must fulfill certain requirements.

The following infrastructures are required for installing Edge Integration Cell:

-   \(Mandatory\) A Kubernetes cluster

-   \(Mandatory\) A PostgreSQL database

-   \(Mandatory\) A Redis data store

-   \(Mandatory\) A Load Balancer

-   \(Optional\) A container registry to mirror the Edge Integration Cell container images.

-   \(Optional\) An Identity and Authentication Service \(IAS\) tenant for single sign-on.




<a name="loio46720c5f00494102b4d1b036045dc20a__section_k5d_t51_mvb"/>

## Kubernetes Cluster Requirements

Your Kubernetes cluster must meet certain requirements before you can set up Edge Integration Cell.

> ### Note:  
> For information about Kubernetes versions, see SAP Note [3247839](https://me.sap.com/notes/3247839).
> 
> You can install Edge Integration Cell on Kubernetes clusters on cloud platforms such as Amazon Web Services \(Amazon Elastic Kubernetes Service, Amazon EKS\), Microsoft Azure \(Azure Kubernetes Service, AKS\), SUSE Rancher \(Rancher Kubernetes Engine, RKE2\) and Red Hat OpenShift \(OpenShift Kubernetes Engine, OKE\).

-   The Kubernetes cluster must have role-based access control \(RBAC\) enabled.

-   The Kubernetes cluster must have at least one worker node. The worker nodes must have the same version as the Kubernetes API server.

-   The Kubernetes cluster must be able to dynamically provision persistent volumes for access modes `ReadWriteOnce`,`ReadWriteMany`. There must be at least one storage class - the default storage class. You can configure additional storage classes during initial deployment. Storage class for access mode `ReadWriteMany` requires volume binding mode`Immediate`. Storage classes should allow volume expansion in general.

-   The container registry must be accessible \(with read, write permissions\) from the Kubernetes cluster, when used for image replication \(optional\). The Kubernetes cluster must trust the registry. That means that Image Replication Service needs access to the trust chain of the registry. Client authentication is required.

-   A `high-privileged` kubeconfig is required to initialize the edge node, as cluster admin privileges are required to execute CRUD operations on namespaces and CRDs.


> ### Note:  
> Using a policy controller like Azure Policy, Gatekeeper or Open Policy Agent \(OPA\) is currently not supported.



<a name="loio46720c5f00494102b4d1b036045dc20a__section_gm2_l11_yyb"/>

## PostgreSQL Database Requirements

Your PostgreSQL database must meet certain requirements before you can set up Edge Integration Cell:

-   PostgreSQL server must have TLS/SSL enabled.

-   Server certificate must use a Subject Alternative Name \(SAN\) extension \(type DNS Name\) to be used as server identity.

-   Using client certificates is currently not supported.

-   Server must provide a single endpoint \(host and port pair\).

    -   Using a connection proxy for failover such as `pgBouncer`, `HAProxy`, `Pgpool-II`.

        > ### Note:  
        > If you use `pgBouncer` as a connection proxy for PostgreSQL, the following parameters must be set:
        > 
        > -   pgbouncer.pool\_mode = transaction
        > 
        > -   pgbouncer.max\_prepared\_statements \> 0
        > 
        > -   pgbouncer.ignore\_startup\_parameters = extra\_float\_digits


    -   Alternatively, in case PostgreSQL HA is deployed in K8s, the PostgreSQL K8s service should always point to the PostgreSQL read-write pod.


The requirements are fulfilled when using cloud platform offerings like Azure Database for PostgreSQL, or Amazon RDS for PostgreSQL.

> ### Note:  
> For more information about PostgreSQL, see [3247839](https://me.sap.com/notes/3247839).



<a name="loio46720c5f00494102b4d1b036045dc20a__section_rgm_1n1_yyb"/>

## Redis Data Store Requirements

Your Redis data store must meet certain requirements before you can set up Edge Integration Cell:

-   Redis server must have TLS/SSL enabled.

-   Server certificate must use a Subject Alternative Name \(SAN\) extension \(type DNS Name\) to be used as server identity.

-   Using client certificates is currently not supported.

> ### Note:  
> For more information about Redis, see [3247839](https://me.sap.com/notes/3247839).

