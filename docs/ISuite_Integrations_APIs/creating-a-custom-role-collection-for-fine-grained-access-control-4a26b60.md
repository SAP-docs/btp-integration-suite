<!-- loio4a26b609e40e4b1e9ab091df852eb81f -->

# Creating a Custom Role Collection for Fine-Grained Access Control

Create a custom role collection in the SAP BTP Cockpit by selecting only the specific roles required for a user’s responsibilities, enabling precise and least-privilege access management.



## Context

SAP BTP Cockpit provides several predefined role collections that simplify permission assignment by bundling authorizations for common user personas. For example, the predefined role collection **PI\_Integration\_Developer** grants access to both the Design and Monitor sections of the SAP Integration Suite. It allows users to create, design, deploy, copy, import, download, and delete integration and API artifacts, as well as monitor integration processes. While predefined role collections are convenient, they may not always align with specific environments or user responsibilities — in some cases, they may grant broader permissions than necessary, while in others, they may not include all the permissions a user actually requires. In such cases, creating a custom role collection allows you to tailor permissions precisely to a user’s role — either by adding the additional roles needed or by including only a subset of roles — ensuring adherence to the principle of least privilege.

> ### Example:  
> Consider a integration developer working on the Production tenant. Their job is to:
> 
> -   Monitor APIs and message processing logs \(MPLs\).
> -   Investigate failed messages and troubleshoot issues.
> -   View deployed artifacts and security material.
> 
> However, this developer should not be able to modify, deploy, or delete integration artifacts in production, as any such changes must follow a controlled transport process.
> 
> If you assign the predefined `PI_Integration_Developer` role collection to this user, they would inadvertently receive edit and deploy permissions, which violates the principle of least privilege and poses a risk to the production environment.
> 
> To address this, you can create a custom role collection \(for example, PI\_Production\_Support\) and include only the roles needed for read-only monitoring and troubleshooting, such as:
> 
> -   `MonitoringDataRead` – to view MPLs, deployed artifacts, and log files.
> -   `MessageProcessingLocksRead` – to view message locks during troubleshooting.
> -   `WorkspacePackagesRead` – to view packages and artifacts without editing.
> -   `CredentialsRead` – to verify credential configurations.
> 
> This way, the support engineer has exactly the access they need — nothing more, nothing less.



## Custom User Roles


<table>
<tr>
<th valign="top">

User Roles

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

CredentialsEdit

</td>
<td valign="top">

Create, change, delete, or undeploy credentials.

</td>
</tr>
<tr>
<td valign="top">

CredentialsRead

</td>
<td valign="top">

View credentials.

</td>
</tr>
<tr>
<td valign="top">

MessageProcessingLocksDelete

</td>
<td valign="top">

Delete message processing locks.

</td>
</tr>
<tr>
<td valign="top">

MessageProcessingLocksRead

</td>
<td valign="top">

View message processing locks.

</td>
</tr>
<tr>
<td valign="top">

MonitoringArtifactsDeploy

</td>
<td valign="top">

Add, edit, and undeploy number ranges; undeploy integration flows.

</td>
</tr>
<tr>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

View MPLs, deployed artifacts, certificate-to-user mappings, JDBC data sources, number ranges, and system log files; download MPLs and log files; deploy integration flows; perform connectivity tests without authentication.

</td>
</tr>
<tr>
<td valign="top">

SecurityMaterialDownload

</td>
<td valign="top">

Download known-host files, key-store files, and keyrings.

</td>
</tr>
<tr>
<td valign="top">

SecurityMaterialEdit

</td>
<td valign="top">

Create, change, delete, or undeploy known-host files, key-store files, keyrings, and user-certificate mappings.

</td>
</tr>
<tr>
<td valign="top">

UserRolesEdit

</td>
<td valign="top">

Create, edit, and delete user roles.

</td>
</tr>
<tr>
<td valign="top">

WorkspaceArtifactLocksDelete

</td>
<td valign="top">

Delete design-time artifact locks.

</td>
</tr>
<tr>
<td valign="top">

WorkspaceArtifactLocksRead

</td>
<td valign="top">

View design-time artifact locks.

</td>
</tr>
<tr>
<td valign="top">

WorkspaceArtifactsDeploy

</td>
<td valign="top">

Create, import, export, and delete packages and package artifacts in the workspace \(Design\).

</td>
</tr>
<tr>
<td valign="top">

WorkspaceDesignGuidelinesConfigure

</td>
<td valign="top">

Configure design guidelines from Tenant Settings.

</td>
</tr>
<tr>
<td valign="top">

WorkspacePackagesConfigure

</td>
<td valign="top">

Configure artifacts \(integration flows and value mappings\) in the workspace \(Design\)..

</td>
</tr>
<tr>
<td valign="top">

WorkspacePackagesEdit

</td>
<td valign="top">

Create, import, export, and delete packages and package artifacts in the workspace \(Design\).

</td>
</tr>
<tr>
<td valign="top">

WorkspacePackagesRead

</td>
<td valign="top">

View packages and package artifacts in the workspace \(Design\).

</td>
</tr>
<tr>
<td valign="top">

WorkspacePackagesTransport

</td>
<td valign="top">

Transport integration packages.

</td>
</tr>
</table>



## Creating a Custom Role Collection

1.  Create a custom role collection:
    1.  Open the SAP BTP cockpit and go to your *Subaccount*.
    2.  In the left navigation pane, choose *Security* \> *Role Collections*, and choose *Create*.
    3.  In the *Create Role Collection* dialog, provide a **Name** and **Description**, and choose *Create*.

        The custom role collection gets created.


2.  Add a custom role to the role collection you created in Step 1:
    1.  Search for and choose the newly created role collection.
    2.  Go to the *Roles* section and choose *Edit*.
    3.  In the *Roles* tab, choose the *Role Name* input field.

        The role selection screen opens.

    4.  Use the search field or dropdown filters under *Role Name* to display the roles that are available. The roles are sorted alphabetically. Choose the role you want to add.
    5.  **\(Optional\)** Repeat the selection process to add more roles.
    6.  Review the selected roles in the *Selected Roles* section, and choose *Add*.
    7.  Save your changes.




## Result

By following this approach, you have enforced the **principle of least privilege**, ensuring that users in sensitive environments, such as Production, have access strictly aligned with their responsibilities. This reduces the risk of accidental changes, strengthens governance, and supports compliance with your organization’s access control policies.

**Related Information**  


[Assigning Role Collections to Users](assigning-role-collections-to-users-80bb02e.md "Role collections enable you to group together the roles you create. The role collections you define can be assigned to users logged on to SAP ID service.")

