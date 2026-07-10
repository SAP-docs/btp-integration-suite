<!-- loio73b3e92140f046b28acf2ce506a5e0e3 -->

# Key Personas for API-Centric Integrations

When managing user access through the SAP BTP cockpit, you'll encounter a set of predefined role colections that can be assigned to users within your account. These roles are aligned with specific personas based on the primary responsibilities associated with integrations and APIs, ensuring that each user has the appropriate permissions to perform their tasks effectively.


<table>
<tr>
<th valign="top">

Persona

</th>
<th valign="top">

Role Collection

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Integration provisioner

</td>
<td valign="top">

Integration\_Provisioner

</td>
<td valign="top">

The Integration\_Provisioner role:

-   Gives you initial access to the SAP Integration Suite.
-   Lets you add and manage capabilities. For more information, see [Activate and Configure the API Management Capability](activate-and-configure-the-api-management-capability-f6eb433.md).



</td>
</tr>
<tr>
<td valign="top">

Tenant administrator

</td>
<td valign="top">

PI\_Administrator

</td>
<td valign="top">

Enables the administrator to perform administrative tasks on the tenant.

This persona includes authorization to tasks like:

-   Handling tenant level settings like transport, virtual host, manage software updates, and a few more.

-   Managing access policies to restrict user access of integration content

    > ### Note:  
    > This is supported only for APIs on Edge Integration Cell.

-   Monitoring API and MCP artifacts, and their runtime status.

-   Deploying security content

-   Deploying API Management artifacts

-   Deleting design time artifact locks.




</td>
</tr>
<tr>
<td valign="top">

API developer

</td>
<td valign="top">

PI\_Integration\_Developer

</td>
<td valign="top">

The PI\_Integration\_Developer role:

-   Grants access to the *Design* and *Monitor* sections in the SAP Integration Suite side navigation. For more information, see [Design APIs and MCP Servers](design-apis-and-mcp-servers-94957bc.md) and [Monitor APIs and MCP Servers](monitor-apis-and-mcp-servers-399b6c6.md).
-   Enables you to create, design, deploy, copy, import, download, and delete integration and API artifacts from the Design section.
-   Allows you to monitor integration artifacts and processes from the *Monitor* section.



</td>
</tr>
<tr>
<td valign="top">

Read-only persona

</td>
<td valign="top">

PI\_Read\_Only

</td>
<td valign="top">

The PI\_Integration\_DeveloperRead\_Only role:

-   Grants read-only access to API artifacts in the *Monitor* section of the SAP Integration Suite.
-   Also allows you to download integration flow artifacts for review or analysis.



</td>
</tr>
</table>

