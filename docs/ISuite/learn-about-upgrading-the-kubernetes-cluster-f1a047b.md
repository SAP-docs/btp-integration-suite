<!-- loiof1a047b462fb4b17a7e1e0d67b091d4f -->

# Learn About Upgrading the Kubernetes Cluster

Learn about upgrading the Kubernetes cluster.



## Context

Use a Kubernetes version supported by both the old and the new versions of Edge Integration Cell.

For more information about supported versions, see SAP Note [3247839](https://me.sap.com/notes/3247839).

If the Kubernetes version isn't supported by the new Edge Integration Cell version, you have to upgrade Kubernetes. The Kubernetes upgrade process depends on your Kubernetes provider. See the respective documentation about how to upgrade.

While you can upgrade a running Kubernetes cluster, it puts additional load on your cluster \(similar to failing nodes\). Therefore, we recommend scheduling a Kubernetes upgrade during a low load time period.

