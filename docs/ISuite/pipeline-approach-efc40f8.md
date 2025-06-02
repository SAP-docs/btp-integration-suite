<!-- loioefc40f8409e9444e8f566591c3aa1d3f -->

# Pipeline Approach

Migrate supported integration objects from your on-premise system to SAP Integration Suite as Integration Flows using the pipeline approach.



<a name="loioefc40f8409e9444e8f566591c3aa1d3f__prereq_idw_jf2_s2c"/>

## Prerequisites

-   You've connected your SAP Process Orchestration or SAP Process Integration system with SAP Integration Suite using SAP BTP destinations. See: [Configuring Connectivity to an SAP Process Orchestration System](50-Development/IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).

-   You've evaluated the migration feasibility for your integration object using Migration Assessment. See: [Create a Scenario Evaluation Request](create-a-scenario-evaluation-request-435ec61.md).

-   Message queues are activated. See: [Managing Message Queues](50-Development/managing-message-queues-cdcce24.md). For more information, see [Run an Integration Flow Under Well-Defined Boundary Conditions](50-Development/run-an-integration-flow-under-well-defined-boundary-conditions-f8cf974.md) 
-   You've discovered, copied, and deployed the relevant prepackaged generic integration flows in your design time. See: [Working with Prepackaged Integration Content](50-Development/working-with-prepackaged-integration-content-bd2ed3e.md)
-   You've created an integration package in Integration Suite for the purpose of migration. See: [Creating an Integration Package](50-Development/creating-an-integration-package-9126d79.md).

-   You've understood the [Supported Patterns](supported-patterns-ad867ae.md#loioad867aea1fc749a99abc2cf643c94038) in Migration Tooling.




<a name="loioefc40f8409e9444e8f566591c3aa1d3f__context_pnq_lf2_s2c"/>

## Context

