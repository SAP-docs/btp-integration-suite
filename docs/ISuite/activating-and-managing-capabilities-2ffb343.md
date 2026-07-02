<!-- loio2ffb343c163c48a4b3a90f9f3c487328 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Activating and Managing Capabilities

Activate capabilities for SAP Integration Suite.



<a name="loio2ffb343c163c48a4b3a90f9f3c487328__prereq_ydy_lxj_dmb"/>

## Prerequisites

-   You have access to the SAP Integration Suite home page. See [Working with SAP Integration Suite Home](20-Working_with_SAP_Integration_Suite_Home/working-with-sap-integration-suite-home-a53dce3.md).
-   You have the Integration\_Provisioner role collection assigned to your user. See [Subscribing and Configuring Initial Access to SAP Integration Suite](10-InitialSetup/subscribing-and-configuring-initial-access-to-sap-integration-suite-8a3c8b7.md).



<a name="loio2ffb343c163c48a4b3a90f9f3c487328__context_mpf_myf_dmb"/>

## Context

This topic describes how to add and activate relevant capabilities in SAP Integration Suite. The following capabilities are available:

-   Cloud Integration

-   API Management

    -   Developer Hub
    -   API Composition

-   Event Mesh

-   Open Connectors

-   Integration Advisor

-   Trading Partner Management

-   OData Provisioning

-   Data Space Integration

-   Integration Assessment

-   Migration Assessment


You can watch a short video about activating capabilities, and getting access to functionality here:





## Procedure

