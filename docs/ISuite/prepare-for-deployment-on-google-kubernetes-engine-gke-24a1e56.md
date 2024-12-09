<!-- loio24a1e564506d4365a8ab64be2835628d -->

# Prepare for Deployment on Google Kubernetes Engine \(GKE\)

Before deploying your cluster on Google Kubernetes Engine \(GKE\), perform the following tasks.


<table>
<tr>
<th valign="top">

Task

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Create a Google Cloud Platform \(GCP\) account \(mandatory\).

</td>
<td valign="top">

[Get started with Google Cloud](https://cloud.google.com/docs/get-started)

</td>
</tr>
<tr>
<td valign="top">

Create a Kubernetes cluster on GCP \(mandatory\).

</td>
<td valign="top">

[Create a GKE cluster](https://cloud.google.com/kubernetes-engine/docs/quickstarts/create-cluster)

</td>
</tr>
<tr>
<td valign="top">

Create a Google Artifact Registry \(GAR\) \(recommended but not mandatory\).

Ensure a Docker repository is available in GAR. Ensure that the service account of your instance has the appropriate access rights to the repository in GAR within your GCP account.

</td>
<td valign="top">

[Google Artifact Registry](https://cloud.google.com/artifact-registry/docs)

</td>
</tr>
<tr>
<td valign="top">

Enable the Filestore Container Storage Interface \(CSI\) driver to support dynamic provisioning of NFS storage \(recommended but not mandatory\).

</td>
<td valign="top">

[Filestore CSI driver](https://cloud.google.com/kubernetes-engine/docs/how-to/persistent-volumes/filestore-csi-driver)

</td>
</tr>
<tr>
<td valign="top">

Install Google Cloud Command Line Interface \(CLI\).

</td>
<td valign="top">

[GCP Command Line Interface](https://cloud.google.com/sdk/docs/install)

</td>
</tr>
<tr>
<td valign="top">

Install the Kubernetes command-line tool kubectl.

</td>
<td valign="top">

[Install Kubectl](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-access-for-kubectl)

</td>
</tr>
</table>

> ### Note:  
> The Edge Integration Cell solution currently cannot be deployed on a GKE cluster with Workload Identity enabled. Verify that Workload Identity is disabled before adding your cluster to Edge Lifecycle Management.

