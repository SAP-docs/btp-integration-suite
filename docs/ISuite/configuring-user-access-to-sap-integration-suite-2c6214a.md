<!-- loio2c6214a3228e4b4cba207f49fda92ed4 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Configuring User Access to SAP Integration Suite

Assign the required roles and role collections to users for accessing the individual capabilities.



<a name="loio2c6214a3228e4b4cba207f49fda92ed4__section_njn_blz_l2c"/>

## Prerequisites

You have the *Integration\_Provisioner* role assigned to you.

The *Integration\_Provisioner* role:

-   Gives you initial access to the SAP Integration Suite.
-   Lets you add and manage capabilities. See [Activating and Managing Capabilities](activating-and-managing-capabilities-2ffb343.md)



<a name="loio2c6214a3228e4b4cba207f49fda92ed4__section_vcs_wvn_m2c"/>

## Context

Once you have subscribed to SAP Integration Suite and you’ve activated capabilities you must assign users the required roles and role collections to access the functionality of these capabilities.

For more information on role collections, see [Roles and Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/14a877c6e2f14832999df500ffa6e05e.html).



<a name="loio2c6214a3228e4b4cba207f49fda92ed4__section_xbf_glz_l2c"/>

## Procedure

1.  To assign role collections to a user, go to your subaccount and navigate to *Security* \> *Users*.
2.  Choose *Create* to add a new user.

    If the user details already exist in the subaccount, you can skip step 2 and 3 and continue from step 4.

3.  Enter the *User Name* and *E-Mail*, and choose *Create*.
4.  Choose the user and under *Role Collections* section select <span class="SAP-icons-V5"></span> Additional Options Additional Options and choose *Assign Role Collection*.
5.  In the resulting dialog box, select the checkbox of the role collection that you want to assign to the user and choose *Assign Role Collection*.

Expand the following sections to learn about the role collections available for that capability of SAP Integration Suite.



### Cloud Integration