1.  On the SAP Integration Suite home page, under the *Capabilities* section, choose either *Add Capabilities* \(if it's your first time accessing the SAP Integration Suite home page\) or <span class="SAP-icons-V5"></span> *Manage Capabilities* ![](images/AddingCapabilities_SUI_16a5ec1.png).

2.  On the *Activate Capabilities* screen, under *Select Capabilities*, select the relevant capabilities as shown in the following table and choose *Next* to configure additional functionality for individual capabilities. ![](images/SelectCapabilitySUI_43d96ed.png)


    <table>
    <tr>
    <th valign="top">

    To Activate...
    
    </th>
    <th valign="top">

    Select...
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Cloud Integration
    
    </td>
    <td valign="top">
    
    *Build Integration Scenarios*

    > ### Note:  
    > -   Select the environment based on your operational needs:
    > 
    >     -   *Non-Production* for non-critical business activities like performance testing, testing new integration scenarios.
    >     -   *Production* for critical business activities.
    > 
    >     > ### Recommendation:  
    >     > If you want to activate both API Management and Cloud Integration capabilities within the same tenant, select the same environment for both capabilities. Once you have activated API Management capability, you can align the environment by setting the *Account Type* field \(Production or Non-Production\) on the *Settings* \> *Runtimes* \> *API Management* section. See [Enable API Management Capability](https://help.sap.com/docs/integration-suite/sap-integration-suite/enabling-api-management-capability-from-integration-suite).
    > 
    > -   To support the usage of Java Message Service \(JMS\) queues as temporary storage, select Message Queues. Using JMS message queues allow you to configure asynchronous decoupling of sender and receiver message processing to ensure that in case of an error a retry is done from SAP Integration Suite rather than the sender system. You can use the tenant to manage these queues. See [Managing Message Queues](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/cdcce24f484a41c08ab46d12ab666451.html).

    ![](images/CI_SUI_f5734a7.png)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    API Management
    
    </td>
    <td valign="top">
    
    *Manage APIs*

    On the next screen, the *API Modelling* checkbox appears, and is enabled by default.

    If you want to consume APIs and events published on Developer Hub—a web-based platform that allows organizations to publish their APIs and events for developers to discover, explore, and use—you need to select the *Developer Hub* checkbox.

    To expose your business data as a semantically connected data graph, select the *API Composition* checkbox.

    > ### Note:  
    > The Developer Hub checkbox must be selected in order to activate API Composition.

    For end-to end instructions on how to activate the API Management capability, see [Activating and Configuring API Management Capability](https://help.sap.com/docs/integration-suite/sap-integration-suite/enabling-api-management-capability-from-integration-suite). You can also refer to the [Set Up API Management from Integration Suite](https://developers.sap.com/tutorials/api-mgmt-isuite-initial-setup.html) tutorial for visual instructions.

    ![](images/SUI_API_e159e2f.png)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Event Mesh 
    
    </td>
    <td valign="top">
    
    *Manage Business Events*

    > ### Remember:  
    > If you're an existing customer of the standalone SAP Event Mesh service \(default plan\) or if you've subscribed to SAP S/4HANA Cloud Extensibility service, you can't subscribe to the Event Mesh capability in the same subaccount. In such cases, you must subscribe to SAP Integration Suite in a different subaccount.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    OData Provisioning

    > ### Remember:  
    > To register OData services from the SAP Business Suite you need to install a Cloud Connector and perform the necessary configurations for connecting to the on-premise back-end system. For more information, see [Cloud Connector](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/cloud-connector?version=Cloud).


    
    </td>
    <td valign="top">
    
    *Access data in SAP Business Suite*

    For end-to-end instructions on activating the OData Provisioning capability, see [Runtime Access and Role Assignment for OData Provisioning](https://help.sap.com/viewer/c0ec55d6862d4b01af33a70e79ed1a2e/CLOUD/en-US/b46816c20e02415597d5546b1e277e23.html "Steps to complete the activation of the OData Provisioning capability by providing runtime access and assigning roles.") :arrow_upper_right:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Open Connectors
    
    </td>
    <td valign="top">
    
    *Extend Non-SAP Connectivity* 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Integration Advisor
    
    </td>
    <td valign="top">
    
    *Implement Interfaces and Mapping* 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Trading Partner Management

    > ### Note:  
    > Cloud Integration \(with Message Queues\) and Integration Advisor capabilities are prerequisites for activating Trading Partner Management.


    
    </td>
    <td valign="top">
    
    *Manage Trading Partners* 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Data Space Integration 
    
    </td>
    <td valign="top">
    
    *Exchange Data Within Data Spaces* 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Integration Assessment
    
    </td>
    <td valign="top">
    
    *Manage and Provide Integration Technology Guidance* 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Migration Assessment 
    
    </td>
    <td valign="top">
    
    *Assess Migration Scenarios* 
    
    </td>
    </tr>
    </table>
    
3.  Choose *Activate*. ![](images/sui_summary_327220b.png)

    > ### Note:  
    > -   The availability of capabilities for activation is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://me.sap.com/notes/2903776).
    > 
    > -   If you face any issues during activation or the activation fails, then refer SAP Note [2904202](https://me.sap.com/notes/2904202) and proceed accordingly.
    > 
    > -   You can choose *Manage Capabilities* to activate additional capabilities at a later point in time.
    > 
    > -   After activation, assign the required role collections to users for accessing the individual capabilities. See [Configuring User Access](configuring-user-access-to-sap-integration-suite-2c6214a.md).




<a name="loio2ffb343c163c48a4b3a90f9f3c487328__result_pph_4z5_plb"/>

## Results

-   Capabilities are displayed on the home page as tiles. To access the functionalities offered by these capabilities, users must have the required role collections assigned. See [Configuring User Access to SAP Integration Suite](configuring-user-access-to-sap-integration-suite-2c6214a.md).
-   After activating Cloud Integration, create a service broker instance. See [Creating Service Instance and Service Key for Inbound Authentication](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/19af5e205fe14af6a4f8a9fd80d4dc92.html "With a service instance, you define how to access a certain SAP BTP service. In the context of SAP Integration Suite , a service instance is the definition of an OAuth client.") :arrow_upper_right:.

-   The API Management capability needs a few more configuration steps before activation. See [Additional Configurations for API Management](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/5ac63ab89ed64fb89a28382fc4b55990.html "In this section, you'll find information about different plans for managing API Management, API portal and Developer Hub.") :arrow_upper_right:.
-   The Event Mesh capability needs an additional configuration step before usage. See: [Initiating the Message Broker](https://help.sap.com/viewer/a01a83f4826d486b9fc66d1df0de9da4/CLOUD/en-US/61eb5dd788ee4d5ba476842a5e5aa135.html "Initiate the message broker before you get started with the Event Mesh capability.") :arrow_upper_right:.

-   After activating Data Space Integration, continue with the additional preparatory steps. See [Preparatory Steps](https://help.sap.com/viewer/c6f026f9206e4a60948e827535eef449/CLOUD/en-US/95366b2757d64a89aaa4efa6027a8fb4.html "Before you can perform the onboarding steps that are specific to Data Space Integration, you must be onboarded to SAP Integration Suite and have enabled Cloud Integration.") :arrow_upper_right:.

**Related Information**  


[Centralized Developer Hub](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/38422de917ee40e1a47df0b368def295.html "Developer Hub is a central API catalog, allowing application developers to consume APIs and other assets, from a common platform.") :arrow_upper_right:

