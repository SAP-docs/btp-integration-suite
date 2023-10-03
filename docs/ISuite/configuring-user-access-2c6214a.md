<!-- loio2c6214a3228e4b4cba207f49fda92ed4 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Configuring User Access

Assign the required roles to users for accessing the individual capabilities.



<a name="loio2c6214a3228e4b4cba207f49fda92ed4__prereq_xvk_bm5_3tb"/>

## Prerequisites

You have the **Integration\_Provisioner** role assigned to you.



## Context

Once you’ve activated capabilities in the Integration Suite, you must assign users the required roles and role collections to access the functionality of these capabilities.

For more information on role collections, see [Roles and Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/14a877c6e2f14832999df500ffa6e05e.html).



## Procedure

1.  To assign role collections to a user, go to your subaccount and navigate to *Security* \> *Users*.

2.  Choose *Create* to add a new user.

    If the user details already exist in the subaccount, you can skip step 2 and 3 and continue from step 4.

3.  Enter the *User Name* and *E-Mail*, and choose *Create*.

4.  Choose the user and select <span class="SAP-icons"></span> under *Role Collections* section and choose *Assign Role Collection*.

5.  In the resulting dialog box, select the checkbox of the role collection that you want to assign to the user and choose *Assign Role Collection*.

    > ### Note:  
    > Clear your web browser cache and cookies before navigating to *Go to Application*.

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

    You Can...


    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="4">
    
    Cloud Integration

    For detailed list of scope and actions for each role collection, see [Tasks and Permissions](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/556d5575d4b0483e85d4f3251f21d0ec.html "") :arrow_upper_right:.


    
    </td>
    <td valign="top">
    
    *PI\_Read\_Only* 


    
    </td>
    <td valign="top">
    
    -   Discover and copy pre-shipped standard packages

    -   Monitor integration flows and the status of integration artifacts.

    -   View packages and package artifacts in *Design* workspace

    -   View data store entries

    -   View access policies

    -   View B2B partner profiles and agreements

    -   View design time artifact locks.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Business\_Expert* 


    
    </td>
    <td valign="top">
    
    -   Discover and copy pre-shipped standard packages

    -   Monitor integration flows and the status of integration artifacts.

    -   Edit trace configuration and change log levels and archiving configuration.

    -   View packages and package artifacts in *Design* workspace.

    -   View data store entries.

    -   View design time artifact locks.

    -   Inspect usage of integration resources.

    -   Edit B2B partner profiles and contact persons.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Integration\_Developer* 


    
    </td>
    <td valign="top">
    
    -   Do *PI\_Read\_Only* and *PI\_Business\_Expert* tasks.

    -   Create, edit, import, export, delete package with its artifacts.

    -   Deploy/undeploy artifacts.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Administrator* 


    
    </td>
    <td valign="top">
    
    -   Do *PI\_Integration\_Developer* tasks.

    -   Handle tenant level settings like transport, connection to SAP Process Orchestration systems, manage software updates, and a few more.

    -   Manage access policies to restrict user access of integration content.

    -   Deploy security content.

    -   Delete messages from transient data store.

    -   Delete design time artifact locks.



    
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

    For more information on relevant roles, see [Assign User Roles in API Management](assign-user-roles-in-api-management-911ca5a.md).

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
    
    Integration Advisor

    For more information on assigning roles, see [Assigning Users](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b5226b95e11b42cd9e257ae6d2b0ee0a.html).


    
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
    
    *iacd-content-administrator*


    
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

    To permit additional users access to Open Connectors, assign the OpenConnectors\_User role collection to the new user.

    > ### Note:  
    > No additional role collection assignment needed, if the logged-in user already has the ‘Integration Provisioner’ role collection assigned which you need for general user management.


    
    </td>
    <td valign="top">
    
    Add non-SAP cloud applications to your integration scenarios.

    > ### Note:  
    > Just adding the OpenConnectors\_User role collection in the SAP BTP Trust Configuration cockpit isn't sufficient to access Open Connectors. The newly added user will have to be explicitly added as a **member** by the user who enabled SAP Integration Suite \(or by any other user who already has the **Account Admin** privileges\).
    > 
    > See [Open Connectors](https://help.openconnectors.ext.hana.ondemand.com/home/ac-roles).


    
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


    To know more, see [Additional Configurations for Trading Partner Management](additional-configurations-for-trading-partner-management-bcf7f21.md)


    
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
    -   Create interface requests


    
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
    -   Determine integration technologies, application profile and application instance.
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
    

