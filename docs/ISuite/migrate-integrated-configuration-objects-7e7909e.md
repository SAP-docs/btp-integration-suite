<!-- loio7e7909e6ebd44365867a6c611d94083a -->

# Migrate Integrated Configuration Objects

Migrate supported integration artifacts from your SAP Process Orchestration system to SAP Integration Suite as Integration Flows.



<a name="loio7e7909e6ebd44365867a6c611d94083a__prereq_ysx_ncm_y5b"/>

## Prerequisites

-   You've evaluated the migration feasibility for your ICO using Migration Assessment. See: [Create a Scenario Evaluation Request](create-a-scenario-evaluation-request-435ec61.md).

-   You've connected your SAP Process Orchestration System with SAP Integration Suite using SAP BTP destinations. See: [Connecting an SAP Process Orchestration System](connecting-an-sap-process-orchestration-system-4120ecb.md).

-   You've created an integration package in Integration Suite for the purpose of migration. See: [Creating an Integration Package](50-Development/creating-an-integration-package-9126d79.md).




## Procedure

1.  In the integration package that you created, choose *Edit* \> *Migrate*.

    The migration wizard comes up.

2.  In the *Process Orchestration System* tab, select the *Name* of the SAP Process Orchestration system.

    All the systems that are added as a part of [Connecting an SAP Process Orchestration System](connecting-an-sap-process-orchestration-system-4120ecb.md) are listed here.

    Based on your configuration, you see the address of the Integration Directory and ES Repository for the system that you select.

3.  Choose *Connect* to establish a connection to the selected system. Upon successful connection, choose *Next Step*.

4.  In the *Process Orchestration Artifacts* tab, select the *Name* of the ICO that you want to migrate. You can use *Show Filters* to drill down to the correct ICO that you want to select.

    You can use regular expression in any of the filters to locate your ICOs. You can use the character \* to combine multiple search terms.

5.  Choose *Next Step*.

6.  In the *Template* tab, a template that is associated to your ICO is automatically preselected. If there are multiple templates associated, select the template of your choice.

    > ### Note:  
    > If there are no associated templates available and yet the ICO is ready for migration, the migration tooling falls back to the default template. The default template creates a point-to-point integration design; this template doesn't contain the integration scenario or the communication channels from the source ICO.
    > 
    > If a default template was applied, the sender and receiver channels are empty. But the resources from your ICO, like mappings and scripts, are migrated so that you can easily reuse them and create an integration design.
    > 
    > The default template is also available for all ICOs that are ready for migration with one or more supported templates.

    Based on the template that you select, you see a short description that explains what the template contains.

7.  Choose *Next Step*.

8.  In the *Integration Flow* tab, provide a *Name* and *ID* for the integration flow that is about to be created in Integration Suite.

9.  Choose *Review*.

10. In the *Review* tab, check all your entries. If needed, use the *Edit* option for the associated tab to make changes.

11. Choose *Migrate*.

    An integration flow equivalent to the ICO is created. The sender and receiver channels, other flow steps like mappings, and attributes from the ICO are migrated too.

    For the sender and receiver adapter, all their attributes from the ICO are externalized in the newly created integration flow. This design helps you configure the parameters for Integration Suite without having to edit the integration flow.

12. Look out for useful information in the *Migration Success* page.

    In the *Channel Mappings* section, you see the mappings for the sender and receiver channels in this tab. For the sender and receiver adapter types used in the source ICO, you see the equivalent adapter types that the migration tooling creates in the integration flow.

    In the *Next Steps* section, you see information about the manual steps that are required to ensure the integration flow is deployable.




<a name="loio7e7909e6ebd44365867a6c611d94083a__postreq_xdk_3rn_y5b"/>

## Next Steps

-   Though the migration tooling tries to keep information intact, check the configurations of all the components involved in the newly created integration flow. Manually fix the gaps in the integration design, if any.

-   If needed, use the *Configure* option in read-only mode to change the externalized parameters of the sender and receiver adapters.

-   If your source ICO contains an RFC receiver adapter, make sure that you’ve configured the RFC destination in your SAP BTP cockpit. See [Creating an RFC Destination](50-Development/creating-an-rfc-destination-3b55fa7.md).

-   If your source ICO contains a JDBC receiver adapter, make sure that you’ve added the JDBC data source. See [Managing JDBC Data Sources](50-Development/managing-jdbc-data-sources-4c873fa.md).

-   Simulate the integration flow to validate if it works as expected.

-   Check if the security artifacts, like credential name and key alias, that are used in your ICO are rightly configured. Deploy the necessary security artifacts before you deploy the integration flow.

-   Deploy the integration flow.


