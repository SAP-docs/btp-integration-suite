<!-- loio21ae0fde134c450e89fb578a5d837745 -->

# Prepare for Deployment on Red Hat OpenShift \(OCP\)

OCP storage configuration depends on the underlying storage infrastructure. For information about supported storage, see [3247839](https://me.sap.com/notes/3247839), and for storage infrastructure, see [OpenShift Container Platform storage overview](https://docs.openshift.com/container-platform/4.14/storage/index.html).

> ### Note:  
> For information about how to prepare your infrastructure for the installation of Edge Integration Cell on OpenShift, see [Installation Guidance: SAP Edge Integration Cell on OpenShift](https://access.redhat.com/articles/7085063).


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

Create a Kubernetes cluster \(mandatory\).

</td>
<td valign="top">

[Install OCP](https://access.redhat.com/documentation/en-us/openshift_container_platform/4.14/html/installing/index)

</td>
</tr>
<tr>
<td valign="top">

Set up a private container registry for replicating container images \(recommended but not mandatory\).

</td>
<td valign="top">

Example: [Quay](https://access.redhat.com/documentation/en-us/red_hat_quay/3.11) \(recommended\)

Quay is included as part of OCP. It's an example of a container registry that you can use with Edge Lifecycle Management.

</td>
</tr>
<tr>
<td valign="top">

Create at least one storage class and a dynamic provisioner for it in your cluster.

Storage classes should support dynamic provisioning for access modes `ReadWriteOnce` and `ReadWriteMany`.

</td>
<td valign="top">

[OCP Storage](https://access.redhat.com/documentation/en-us/openshift_container_platform/4.14/html/storage/index)

</td>
</tr>
<tr>
<td valign="top">

Install the Kubernetes command-line tool `kubectl`.

</td>
<td valign="top">

[Install Kubectl](https://kubernetes.io/docs/tasks/tools/#kubectl)

</td>
</tr>
<tr>
<td valign="top">

Install the OpenShift command-line tool `oc` \(recommended\).

</td>
<td valign="top">

[OpenShift CLI](https://docs.openshift.com/container-platform/4.15/cli_reference/openshift_cli/getting-started-cli.html)

</td>
</tr>
</table>

