<!-- loio0359e5c3c13140d7b6229bffe8dea60d -->

# Prepare for Deployment on SUSE Rancher Kubernetes Engine \(RKE or RKE2\)

Before deploying your cluster on SUSE Rancher Kubernetes Engine \(RKE or RKE2\), perform the following tasks.

Rancher Kubernetes Engine doesn't have a predefined storage provisioner. For information about supported storage, see [3247839](https://me.sap.com/notes/3247839).

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

RKE: [https://rke.docs.rancher.com/](https://rke.docs.rancher.com/) 

or

RKE2: [https://docs.rke2.io/](https://docs.rke2.io/) 



</td>
</tr>
<tr>
<td valign="top">

Set up a private container registry for replicating container images \(recommended but not mandatory\).



</td>
<td valign="top">

Example Harbor: [https://goharbor.io/](https://goharbor.io/) \(recommended\)

Harbor is a widely used open source registry. It's one example for a container registry that can be used together with Edge Lifecycle Management.



</td>
</tr>
<tr>
<td valign="top">

Create at least one storage class and a dynamic provisioner for it in your cluster.

Storage classes should support dynamic provisioning for access modes `ReadWriteOnce` and`ReadWriteMany`.



</td>
<td valign="top">

Example Longhorn: [https://longhorn.io/docs/](https://longhorn.io/docs/).

Longhorn is a cloud native distributed block storage that can be used as storage backend. For other options, refer to Rancher documentation.



</td>
</tr>
<tr>
<td valign="top">

Install the Kubernetes command-line tool `kubect l` 



</td>
<td valign="top">

[https://kubernetes.io/docs/tasks/tools/\#kubectl](https://kubernetes.io/docs/tasks/tools/#kubectl) 



</td>
</tr>
</table>

