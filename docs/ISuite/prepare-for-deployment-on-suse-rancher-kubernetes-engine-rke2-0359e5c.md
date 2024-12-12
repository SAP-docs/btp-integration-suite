<!-- loio0359e5c3c13140d7b6229bffe8dea60d -->

# Prepare for Deployment on SUSE Rancher Kubernetes Engine \(RKE2\)

Before deploying your cluster on SUSE Rancher Kubernetes Engine \(RKE2\), perform the following tasks.

Rancher Kubernetes Engine doesn't have a predefined storage provisioner. For information about supported storage, see [3247839](https://me.sap.com/notes/3247839).

> ### Note:  
> For information about how to prepare your infrastructure for the installation of Edge Integration Cell on Rancher Kubernetes Engine 2 using Rancher Prime, see [SAP Edge Integration Cell on SUSE](https://documentation.suse.com/sbp/sap-other/html/SAP-EIC/index.html).

****


<table>
<tr>
<th valign="top">

Tasks

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Create a Kubernetes cluster \(mandatory\)

</td>
<td valign="top">

[RKE2](https://docs.rke2.io/) 

</td>
</tr>
<tr>
<td valign="top">

Set up a private container registry for replicating container images \(recommended but not mandatory\).

</td>
<td valign="top">

Example: [Harbor](https://goharbor.io/) \(recommended\)

Harbor is a widely used open source registry. It's an example of a container registry that you can use together with Edge Lifecycle Management.

</td>
</tr>
<tr>
<td valign="top">

Create at least one storage class and a dynamic provisioner for it in your cluster.

Storage classes should support dynamic provisioning for access modes `ReadWriteOnce` and`ReadWriteMany`.

</td>
<td valign="top">

Example: [Longhorn](https://longhorn.io/docs/)

Longhorn is a cloud native distributed block storage that you can use as storage backend. For other options, refer to the [Rancher](https://ranchermanager.docs.rancher.com/) documentation.

</td>
</tr>
<tr>
<td valign="top">

Install the Kubernetes command-line tool `kubectl` 

</td>
<td valign="top">

[Install Kubectl](https://kubernetes.io/docs/tasks/tools/#kubectl) 

</td>
</tr>
</table>

