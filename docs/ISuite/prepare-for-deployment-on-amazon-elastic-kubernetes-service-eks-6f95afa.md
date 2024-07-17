<!-- loio6f95afa8e2784aabad5d5611936125f7 -->

# Prepare for Deployment on Amazon Elastic Kubernetes Service \(EKS\)

Before deploying your cluster on Amazon Elastic Kubernetes Service \(EKS\), perform the following tasks.


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

Create an AWS account \(mandatory\).

</td>
<td valign="top">

[Create a standalone AWS account](https://docs.aws.amazon.com/accounts/latest/reference/manage-acct-creating.html)

</td>
</tr>
<tr>
<td valign="top">

Create a Kubernetes cluster on Amazon Elastic Kubernetes Service \(mandatory\).

</td>
<td valign="top">

[Getting started with Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/getting-started.html)

</td>
</tr>
<tr>
<td valign="top">

Sign up for the Amazon Elastic Container Registry \(Amazon ECR\) service \(recommended but not mandatory\). Make sure that the Identity and Access Management \(IAM\) roles used in cluster creation have access rights to the registry.

</td>
<td valign="top">

[IAM for Amazon EKS](https://docs.aws.amazon.com/eks/latest/userguide/IAM_policies.html)

</td>
</tr>
<tr>
<td valign="top">

Create at least one storage class and a dynamic provisioner for it in your cluster.

</td>
<td valign="top">

[Storage classes](https://docs.aws.amazon.com/eks/latest/userguide/storage.html)

</td>
</tr>
<tr>
<td valign="top">

Install Amazon Elastic File System \(EFS\) Container Storage Interface \(CSI\) driver to support dynamic provisioning of Amazon EFS file systems. Create a storage class and a dynamic provisioner for it.

</td>
<td valign="top">

[Amazon EFS CSI driver](https://docs.aws.amazon.com/eks/latest/userguide/efs-csi.html)

</td>
</tr>
<tr>
<td valign="top">

Install AWS Command Line Interface \(CLI\).

</td>
<td valign="top">

[AWS Command Line Interface](https://aws.amazon.com/cli)

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
</table>

