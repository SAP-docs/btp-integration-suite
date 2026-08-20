<!-- loio1b75b4a724ce4a48b914b133dd576ce0 -->

# Standard Approach

Migrate supported integration objects from your on-premise system to SAP Integration Suite as Integration Flows via standard approach.



<a name="loio1b75b4a724ce4a48b914b133dd576ce0__prereq_ysx_ncm_y5b"/>

## Prerequisites

-   You've connected your SAP Process Orchestration or SAP Process Integration system with SAP Integration Suite using SAP BTP destinations. See: [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md).

-   You've evaluated the migration feasibility for your integration object using Migration Assessment. See: [Create a Scenario Evaluation Request](https://help.sap.com/viewer/37c02ad991d24d33b1472b00c1a05378/CLOUD/en-US/435ec6196a9f4007910b69bcab90937a.html "Assess your integration scenarios using the information from data extraction requests.") :arrow_upper_right:.

-   You've understood the [Supported Patterns](supported-patterns-ad867ae.md#loioad867aea1fc749a99abc2cf643c94038) in Migration Tooling.

-   You've created an integration package in Integration Suite for the purpose of migration. See: [Creating an Integration Package](creating-an-integration-package-9126d79.md).




## Procedure

1.  In the integration package that you created, choose *Edit* \> *Migrate*.

    The migration wizard comes up.