Migrate your integration scenarios from SAP Process Integration and SAP Process Orchestration to Cloud Integration using the [pipeline concept](https://help.sap.com/docs/migration-guide-po/migration-guide-for-sap-process-orchestration/pipeline-concept). For more information, see [Introducing the new pipeline concept in SAP Cloud Integration](https://community.sap.com/t5/technology-blogs-by-sap/introducing-the-new-pipeline-concept-in-cloud-integration/ba-p/13639651) \(SAP Community Blog\).

You can watch a short video to understand the pipeline approach in a nutshell:





## Procedure

1.  In the integration package that you created, choose *Edit* \> *Migrate*.

    The migration wizard comes up.

2.  In the *Process Orchestration System* tab, select the *Name* of the SAP Process Orchestration system.

    All the systems that are added as a part of [Configuring Connectivity to an SAP Process Orchestration System](50-Development/IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md) are listed here.

    Based on your configuration, you see the address of the Integration Directory and ES Repository for the system that you select.

3.  Choose *Next Step*.

4.  In the *Process Orchestration Artifacts* tab, select an *Object Type*. You can use *Show Filters* to drill down to the correct object that you want to select.

    The supported object types are:

    -   *Integrated Configuration* – an object processed on the Java-only runtime of an SAP Process Integration or SAP Process Orchestration system.

    -   *Receiver Determination* – an object supported only in the SAP Process Integration dual-stack installations \(from release 7.31 on dual usage type\) where messages are processed on both the ABAP as well as the Java stack.


5.  In the *Process Orchestration Artifacts* tab, select the *Name* of the object that you want to migrate. You can use *Show Filters* to drill down to the correct object that you want to select.

    You can use regular expression in any of the filters to locate your objects. You can use the character \* to combine multiple search terms.

6.  Choose *Next Step*.

7.  In the *Pattern* tab, a pattern that is associated to your object is automatically preselected.

    > ### Note:  
    > If there are no associated patterns available and yet the object is ready for migration, the migration tooling falls back to the default pattern. The default pattern creates a point-to-point integration design; this pattern doesn't contain the integration scenario or the communication channels from the source object.
    > 
    > If the default pattern was applied, the sender and receiver channels are empty. But the resources from your object, like mappings and scripts, are migrated so that you can easily reuse them and create an integration design.
    > 
    > The default pattern is also available for all object that are ready for migration with a supported pattern.

    Based on the pattern that you select, you see a short description that explains what the pattern is.

8.  By default, *Standard* is selected. Choose *Pipeline* if you prefer to use the pipeline approach. To understand the best approach for your use case, see [Migration Approaches](migration-approaches-9ddb257.md).

    > ### Note:  
    > You can select the Pipeline approach for Point-to-Point Asynchronous, Content-Based Routing, and Recipient List Asynchronous patterns.

9.  Enable *Idempotent Process at Receiver Side* if you want the receiver adapter to identify and ignore any duplicate processing of messages. For more information, see [Define Idempotent Process Call](50-Development/define-idempotent-process-call-84c85d7.md).

    > ### Note:  
    > This is only available if the selected *Pattern* is *Point-to-Point Asynchronous*.

10. Choose *Next Step*.

11. In the *Message Mapping from ESR* tab, select the import method for the message mapping objects that are associated to the leading object.

    > ### Note:  
    > By default, the option *Enable Reusable Message Mapping Artifacts* is enabled to so that you import the message mappings objects from ESR as message mapping artifacts to SAP Integration Suite. This approach helps you to benefit from the advantages of reusable artifacts. See: [Creating Message Mapping as an Artifact](50-Development/creating-message-mapping-as-an-artifact-1d52a7b.md).
    > 
    > If you disable the option, upon successful migration, only the message mapping objects from ESR are imported directly to the integration flow as local resources. Other resources like function library objects and archives are not migrated. In this approach, you must edit a local resource in all places where it's used. If you opt to disable the option, skip the substeps that follow and move to the [next step.](pipeline-approach-efc40f8.md#loioefc40f8409e9444e8f566591c3aa1d3f__flib)

    1.  In the *Artifact Package* column, select the integration package to which you want to import the message mapping object.

        By default, the integration package in which you're triggering the migration is selected.

    2.  Select the *Import Method* based on your requirement.

        -   If the selected integration package doesn't contain a relevant message mapping artifact, the method is set to *Create*.

        -   If the selected integration package already contains message mapping artifacts relevant to the one you're trying to import, the method is automatically set to *Reuse*. Based on your requirements, either select an existing message mapping artifact or change the import method to *Create*.

            The comparison happens based on conditions like name, namespace, and software component version \(SWCV\).


        > ### Tip:  
        > For ease of reusability, in the *Artifact Package* column, select more or all integration packages so that you can check for the availability of the message mapping object across all selected packages.


12. Choose *Next Step*.

13. In the *Message Mapping Resources* tab, identify and appropriately import the dependent resources of the message mapping objects like function library, message and data types, WSDL, and a few more.

    This step is applicable only if you're creating at least one message mapping object in the previous step. If you're reusing all associated message mapping objects in the previous step, skip the substeps that follow and move to the [next step.](pipeline-approach-efc40f8.md#loioefc40f8409e9444e8f566591c3aa1d3f__scenario)

    1.  Enable the option *Import Only Supported Message Mappings* if you like to skip the import of message mapping objects \(and the dependent resources\) that aren't supported by Integration Suite.

        > ### Remember:  
        > By default, the option is disabled letting you import all message mapping objects associated to the leading integration object. By doing so, the unsupported message mapping objects are only partially imported. The specific dependent resources that aren't supported are skipped during the import process.

    2.  For the dependent function library objects associated to the message mapping object, select a Function Libraries artifact in SAP Integration Suite.


14. Choose *Next Step*.

15. In the *Scenario* tab, enter the *Name* for the scenario you are migrating.

    Following details are automatically populated:

    -   *ID* based on the scenario name.
    -   The Runtime is preset as Cloud Integration.
    -   **Sender Details**: Enter the combination of *Sender Component* and *Sender Interface* to be used to create the Alternative Partner in the Partner Directory. The former maps to *Agency* and latter to the *ID* of the Alternative Partner of the partner directory. For more information, see [Managing Partner Directory Entries](50-Development/managing-partner-directory-entries-3d6eee7.md).

        > ### Remember:  
        > -   Scenario name is used to create a partner in the partner directory. If a partner with an identical name already exists, you will need to either rename the scenario or consider deleting the existing partner from the Partner Directory. See: [Managing Partner Directory Entries](50-Development/managing-partner-directory-entries-3d6eee7.md)
        > -   If an alternative partner already exists with the same Sender Component and Sender Interface combination, it indicates that the selected scenario has already been migrated. If you still wish to proceed, you must delete the alternative partner.

        > ### Caution:  
        > Deleting a partner or alternative partner may inadvertently affect other scenarios. Ensure to review all dependencies and assess potential impacts before proceeding with the deletion.

    -   For the JMS receiver adapter, enter a *JMS Queue Name*. The JMS inbound queue for the Integrated Messaging Runtime pipeline is preset to default pipeline `PIPX01`.

        > ### Recommendation:  
        > Use the default pipeline for migration. After the migration, you can update the queue name in your integration flows if you prefer to use another pipeline. See, .

    -   **Inbound Conversion Integration Flow**: This section appears if the integration flow includes message conversion and mapping steps and uses ProcessDirect as both the sender and receiver adapters. Define an endpoint that the preceding integration flow uses to invoke this integration flow.
    -   **Outbound Processing Integration Flow**: An integration flow is created for each combination of receiver and interface. For each combination, define an endpoint that the preceding integration flow uses to invoke the outbound integration flows. Refer [pipeline concept](https://help.sap.com/docs/migration-guide-po/migration-guide-for-sap-process-orchestration/pipeline-concept) for more details.

        > ### Remember:  
        > -   The endpoints are maintained in the generated XSLT. For content-based routing and recipient list migration involving multiple receivers, the XSLT is saved as a Binary Parameter entity in the Partner Directory. For point-to-point asynchronous migrations with a single receiver, it is stored as a String Parameter entity.
        > -   If you modify the endpoints in the scenario-specific integration flows after the migration, you have to manually update the same in the XSLT stored in the corresponding Partner Directory entity.


16. Choose *Review*.

17. In the *Review* tab, check all your entries. If needed, use the *Edit* option for the associated tab to make changes.

18. Choose *Migrate*.

    Multiple integration flows equivalent to the source object are created. The sender and receiver channels, other flow steps like mappings, and attributes from the source object are migrated too.

    For the sender and receiver adapter, only necessary attributes from the source object are externalized in the newly created integration flows. This design helps you configure the parameters for SAP Integration Suite without having to edit the integration flow.

19. Look out for useful information in the *Migration Success* page. Choose *Report* at the top-right corner to download the migration report in PDF format. Also, review the [Known Limitations](known-limitations-of-migration-tooling-7a552d4.md) to understand any potential restrictions.

    In the *Channels and Resources* section, you see the mappings for the sender and receiver channels. For the sender and receiver adapter types used in the source object, you see the equivalent adapter types that the migration tooling creates in the integration flow.

    In the *Next Steps* section, you see information about the manual steps that are required to ensure that the integration flow is deployable.




## Next Steps

-   Though the migration tooling tries to keep information intact, check the configurations of all the components involved in the newly created integration flow. Manually fix the gaps in the integration design, if any.

-   If needed, use the *Configure* option in read-only mode to change the externalized parameters of the sender and receiver adapters.

-   If your source object contains an RFC receiver adapter, make sure that you’ve configured the RFC destination in your SAP BTP cockpit. See [Creating an RFC Destination](50-Development/creating-an-rfc-destination-3b55fa7.md).

-   If your source object contains a JDBC receiver adapter, make sure that you’ve added the JDBC data source. See [Managing JDBC Data Sources](50-Development/managing-jdbc-data-sources-4c873fa.md).

-   Simulate the integration flow to validate if it works as expected.

-   Check if the security artifacts, like credential name and key alias that are used in your source object are rightly configured. Deploy the necessary security artifacts before you deploy the integration flow.

-   If your source integration scenario has a scheduler expression, the same is reset to trigger the message processing of the integration flow every 60 seconds. Modify as per your requirements.

-   Deploy the integration flow.