For detailed list of scope and actions for each role collection, see [Tasks and Permissions for Cloud Integration](60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Tasks

</th>
</tr>
<tr>
<td valign="top">

*PI\_Read\_Only* 

</td>
<td valign="top">

Refer to [Read-Only Persona](https://help.sap.com/docs/integration-suite/sap-integration-suite/persona-2937e5ca6ef448cfb21451a2461cc2a6?q=persona&state=DRAFT&version=DEV) for the tasks.

</td>
</tr>
<tr>
<td valign="top">

*PI\_Business\_Expert* 

</td>
<td valign="top">

Refer to [Business Expert Persona](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fhelp.sap.com%2Fdocs%2Fintegration-suite%2Fsap-integration-suite%2Fpersona-2937e5ca6ef448cfb21451a2461cc2a6%3Flocale%3Den-US%26q%3Dpersona%26state%3DDRAFT%26version%3DDEV) for the tasks.

</td>
</tr>
<tr>
<td valign="top">

*PI\_Integration\_Developer* 

</td>
<td valign="top">

Refer to [Integration Developer Persona](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fhelp.sap.com%2Fdocs%2Fintegration-suite%2Fsap-integration-suite%2Fpersona-2937e5ca6ef448cfb21451a2461cc2a6%3Flocale%3Den-US%26q%3Dpersona%26state%3DDRAFT%26version%3DDEV) for the tasks.

</td>
</tr>
<tr>
<td valign="top">

*PI\_Administrator* 

</td>
<td valign="top">

Refer to [Tenant Administrator Persona](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fhelp.sap.com%2Fdocs%2Fintegration-suite%2Fsap-integration-suite%2Fpersona-2937e5ca6ef448cfb21451a2461cc2a6%3Flocale%3Den-US%26q%3Dpersona%26state%3DDRAFT%26version%3DDEV) for the tasks.

</td>
</tr>
</table>



### API Management


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

*APIManagement.SelfService.Administrator*

</td>
<td valign="top">

-   Complete the onboarding process
-   Access the *API Settings* page. See [Setting Up API Management Capability](50-Development/setting-up-api-management-capability-f34e86c.md) 

For more information on relevant roles, see [Assign User Roles in API Management](https://help.sap.com/viewer/de4066bb3f9240e3bfbcd5614e18c2f9/Cloud/en-US/911ca5a620e94ab581fa159d76b3b108.html "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.") :arrow_upper_right:.

For end-to end instructions on how to set up and configure API Management, refer the tutorial [Set Up API Management from Integration Suite | Tutorials for SAP Developers](https://developers.sap.com/tutorials/api-mgmt-isuite-initial-setup.html).

</td>
</tr>
<tr>
<td valign="top">

Role Collection for Developer Hub: *AuthGroup.SelfService.Admin* 

</td>
<td valign="top">

-   Onboard to Developer Hub.
-   Gain access to Developer Hub. See [Setting Up API Management Capability](50-Development/setting-up-api-management-capability-f34e86c.md)



</td>
</tr>
<tr>
<td valign="top">

Role Collection for Graph: *Graph.KeyUser* 

</td>
<td valign="top">

-   Create business data graphs
-   Activate business data graphs

See [Define Users](https://help.sap.com/docs/integration-suite/sap-integration-suite/initial-setup-12ad448225ac47049982d9faab7978a3?version=CLOUD#3-define-users-for-graph).

</td>
</tr>
<tr>
<td valign="top">

Role Collection for Graph: *GraphNavigator.Viewer* 

</td>
<td valign="top">

Use the Graph Navigator in SAP Developer Hub to inspect business data graphs. See [Define Users](https://help.sap.com/docs/integration-suite/sap-integration-suite/initial-setup-12ad448225ac47049982d9faab7978a3?version=CLOUD#3-define-users-for-graph).

</td>
</tr>
<tr>
<td valign="top">

Role Collection for Graph: *Graph.Guest* 

</td>
<td valign="top">

Assign the Graph\_Guest authorization role to one or more users so that they have read-only access to Graph and the Graph Configuration API. See [Define Users](https://help.sap.com/docs/integration-suite/sap-integration-suite/initial-setup-12ad448225ac47049982d9faab7978a3?version=CLOUD#3-define-users-for-graph).

</td>
</tr>
</table>



### Event Mesh


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

*EventMeshDeveloper*

</td>
<td valign="top">

-   Manage queues and topic subscriptions

-   Monitor event mesh and queues




</td>
</tr>
<tr>
<td valign="top">

*EventMeshAdmin*

</td>
<td valign="top">

-   Do *EventMeshDeveloper* tasks.

-   Manage event mesh lifecycle




</td>
</tr>
</table>



### Integration Advisor


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

*iadv-content-developer*

</td>
<td valign="top">

-   Discover the different Type systems enabled for the B2B standards
-   Design your own custom type system
-   Create Message Implementation Guidelines \(MIGs\) using the type systems
-   Simulate and activate your MIGs
-   Create interfaces and mappings from these MIGs using Mapping Guidelines \(MAGs\)
-   Simulate and activate your MAGs
-   Inject or export these data as Runtime Artifacts
-   Export and import your MIGs and MAGs



</td>
</tr>
<tr>
<td valign="top">

*iadv-content-administrator*

</td>
<td valign="top">

-   iadv-content-developer tasks
-   Unlock MIGs and MAGs locked by other users
-   Disable Proposal service



</td>
</tr>
<tr>
<td valign="top">

*iadv-content-read*

</td>
<td valign="top">

-   Read-only access to view the following artefacts:

    -   Type system library

    -   MIGs
    -   MAGs
    -   Custom Type Systems

-   Simulate MIGs and MAGs
-   Export artefacts

> ### Note:  
> Users with this role can view and browse these objects, but cannot edit or modify them in any way.
> 
> This role does not include importing artefacts \(MIGs/MAGs\).



</td>
</tr>
</table>



### Trading Partner Management

****


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

PI\_Business\_Expert

</td>
<td valign="top">

-   Monitor your B2B interchanges and their payloads
-   Monitor integration flows and the status of integration artifacts
-   Read and inspect message payloads and attachments



</td>
</tr>
<tr>
<td valign="top">

PI\_Integration\_Developer

</td>
<td valign="top">

-   Create and maintain your company profile
-   Create and maintain trading partner profiles
-   Create and maintain agreement templates
-   Create and maintain agreements using the templates
-   Activate your trading partner agreements
-   Export and import your agreements
-   Update the MIG/MAG information for a group of agreements
-   Activate/Deactivate a group of agreements.
-   Discover integration flow packages
-   Configure and deploy your generic integration flows
-   Download artifacts



</td>
</tr>
</table>

****


<table>
<tr>
<th valign="top">

Role

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

AuthGroup\_TenantPartnerDirectoryConfigurator

</td>
<td valign="top">

You need to create a new Role Collection and assign this role to it. To know more, see [Define a Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/define-role-collection).

This is a role that needs to be assigned to a role collection in order to

-   Activate agreements and publish their content into the partner directory.
-   Deactivate agreements.



</td>
</tr>
</table>



### OData Provisioning

Create a role collection and add the roles described here to that role collection before assigning it to the user who will work with this capability. See [Define a Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/define-role-collection).

> ### Note:  
> When you subscribe to the OData Provisioning capability, you can assign several associated roles. However, for the SAP Integration Suite, only the following roles should be assigned:*ODPManage*, *ODPAPIAccess*, *APIFullAccess*.


<table>
<tr>
<th valign="top">

Role

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

*ODPManage* 

</td>
<td valign="top">

-   View and register OData services



</td>
</tr>
<tr>
<td valign="top">

*APIFullAccess*

</td>
<td valign="top">

-   Get runtime access to the registered OData services.



</td>
</tr>
<tr>
<td valign="top">

*ODPAPIAccess*

</td>
<td valign="top">

-   Access the service document.



</td>
</tr>
</table>



### Data Space Integration


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

DataspaceReadOnly

</td>
<td valign="top">

-   See the assets, policies, and contract definitions that were created.

-   See the negotiated agreements.




</td>
</tr>
<tr>
<td valign="top">

DataspaceConsumer

</td>
<td valign="top">

-   Initiate contract negotiations.

-   Initiate transfer of assets.

-   Use the Data Management API to request data via Data Space Integration.

-   Use the EDR Management API to request data via Data Space Integration.

-   Read the negotiated agreements.




</td>
</tr>
<tr>
<td valign="top">

DataspaceProvider

</td>
<td valign="top">

-   Create assets, policies, and contract definitions.

-   See the negotiated agreements.




</td>
</tr>
<tr>
<td valign="top">

DataspaceTechnicalAdmin

</td>
<td valign="top">

-   Onboard Data Space Integration to a data space.

-   Assign company policies to use cases.




</td>
</tr>
<tr>
<td valign="top">

DataspaceBusinessAdmin

</td>
<td valign="top">

-   Create and edit company policies.

-   Assign company policies to use cases.



</td>
</tr>
</table>



### Open Connectors


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

*OpenConnectors\_User*

To permit additional users access to Open Connectors, assign the `OpenConnectors_User` role collection to the new user.

> ### Note:  
> No action needed if the logged user already has the `Integration Provisioner` role collection.



</td>
<td valign="top">

Add non-SAP cloud applications to your integration scenarios.

> ### Note:  
> Just adding the `OpenConnectors_User` role collection in the SAP BTP Trust Configuration cockpit isn't sufficient to access Open Connectors. The newly added user will have to be explicitly added as a **member** by the Open Connectors admin users.
> 
> See [Grant Users Access to Open Connectors, Capability Within SAP Integration Suite](https://blogs.sap.com/2024/01/08/grant-the-user-to-access-to-open-connectors-capability-of-integration-suite/) .



</td>
</tr>
</table>



### Integration Assessment


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

INTAS\_BusinessDomainExpert

</td>
<td valign="top">

-   Create business solution requests for the business users and project managers.
-   Create interface requests.



</td>
</tr>
<tr>
<td valign="top">

INTAS\_IntegrationArchitect

</td>
<td valign="top">

-   Fill out questionnaires.
-   Determine application profile and application instance.



</td>
</tr>
<tr>
<td valign="top">

INTAS\_EnterpriseArchitect

</td>
<td valign="top">

-   Maintain the settings of a business solution request, namely integration domain, integration style, integration use case pattern, key characteristics, and questionnaire.
-   Determine integration technologies, application profile, and application instance.
-   Specify integration guidelines and best practices.



</td>
</tr>
<tr>
<td valign="top">

INTAS\_Administrator

</td>
<td valign="top">

-   Edit/Delete ISA-M data, Questionnaire, Applications, Technologies all sections, Business Solution Request.



</td>
</tr>
<tr>
<td valign="top">

INTAS\_ViewOnly

</td>
<td valign="top">

-   View ISA-M data, Questionnaire, Applications, Technologies, Business Solution Request, Interface Assessment.



</td>
</tr>
</table>



### Migration Assessment


<table>
<tr>
<th valign="top">

Role Collection

</th>
<th valign="top">

Task

</th>
</tr>
<tr>
<td valign="top">

PIMAS\_Admin

</td>
<td valign="top">

-   Read and maintain system data, rule data, and effort data.

> ### Note:  
> The role collection PIMAS\_Admin is superordinate to all other role collections available for Migration Assessment.



</td>
</tr>
<tr>
<td valign="top">

PIMAS\_IntegrationAnalyst

</td>
<td valign="top">

-   Read system data, rule data, and effort data.
-   Read and maintain extraction data requests.
-   Read and maintain scenario evaluation requests.
-   Download scenario evaluation results.
-   Read monitoring data.



</td>
</tr>
</table>

> ### Note:  
> Clear your web browser cache and cookies before accessing to the application, by navigating to *Services* \> *Instances and Subscription* and then select the instance of the application.