2.  In the *Process Orchestration System* step, select the *Name* of the SAP Process Orchestration system.

    All the systems that are added as a part of [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md) are listed here.

    Based on your configuration, you see the address of the Integration Directory and ES Repository for the system that you select.

    > ### Note:  
    > When an error occurs, you can download the error log. Include this log when raising a [ticket](http://support.sap.com) on the component LOD-HCI-PI-WT-IFL to get a faster and more accurate resolution.

3.  Choose *Next Step*.

4.  In the *Process Orchestration Artifacts* step, select an *Object Type*. You can use *Show Filters* to drill down to the correct object that you want to select.

    The supported object types are:

    -   *Integrated Configuration* – an object processed on the Java-only runtime of an SAP Process Integration or SAP Process Orchestration system.

    -   *Receiver Determination* – an object supported only in the SAP Process Integration dual-stack installations \(from release 7.31 on dual usage type\) where messages are processed on both the ABAP as well as the Java stack.


5.  In the *Process Orchestration Artifacts* step, select the *Name* of the object that you want to migrate. You can use *Show Filters* to drill down to the correct object that you want to select.

    You can use regular expression in any of the filters to locate your objects. You can use the character \* to combine multiple search terms.

6.  Choose *Next Step*.

7.  In the *Pattern* step, a pattern that is associated to your object is automatically preselected.

    > ### Note:  
    > If there are no associated patterns available and yet the object is ready for migration, the migration tooling falls back to the default pattern. The default pattern creates a point-to-point integration design; this pattern doesn't contain the integration scenario or the communication channels from the source object.
    > 
    > If the default pattern was applied, the sender and receiver channels are empty. But the resources from your object, like mappings and scripts, are migrated so that you can easily reuse them and create an integration design.
    > 
    > The default pattern is also available for all object that are ready for migration with a supported pattern.

    Based on the pattern that you select, you see a short description that explains what the pattern is.


If the preselected pattern is *Point-to-Point Asynchronous*, there are additional options available to better design your integration flow.

8.  Use the following options based on your requirements:

    1.  Decouple the sender and receiver adapters with a JMS queue using the checkbox *Decouple with JMS Queue*. By default, the checkbox is enabled. For more information, see [Decoupling via JMS Queue](decoupling-via-jms-queue-ecbde19.md).

    2.  Enable *Idempotent Process at Receiver Side* if you want the receiver adapter to identify and ignore any duplicate processing of messages. For more information, see [Define Idempotent Process Call](define-idempotent-process-call-84c85d7.md).


9.  Choose *Next Step*.


Handle the dependent message mapping objects and its resources in an efficient way.

10. In the *Message Mapping from ESR* step, select the import method for the message mapping objects that are associated to the leading object.

    > ### Note:  
    > By default, the option *Enable Reusable Artifacts* is enabled so that you import the objects from ESR as global artifacts to SAP Integration Suite. This approach helps you to benefit from the advantages of reusable artifacts. See: [Creating Message Mapping as an Artifact](creating-message-mapping-as-an-artifact-1d52a7b.md). De-selecting this option imports the message mapping as a local resource within the integration flow. This is useful when the message mapping is specific to a particular integration flow and isn't intended for reuse. It also reduces the need to create and maintain additional global artifacts after migration.
    > 
    > If you disable the option, upon successful migration, only the message mapping and its referenced objects from ESR are imported directly to the integration flow as local resources. Other resources like function libraries and archive objects will be created as global artifacts are not migrated. In this approach, you must edit a local resource in all places where it's used. If you opt to disable the option, skip the substeps that follow and move to the [next step](standard-approach-1b75b4a.md#loio1b75b4a724ce4a48b914b133dd576ce0__flib).

    1.  In the *Artifact Package* column, select the integration package to which you want to import the message mapping object.

        By default, the integration package in which you're triggering the migration is selected.

    2.  Select the *Import Method* based on your requirement.

        -   If the selected integration package doesn't contain a relevant message mapping artifact, the method is set to *Create*.

        -   If the selected integration package already contains message mapping artifacts relevant to the one you're trying to import, the method is automatically set to *Reuse*. Based on your requirements, either select an existing message mapping artifact or change the import method to *Create*.

            The comparison happens based on conditions like name, namespace, and software component version \(SWCV\).


        > ### Tip:  
        > For ease of reusability, in the *Artifact Package* column, select more or all integration packages so that you can check for the availability of the message mapping object across all selected packages.


11. Choose *Next Step*.

12. In the *Message Mapping Resources* step, identify and appropriately import the dependent resources of the local or global objects like function library, message and data types, WSDL, and a few more. Refer to the *Target Reference Type* column to understand whether the resource is being imported as a local resource or global. Function Libraries and Imported Archives are always imported as global references.

    For local message mappings, the dependent resources are handled as follows:

    **Resource Handling for Local Message Mappings**


    <table>
    <tr>
    <th valign="top">

    Resource Type
    
    </th>
    <th valign="top">

    Migration Behavior
    
    </th>
    <th valign="top">

    Target Reference Type
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Message Mapping \(MM\)
    
    </td>
    <td valign="top">
    
    Imported into the integration flow
    
    </td>
    <td valign="top">
    
    Local
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    WSDL
    
    </td>
    <td valign="top">
    
    Imported into the integration flow
    
    </td>
    <td valign="top">
    
    Local
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Function Library \(FL\)
    
    </td>
    <td valign="top">
    
    Referenced as an existing artifact
    
    </td>
    <td valign="top">
    
    Global
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Imported Archive \(IA\)
    
    </td>
    <td valign="top">
    
    Referenced as an existing artifact
    
    </td>
    <td valign="top">
    
    Global
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Message Type \(MT\)
    
    </td>
    <td valign="top">
    
    Replaced by the imported local WSDL resource
    
    </td>
    <td valign="top">
    
    Local
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Data Type \(DT\)
    
    </td>
    <td valign="top">
    
    Replaced by the imported local WSDL resource
    
    </td>
    <td valign="top">
    
    Global
    
    </td>
    </tr>
    </table>
    
    This step is applicable only if you're creating at least one message mapping object in the previous step. If you're reusing all associated message mapping objects in the previous step, skip the substeps that follow and move to the [next step](standard-approach-1b75b4a.md#loio1b75b4a724ce4a48b914b133dd576ce0__iflow)

    1.  Enable the option *Import Only Supported Message Mappings* if you like to skip the import of message mapping objects \(and the dependent resources\) that aren't supported by Integration Suite.

        > ### Remember:  
        > By default, the option is disabled letting you import all message mapping objects associated to the leading integration object. By doing so, the unsupported message mapping objects are only partially imported. The specific dependent resources that aren't supported are skipped during the import process.

    2.  For the dependent function library and imported archive objects associated to the message mapping object, select a respective artifact in SAP Integration Suite.

        > ### Note:  
        > Both supported and unsupported function libraries can be imported. If any function library is unsupported it will be highlighted in the *Details* column.
        > 
        > On the *Details* column, place the cursor on the row to know why the function library is unsupported.


13. Choose *Next Step*.

14. In the *Java Mapping from ESR* step, to migrate custom Java-based mapping artifacts, see [AI-based Integration Content Migration](ai-based-integration-content-migration-28a8698.md)

15. In the *Scenario* step, provide a *Name* and *ID* for the integration flow that is about to be created in SAP Integration Suite.

    Following details are automatically populated:

    -   *ID* based on the scenario name.

    -   The Runtime is preset as Cloud Integration.

    -   *Sender Details*: For a *Sender Interface* if the object that is being migrated includes multiple *Sender Components*, each component will be listed here and a *Sender Integration Flow Name* corresponding to each component is created. You can edit the sender integration flow name in this view.


16. Choose *Review*.

17. In the *Review* step, check all your entries. If needed, use the *Edit* option for the associated step to make changes.

    > ### Note:  
    > If you're using AI-based integration content migration feature for java mapping conversion into groovy scripts, verify the AI-Generated groovy scripts before usage in the integration flow.

18. Choose *Migrate*.

    An integration flow that is equivalent to the source object is created. The sender and receiver channels, other flow steps like mappings, and attributes from the source object are migrated too.

    For the sender and receiver adapter, only necessary attributes from the source object are externalized in the newly created integration flow. This design helps you configure the parameters for SAP Integration Suite without having to edit the integration flow.

19. Look out for useful information in the *Migration Success* page. Choose *Report* at the top-right corner to download the migration report in PDF format. Also, review the [Known Limitations](known-limitations-of-migration-tooling-7a552d4.md) to understand any potential restrictions.

    In the *Channels and Resources* section, you see the mappings for the sender and receiver channels. For the sender and receiver adapter types used in the source object, you see the equivalent adapter types that the migration tooling creates in the integration flow.

    In the *Artifact Details* section, you see a list of created scenario-specific integration flows. You also see a list of java lookup integration flows if you've used [AI-based Integration Content Migration](ai-based-integration-content-migration-28a8698.md) feature to convert java mapping to groovy scripts.

    In the *Next Steps* section, you see information about the manual steps that are required to ensure that the integration flow can be deployed.




<a name="loio1b75b4a724ce4a48b914b133dd576ce0__postreq_xdk_3rn_y5b"/>

## Next Steps

-   Though the migration tooling tries to keep information intact, check the configurations of all the components involved in the newly created integration flow. Manually fix the gaps in the integration design, if any.

-   If needed, use the *Configure* option in read-only mode to change the externalized parameters of the sender and receiver adapters.

-   If your source object contains an RFC receiver adapter, make sure that you’ve configured the RFC destination in your SAP BTP cockpit. See [Creating and Modifying RFC Destination](creating-and-modifying-rfc-destination-3b55fa7.md).

-   If your source object contains a JDBC receiver adapter, make sure that you’ve added the JDBC data source. See [Managing JDBC Data Sources](managing-jdbc-data-sources-4c873fa.md).

-   Simulate the integration flow to validate if it works as expected.

-   Check if the security artifacts, like credential name and key alias that are used in your source object are rightly configured. Deploy the necessary security artifacts before you deploy the integration flow.

-   If your source integration scenario has a scheduler expression, the same is reset to trigger the message processing of the integration flow every 60 seconds. Modify as per your requirements.

-   Deploy the integration flow.


