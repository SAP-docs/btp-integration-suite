<!-- loio2c6214a3228e4b4cba207f49fda92ed4 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Configuring User Access to SAP Integration Suite

Assign the required roles and role collections to users for accessing the individual capabilities.



<a name="loio2c6214a3228e4b4cba207f49fda92ed4__prereq_xvk_bm5_3tb"/>

## Prerequisites

You have the *Integration\_Provisioner* role assigned to you.

The *Integration\_Provisioner* role:

-   Gives you initial access to the SAP Integration Suite.
-   Lets you add and manage capabilities. See [Activating and Managing Capabilities](activating-and-managing-capabilities-2ffb343.md)

Once these steps are completed, you add users and assign the various roles associated with the respective capabilities. This process allows different users to access the necessary functionalities.



## Context

Once you’ve activated capabilities in the Integration Suite, you must assign users the required roles and role collections to access the functionality of these capabilities.

For more information on role collections, see [Roles and Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/14a877c6e2f14832999df500ffa6e05e.html).



## Procedure

1.  To assign role collections to a user, go to your subaccount and navigate to *Security* \> *Users*.

2.  Choose *Create* to add a new user.

    If the user details already exist in the subaccount, you can skip step 2 and 3 and continue from step 4.

3.  Enter the *User Name* and *E-Mail*, and choose *Create*.

4.  Choose the user and under *Role Collections* section select <span class="SAP-icons-V5"></span> Additional Options and choose *Assign Role Collection*.

5.  In the resulting dialog box, select the checkbox of the role collection that you want to assign to the user and choose *Assign Role Collection*.

    The following role collections are available for each capability in SAP Integration Suite:

    **Roles**


    <table>
    <tr>
    <th valign="top">

    Capability
    
    </th>
    <th valign="top">

    Role Collection
    
    </th>
    <th valign="top">

    Tasks
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="4">
    
    Cloud Integration

    For detailed list of scope and actions for each role collection, see [Tasks and Permissions for Cloud Integration](60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).
    
    </td>
    <td valign="top">
    
    *PI\_Read\_Only*
    
    </td>
    <td valign="top">
    
    Refer to [Read-Only Persona](https://help.sap.com/docs/integration-suite/sap-integration-suite/cloud-integration-persona#loio4b4ba1c553474259b5be661f4ef0702c__read) for the tasks.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Business\_Expert*
    
    </td>
    <td valign="top">
    
    Refer to [Business Expert Persona](https://help.sap.com/docs/integration-suite/sap-integration-suite/cloud-integration-persona#loio4b4ba1c553474259b5be661f4ef0702c__bus) for the tasks.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Integration\_Developer*
    
    </td>
    <td valign="top">
    
    Refer to [Integration Developer Persona](https://help.sap.com/docs/integration-suite/sap-integration-suite/cloud-integration-persona#loio4b4ba1c553474259b5be661f4ef0702c__dev) for the tasks.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Administrator*
    
    </td>
    <td valign="top">
    
    Refer to [Tenant Administrator Persona](https://help.sap.com/docs/integration-suite/sap-integration-suite/cloud-integration-persona#loio4b4ba1c553474259b5be661f4ef0702c__admin) for the tasks.
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="4">
    
    API Management
    
    </td>
    <td valign="top">
    
    *APIManagement.Selfservice.Administrator*
    
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
    
    Role Collection for API business hub enterprise: *AuthGroup.SelfService.Admin*
    
    </td>
    <td valign="top">
    
    -   Onboard to API business hub enterprise
    -   Gain access to API business hub enterprise. See [Setting Up API Management Capability](50-Development/setting-up-api-management-capability-f34e86c.md)


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Role Collection for Graph: *Graph.KeyUser*
    
    </td>
    <td valign="top">
    
    -   Create business data graphs
    -   Activate business data graphs

    See [Define Users](https://help.sap.com/docs/graph/initial-setup#2.-define-users-for-graph).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Role Collection for Graph: *GraphNavigator.Viewer*
    
    </td>
    <td valign="top">
    
    Use the Graph Navigator in SAP API business hub enterprise to inspect business data graphs. See [Define Users](https://help.sap.com/docs/graph/initial-setup#2.-define-users-for-graph).
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="2">
    
    Event Mesh
    
    </td>
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
    <tr>
    <td valign="top" rowspan="2">
    
    Integration Advisor
    
    </td>
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


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Open Connectors
    
    </td>
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
    <tr>
    <td valign="top" rowspan="3">
    
    Trading Partner Management
    
    </td>
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
    <tr>
    <td valign="top">
    
    *Role* : AuthGroup\_TenantPartnerDirectoryConfigurator
    
    </td>
    <td valign="top">
    
    This is a role that needs to be assigned to a role collection in order to

    -   Activate agreements and publish their content into the partner directory.
    -   Deactivate agreements.


    You need to create a new Role Collection and assign this role to it. To know more, see [Define a Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/define-role-collection).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    -   *APIFullAccess*


    
    </td>
    <td valign="top">
    
    -   Get runtime access to the registered OData services.


    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="5">
    
    Integration Assessment
    
    </td>
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
    <tr>
    <td valign="top" rowspan="2">
    
    Migration Assessment
    
    </td>
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


