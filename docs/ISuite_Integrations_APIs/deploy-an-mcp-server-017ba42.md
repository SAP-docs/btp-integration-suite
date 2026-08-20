<!-- loio017ba42fbcc04686ae368af1357a9df3 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Deploy an MCP Server

After you create an MCP server, deploy it to the runtime to make it available for execution.



<a name="loio017ba42fbcc04686ae368af1357a9df3__prereq_x3l_jbg_q1c"/>

## Prerequisites

You should have the Integration Cell runtime provisioned.



## Context

Deployment packages the server configuration, validates it, and publishes it to the configured Integration Cell runtime. Once the MCP server is deployed, AI agents can connect to the MCP server, discover the tools and resources it exposes, and invoke them based on the configured authentication and authorization policies.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



<a name="loio017ba42fbcc04686ae368af1357a9df3__steps_sqd_4wk_q1c"/>

## Procedure

1.  Log on to SAP Integration Suite.

2.  Choose the navigation icon on the left and choose *Design* \> *Integrations and APIs*.

3.  Select the *<integration package\>* where you want to create an MCP server.

4.  To expose a service as an MCP server, choose *Edit* and navigate to the *Artifacts* tab. For detailed steps on how to add an MCP server, see [How Model Context Protocol \(MCP\) Server Enables AI Integration](how-model-context-protocol-mcp-server-enables-ai-integration-572e7fd.md) .

    If you wish to deploy an artifact that has already been created, select the *<integration package\>* where you created the MCP artifact.

5.  Choose the <span class="SAP-icons-V5"></span> Action icon next to the required artifact and then select the *Deploy* from the options.

    > ### Note:  
    > Alternatively, you can deploy an MCP server from its details page. First, select the *<integration package\>* in which you created the MCP server. Then, select the corresponding artifact to open its *Details* page. On the artifact details page, you will find the option to deploy the artifact. Simply select *Deploy* to proceed with the deployment.

6.  On the *Confirmation* dialog, verify the selected runtime profile. The runtime profile chosen when the MCP server was created is selected by default.

    You can optionally select a virtual host from the *Virtual Host* drop-down list.

    If the MCP server has been deployed previously, the virtual host used in the last deployment is preselected. If the MCP server is being deployed for the first time, the virtual host selected during design time is preselected in the deployment dialog. You can change the selected virtual host before deploying the artifact.

    > ### Note:  
    > The virtual host configured in the MCP server at design time and the virtual host selected during deployment can be different. If you select a different virtual host during deployment, the runtime endpoint is generated using the deployed virtual host. Therefore, in *Monitor* \> *Manage Integration Content*, the URL for the MCP server displayed under *Endpoints* reflects the virtual host currently used by the deployed runtime artifact.
    > 
    > If the MCP server is configured with the virtual host ***api-dev.company.com*** at design time, but you select ***api-prod.company.com*** during deployment, the design-time configuration continues to show ***api-dev.company.com***. However, after deployment, the endpoint URL displayed in *Monitor* \> *Manage Integration Content* uses ***api-prod.company.com***, because it reflects the virtual host associated with the deployed runtime artifact.




<a name="loio017ba42fbcc04686ae368af1357a9df3__result_l2r_tvf_5pb"/>

## Results

Once an MCP server is deployed, it becomes available for consumption.



<a name="loio017ba42fbcc04686ae368af1357a9df3__postreq_f3l_hpl_q1c"/>

## Next Steps

After deploying an MCP server, you can check the runtime logs and the status of the artifact. For more information, see [Monitor APIs and MCP Servers](monitor-apis-and-mcp-servers-399b6c6.md).

> ### Note:  
> The MCP server deployed to an Integration Cell runtime invokes an HTTPS backend endpoint, the backend certificate must be trusted by the runtime keystore. If the required certificate is not available in the keystore, invocations will fail with an internal server error. You can see the detailed error message in Manage Processing Logs.
> 
> To add a trusted certificate to the runtime keystore, see [Uploading a Keystore](uploading-a-keystore-0db193a.md) and [Updating a Certificate](updating-a-certificate-1fa04fa.md).

