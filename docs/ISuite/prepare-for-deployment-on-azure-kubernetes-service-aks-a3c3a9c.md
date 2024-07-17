<!-- loioa3c3a9c49ded4a2098514987b0f57254 -->

# Prepare for Deployment on Azure Kubernetes Service \(AKS\)

Before deploying your cluster on Azure Kubernetes Service \(AKS\), perform the following tasks.

****


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

Create a Microsoft Azure account.

</td>
<td valign="top">

[How to create a new Microsoft account](https://support.microsoft.com/en-us/account-billing/how-to-create-a-new-microsoft-account-a84675c3-3e9e-17cf-2911-3d56b15c0aaf)

</td>
</tr>
<tr>
<td valign="top">

Subscribe to Microsoft Azure.

> ### Note:  
> You can find the subscription ID in the Azure portal at [https://portal.azure.com](https://portal.azure.com): *All Services* \> *Subscriptions*.



</td>
<td valign="top">

[Sign Up for a Microsoft Azure Subscription](https://learn.microsoft.com/en-us/dynamics-nav/how-to--sign-up-for-a-microsoft-azure-subscription)

</td>
</tr>
<tr>
<td valign="top">

Sign up for Azure Kubernetes Service \(AKS\).

</td>
<td valign="top">

[AKS](https://docs.microsoft.com/en-us/azure/aks)

</td>
</tr>
<tr>
<td valign="top">

Create an Azure Container Registry \(ACR\) \(recommended but not mandatory\).

Create a service principal to provide scoped access to your private container registry.

The service principal ID and client secret can be used as logon credentials. The Kubernetes cluster must have the reader role assigned so that it has pull permissions on the container registry.

</td>
<td valign="top">

[Create an Azure container registry using the Azure portal](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-get-started-portal)

[Azure Container Registry authentication with service principals](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-auth-service-principal)

[Authenticate with ACR from AKS](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-auth-aks)

</td>
</tr>
<tr>
<td valign="top">

Install the Azure Command-Line Interface \(CLI\).

</td>
<td valign="top">

[How to install the Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli)

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

