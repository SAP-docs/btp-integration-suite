<!-- loio2c6214a3228e4b4cba207f49fda92ed4 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configuring User Access

Create and modify application roles and assign users to these roles.



<a name="loio2c6214a3228e4b4cba207f49fda92ed4__prereq_xvk_bm5_3tb"/>

## Prerequisites

You have the **Integration\_Provisioner** role assigned to you.



## Context

As a tenant administrator, you can group application roles in role collections. Typically, these role collections provide authorizations for certain types of users. For more information on role collections, see [Roles and Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/14a877c6e2f14832999df500ffa6e05e.html).



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
    <td valign="top" rowspan="3">
    
    Cloud Integration

    For more information on relevant roles, see [Understanding User Persona](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/4b4ba1c553474259b5be661f4ef0702c.html).


    
    </td>
    <td valign="top">
    
    *PI\_Business\_Expert*


    
    </td>
    <td valign="top">
    
    -   Monitor integration flows and the status of integration artifacts

    -   Read the message payload and attachments



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Administrator*


    
    </td>
    <td valign="top">
    
    -   Monitor integration flows and the status of integration artifacts

    -   Deploy security content

    -   Delete messages from transient data store



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *PI\_Integration\_Developer*


    
    </td>
    <td valign="top">
    
    -   Create Integration Flows

    -   Monitor integration flows and the status of integration artifacts

    -   Deploy integration content such as integration flows



    
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
    
    -   Complete the onboarding process and access the *API Settings* page.


    For end-to end instructions on how to set up and configure API Management, refer the tutorial [Set Up API Management from Integration Suite | Tutorials for SAP Developers](https://developers.sap.com/tutorials/api-mgmt-isuite-initial-setup.html).

    For more information on relevant roles, see [Assign User Roles in API Management](assign-user-roles-in-api-management-911ca5a.md).

    To set up the API Management service, see [Setting Up API Management Capability](../50-Development/setting-up-api-management-capability-f34e86c.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Role Collection for API business hub enterprise: *AuthGroup.SelfService.Admin* 


    
    </td>
    <td valign="top">
    
    Onboard to API business hub enterprise and get access to it.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Role Collection for Graph: *Graph\_Key\_User* 


    
    </td>
    <td valign="top">
    
    Create and activate business data graphs. For more information, see [Define Users](https://help.sap.com/docs/graph/initial-setup#2.-define-users-for-graph).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Role Collection for Graph: *Graph\_Navigator\_Viewer* 


    
    </td>
    <td valign="top">
    
    Use the Graph Navigator in SAP API business hub enterprise to inspect business data graphs. For more information, see [Define Users](https://help.sap.com/docs/graph/initial-setup#2.-define-users-for-graph).


    
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
    
    Create and deploy interfaces and mappings


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *iacd-content-administrator*


    
    </td>
    <td valign="top">
    
    Create and deploy interfaces and mappings

    Unlock MIGs and MAGs locked by other users


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Open Connectors


    
    </td>
    <td valign="top">
    
    *OpenConnectors\_User*

    > ### Note:  
    > No additional role collection assignment is needed, if the logged-in user already has the ‘Integration Provisioner’ role collection assigned.

    To permit additional users access to Open Connectors, assign the OpenConnectors\_User role collection to the new user.


    
    </td>
    <td valign="top">
    
    View the Open Connectors capability tile on the Integration Suite Launchpad.

    > ### Note:  
    > Just adding the OpenConnectors\_User role collection in the SAP BTP Trust Configuration cockpit isn't sufficient to access Open Connectors . The newly added user will have to be explicitly added as a **member** by the user who enabled the Integration Suite capability \(or by any other user who already has the **Account Admin** privileges\).
    > 
    > See [Open Connectors](https://help.sap.com/viewer/41a66e9fe3d34f80a50dfdad2357d633/1.0/en-US).


    
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
    
    -   Monitor integration flows and the status of integration artifacts

    -   Read the message payload and attachments



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    PI\_Integration\_Developer


    
    </td>
    <td valign="top">
    
    -   Perform all configurations related to trading partner such as creating and maintaining partner profiles, company profile, agreement templates and agreements, and activating partner agreements.

    -   Connect to a cluster using Integration Designer and to display, download, and deploy artifacts \(for example, integration flows\).


    
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
    
    -   Create business solution requests for business users.

    -   Create business solution requests for project managers.

    -   Create interface requests.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    INTAS\_IntegrationArchitect


    
    </td>
    <td valign="top">
    
    -   Fill out questionnaires.

    -   Review integration technologies.

    -   Determine application profile and application instance.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    INTAS\_EnterpriseArchitect


    
    </td>
    <td valign="top">
    
    -   Manage the settings of a business solution request.

    -   Determine integration technologies.

    -   Establish application profile and application instance.
    -   Specify integration guidelines and best practices.

    -   Incorporate new versions of SAP standard content into the dataset.

        > ### Note:  
        > Only an Enterprise Architect or an Administrator can perform this task.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    INTAS\_Administrator


    
    </td>
    <td valign="top">
    
    -   Manage applications.

    -   Submit Business Solution Request.

    -   Edit ISA-M data.

    -   Delete ISA-M data.

    -   Complete questionnaires.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    INTAS\_ViewOnly


    
    </td>
    <td valign="top">
    
    -   View ISA-M data.

    -   View questionnaires.

    -   View applications.

    -   View technologies.

    -   View Business Solution Request.

    -   View Interface Request.



    
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
    

