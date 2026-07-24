<!-- loiob70e7ece2edb46cab447a6bec891fe7e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Deploy APIs and MCP Servers

After creating an API or an MCP server artifact, it is necessary to deploy it on the chosen runtime in order to make it executable and ready for use.



<a name="loiob70e7ece2edb46cab447a6bec891fe7e__prereq_x3l_jbg_q1c"/>

## Prerequisites

You should have at least one runtime provisioned.

> ### Note:  
> API artifact deployments are runtime-specific. After an API artifact is created on a specific runtime, you cannot change its runtime profile either by editing the artifact or during deployment. For example, an API artifact created for the Integration Cell runtime cannot later be deployed to the Edge Integration Cell runtime, and vice versa.
> 
> The only exception applies to API artifacts created with the Edge Integration Cell runtime profile, where you can select or change the target Edge Integration Cell node during editing or deployment.



<a name="loiob70e7ece2edb46cab447a6bec891fe7e__steps_sqd_4wk_q1c"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  Choose the navigation icon on the left and choose *Design* \> *Integrations and APIs*.

3.  Select the *<integration package\>* where you want to create your artifact.

4.  To expose a service as an API artifact or an MCP server, choose *Edit* and navigate to the *Artifacts* tab. For detailed steps on how to add an API artifact, see [Creating an API Artifact](creating-an-api-artifact-c2fe62c.md) and [How Model Context Protocol \(MCP\) Server Enables AI Integration](how-model-context-protocol-mcp-server-enables-ai-integration-572e7fd.md) .

    If you wish to deploy an artifact that has already been created, select the *<integration package\>* where you created the API or the MCP artifact.

5.  Choose the <span class="SAP-icons-V5"></span> Action icon next to the required artifact and then select the *Deploy* from the options.

    > ### Note:  
    > Alternatively, you can deploy an API artifact or an MCP server from its details page. First, select the *<integration package\>* in which you created the API artifact or the MCP server. Then, select the corresponding artifact to open its *Details* page. On the artifact details page, you will find the option to deploy the artifact. Simply select *Deploy* to proceed with the deployment.

    > ### Note:  
    > After an API artifact is created and deployed to either *Integration Cell* or *Edge Integration Cell*, you cannot change its runtime profile. However, for API artifacts deployed to *Edge Integration Cell*, you can change the assigned edge nodes. Cross-deployment between runtimes is not supported. To deploy the API artifact to a different runtime, create a new API artifact and deploy it to the desired runtime.

6.  On the *Confirmation* dialog, verify the selected runtime profile. The runtime profile chosen when the API artifact was created is selected by default.

    If the API artifact was created for *Edge Integration Cell*, you can select a different edge node from the *Runtime Profile* drop-down list.

    > ### Note:  
    > For Edge Integration Cell, when you select a different edge node, the associated virtual host is updated automatically. The runtime endpoint URL for the deployed artifact is generated using the virtual host associated with the selected edge node.

    If the artifact is deployed to *Integration Cell*, you can optionally select a virtual host from the *Virtual Host* drop-down list.

    If the artifact has been deployed previously, the virtual host used in the last deployment is preselected. If the artifact is being deployed for the first time, the virtual host selected during design time is preselected in the deployment dialog. You can change the selected virtual host before deploying the artifact.

    > ### Note:  
    > Multiple virtual hosts are not supported for artifacts deployed to **Edge Integration Cell**. The virtual host associated with the selected edge node is used automatically. For artifacts deployed to **Integration Cell**, you can select a different virtual host during deployment.
    > 
    > The virtual host configured in the API artifact at design time and the virtual host selected during deployment can be different. If you select a different virtual host during deployment, the runtime endpoint is generated using the deployed virtual host. Therefore, in *Monitor* \> *Manage Integration Content*, the URL for the API artifact displayed under *Endpoints* reflects the virtual host currently used by the deployed runtime artifact.
    > 
    > If the API artifact is configured with the virtual host `api-dev.company.com`at design time, but you select `api-prod.company.com` during deployment, the design-time configuration continues to show `api-dev.company.com`. However, after deployment, the endpoint URL displayed in *Monitor* \> *Manage Integration Content* uses `api-prod.company.com`, because it reflects the virtual host associated with the deployed runtime artifact.




<a name="loiob70e7ece2edb46cab447a6bec891fe7e__result_l2r_tvf_5pb"/>

## Results

Once an artifact is deployed, it becomes available for consumption.



<a name="loiob70e7ece2edb46cab447a6bec891fe7e__postreq_f3l_hpl_q1c"/>

## Next Steps

After deploying the artifact, you can check the runtime logs and the status of the artifact. For more information, see [Monitor APIs and MCP Servers](monitor-apis-and-mcp-servers-399b6c6.md).

> ### Note:  
> When an API or an MCP server artifact deployed to an Integration Cell runtime invokes an HTTPS backend endpoint, the backend certificate must be trusted by the runtime keystore. If the required certificate is not available in the keystore, API invocations will fail with an internal server error. You can see the detailed error message in Manage Processing Logs.
> 
> To add a trusted certificate to the runtime keystore, see [Uploading a Keystore](uploading-a-keystore-0db193a.md) and [Updating a Certificate](updating-a-certificate-1fa04fa.md).

**Related Information**  


[API Artifact](api-artifact-a4f87b1.md "API artifacts are the core building blocks used to design, configure, publish, and manage APIs in SAP Integration Suite, API Management. These artifacts define how APIs behave, how they interact with backend systems, and how they are exposed to consumers.")

[Model Context Protocol \(MCP\)](model-context-protocol-mcp-9eb9239.md "Model Context Protocol (MCP) is an open-source protocol designed to bridge the gap between AI applications or agents and enterprise tools and data. Just as REST APIs connect web applications to data and services, MCP enables AI-native integrations by exposing tools, APIs, and data sources to AI Agents.")

[Copy an API or an MCP Server Artifact](copy-an-api-or-an-mcp-server-artifact-820c9e8.md "Create a copy of an existing API artifact or an MCP server with all its configurations and policies intact. This can be useful when you want to create a similar artifact but with some modifications or variations.")

[Delete APIs and MCP Servers](delete-apis-and-mcp-servers-81694d6.md "Use this procedure to delete an API or an MCP Server artifact from an integration package in the Design workspace.")

