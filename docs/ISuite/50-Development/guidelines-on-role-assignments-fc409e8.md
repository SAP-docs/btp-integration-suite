<!-- loiofc409e8395724a70ad21a1fcfeaebedf -->

# Guidelines on Role Assignments

The combined usage of the following role collections, respectively, authorization groups \(as described under [Personas for Cloud Integration](../60-Security/personas-for-cloud-integration-2937e5c.md)\) gives you full control of the tenant in terms of design, monitoring, and administration.

Assigning these role collections/authorization groups to a user is a good choice for the source tenant \(development system\). However, assigning these role collections/authorization groups to a user on target tenants can lead to undesired behavior and inconsistencies with the transport system. To avoid that a user gets too many permissions in the target system, it's necessary to define permissions on a more detailed level on the target tenant \(test and production\).


<table>
<tr>
<th valign="top">

Required on Target Tenant

</th>
<th valign="top">

Avoid on Target Tenant

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

AuthGroup.IntegrationDeveloper \(Neo\)

PI\_Integration\_Developer \(Cloud Foundry\)

</td>
<td valign="top">

Allows user to connect to Cloud Integration and to display, download, and deploy artifacts.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

AuthGroup.BusinessExpert \(Neo\)

PI\_Business\_Expert \(Cloud Foundry\)

</td>
<td valign="top">

Allows user to perform business tasks like, for example, examining the payload, monitor integration flows, status of integration artifacts.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

AuthGroup.Administrator \(Neo\)

PI\_Administrator \(Cloud Foundry\)

</td>
<td valign="top">

Allows user to connect to Cloud Integration and to perform administrative tasks.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

WebToolingWorkspace.Write \(Neo\)

WorkspacePackagesEdit \(Cloud Foundry\)

</td>
<td valign="top">

Allows user to update a package, create/edit/import/delete a package and its artifacts.

> ### Tip:  
> Updating, creating, editing, importing, or deleting a package or its artifacts on a target tenant isn't recommended. Changes made on the target tenant are overridden when the package is retransported. In addition, objects not properly saved after editing lead to errors while transporting. For that reason, those roles must not be assigned to a user on the target tenant.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

TransportModule.write \(Neo\)

WorkspacePackagesTransport \(Cloud Foundry\)

</td>
<td valign="top">

Allows user to export, import, and update packages.

> ### Tip:  
> Export for transport and import or update a package from transport must be also restricted on the target tenant \(as the transport works with CTS+ or TMS as recommended options\). However, still the export, import, and update of packages can be available just in source tenant with these roles.



</td>
</tr>
<tr>
<td valign="top">

WebToolingWorkspace.Read \(Neo\)

WorkspacePackagesRead \(Cloud Foundry\)

</td>
<td valign="top">

 

</td>
<td valign="top">

Allows user to view packages and artifacts.

> ### Tip:  
> On the target tenant, it's still needed to access and view the transported packages and artifacts.



</td>
</tr>
<tr>
<td valign="top">

WebTooling.IntegrationFlowConfigure \(Neo\)

WorkspacePackagesConfigure \(Cloud Foundry\)

</td>
<td valign="top">

 

</td>
<td valign="top">

Allows user to configure artifacts \(integration flows and value mappings\).

> ### Tip:  
> After transporting a package from source tenant to target tenant, artifacts \(integration flows and value mappings\) must be configured on the target tenant.



</td>
</tr>
<tr>
<td valign="top">

NodeManager.read, GenerationAndBuild.generationandbuildcontent, NodeManager.deploycontent \(Neo\)

WorkspaceArtifactsDeploy \(Cloud Foundry\)

</td>
<td valign="top">

 

</td>
<td valign="top">

Allows user to deploy artifacts.

> ### Tip:  
> After transport to target tenant and configuring the artifacts, artifacts must be deployed.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

WebToolingCatalog.OverviewRead, WebToolingCatalog.DetailsRead, WebToolingWorkspace.Write \(Neo\)

CatalogPackagesRead, CatalogPackageArtifactsRead, CatalogPackagesCopy \(Cloud Foundry\)

</td>
<td valign="top">

Allows user to access SAP Business Accelerator Hub \(*Discover* section\).

> ### Tip:  
> Standard packages are published on SAP Business Accelerator Hub. A good practice is to subscribe only a single tenant to the SAP Business Accelerator Hub \(see [Subscribe Only a Single Tenant to SAP Business Accelerator Hub](subscribe-only-a-single-tenant-to-sap-business-accelerator-hub-185a52a.md)\). If you apply this rule, the standard packages are copied only to the workspace of the source tenant and transported to the target tenant. If there's an update for those packages, then this update can only be applied to the source tenant. Standard packages that are transported to a target tenant do not get updates on that target tenant. To have the updates applied, the package with the update applied must be transported from source to target tenant. To implement this behavior, you can restrict the access to the SAP Business Accelerator Hub on the target tenant assigning these roles just to the source tenant.



</td>
</tr>
<tr>
<td valign="top">

All roles related to the *Monitor* area \(see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md)\)

</td>
<td valign="top">

 

</td>
<td valign="top">

Allows user to perform tasks associated with monitoring and operations.

> ### Tip:  
> There are objects that can't be transported using the transport system. In addition, monitoring- and operations-related tasks must be allowed on the target tenant.



</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

WebToolingSettingsProductProfiles.savetenantconfiguration

</td>
<td valign="top">

Allows user configure the transport option.

> ### Tip:  
> The selection of what transport mechanism to use is done just on the source tenant.



</td>
</tr>
</table>

For more information on the individual roles and tasks, see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

Certain roles must be assigned also in the transport system to determine the responsibilities of who can do what \(for example, import a transport order into a queue, release an order\).

For more information on roles in CTS+, see [CTS Roles and Authorizations](https://help.sap.com/viewer/864321b9b3dd487d94c70f6a007b0397/7.5.10/en-US/3145ef39521e3314e10000000a11402f.html).

For more information on roles in TMS, see [Security](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/51939a49db9749578b7e237139bfd08d.html).

If you have implemented complex transport routes, it's a good practice to assign attributes to certain roles in TMS to restrict the corresponding authorizations to specific transport nodes only. For example, one person is responsible for releasing one order to test environment while a second one is responsible for production. You can find more information in section *Transport Node-Specific Attributes* under [Security](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/51939a49db9749578b7e237139bfd08d.html).

