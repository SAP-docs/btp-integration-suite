<!-- loiof9100ff320ea4f3db85e200463b34d76 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Generate

This phase allows you to migrate your extracted integration scenarios into integration flows. Based on selected migration patterns, migration approaches, and transformation rules, each scenario is processed and the corresponding target-side configurations and flow definitions are derived.



## Prerequisites

You’ve already extracted the integration scenarios that you wish to migrate. See [Extract](extract-084e6f2.md)



## Context

After the extraction of integration scenarios from SAP Process Integration/SAP Process Orchestration, use the generation phase to finally convert your scenarios into required integration flows to be used in your tenant.

**Migration Approach**: The migration is done using the standard approach. You will be able to create individual integration flows for each of your original integration scenarios easily.

> ### Note:  
> Currently only standard migration approach is supported.

**Usage of Patterns**: The migration tooling analyses a migratable object and maps it with an integration pattern. It's based on these patterns, the migration tooling creates equivalent integration flows in the SAP Integration Suite. To know more about patterns, see: [Supported Patterns](supported-patterns-6affc1a.md).

**Supported Components**: In the current scope, migration tooling supports the migration of objects that contain certain communication channels, flow steps, and events. See: [Supported Components](supported-components-6f05bc0.md).



<a name="loiof9100ff320ea4f3db85e200463b34d76__steps_m5h_dgz_bkc"/>

## Procedure

1.  Sign in to your SAP Integration Suite tenant.

2.  Choose *Modernize* \> *Integrations*.

3.  On the *Modernize Integrations* page, choose *Generate* tab.

    -   Choose *Create* to create a new generation request.

        Alternatively, on the *Extract* tab, for a request with the *Completed* status, on the *Actions* column, choose <span class="SAP-icons-V5"></span> and *Generate* to create a subsequent generate request.


    The *Generate Scenario* wizard opens.

4.  In the *Define Request*step, enter the *Request Name* for this generation request.

5.  Choose the *Extraction Scenario Request* for which you wish to proceed for generation from the drop down.

    > ### Note:  
    > Only requests with *Completed* status can be selected.

6.  Choose *Next Step*.

7.  In the *Pattern and Approach* step, from the list of artifacts extracted during extraction step, choose the artifacts which you wish to proceed for final migration.

8.  Choose the pattern for migration. The pattern that is suited to your object is automatically selected. See [Supported Patterns](supported-patterns-6affc1a.md)

    > ### Note:  
    > -   If there are no associated patterns available and yet the object is ready for migration, the migration tooling falls back to the default pattern. The default pattern creates a point-to-point integration design; this pattern doesn't contain the integration scenario or the communication channels from the source object.
    > -   If the default pattern was applied, the sender and receiver channels are empty. But the resources from your object, like mappings and scripts, are migrated so that you can easily reuse them and create an integration design.
    > -   The default pattern is also available for all object that are ready for migration with a supported pattern.

9.  If the pre-selected pattern is *Point-to-Point Asynchronous*, there are additional options available to better design your integration flow. Use the following options based on your requirements:

    -   -   Decouple the sender and receiver adapters with a JMS queue using the checkbox *Decouple with JMS Queue*. By default, the checkbox is enabled. For more information, see [Decoupling via JMS Queue](decoupling-via-jms-queue-ecbde19.md)
-   Enable *Idempotent Process at Receiver Side* if you want the receiver adapter to identify and ignore any duplicate processing of messages. For more information, see [Define Idempotent Process Call](define-idempotent-process-call-84c85d7.md)


10. In the *Message Mapping from ESR* tab, select the artifact package and import method for the message mapping objects that are associated to the leading object.

    > ### Note:  
    > By default, the option *Enable Reusable Artifacts*is enabled to so that you import the objects from ESR as global artifacts to SAP Integration Suite. This approach helps you to benefit from the advantages of reusable artifacts. See: [Creating Message Mapping as an Artifact](creating-message-mapping-as-an-artifact-1d52a7b.md).
    > 
    > If you disable the option, upon successful migration, only the message mapping and its referenced objects from ESR are imported directly to the integration flow as local resources. Other resources like function libraries and archive objects will be created as global artifacts are not migrated. In this approach, you must edit a local resource in all places where it's used. If you opt to disable the option, skip the substeps that follow and move to the [next step](standard-approach-1b75b4a.md#loio1b75b4a724ce4a48b914b133dd576ce0__flib).

11. In the *Artifact Package* column, select the integration package to which you want to import the message mapping object.

12. Select the *Import Method* based on your requirement.

    -   If the selected integration package doesn't contain a relevant message mapping artifact, the method is set to *Create*.
    -   If the selected integration package already contains message mapping artifacts relevant to the one you're trying to import, the method is automatically set to *Reuse*. Based on your requirements, either select an existing message mapping artifact or change the import method to *Create*.

        The comparison happens based on conditions like name, namespace, and software component version \(SWCV\).


    > ### Tip:  
    > For ease of re-usability, in the *Artifact Package* column, select more or all integration packages so that you can check for the availability of the message mapping object across all selected packages.

13. Choose *Next Step*.

14. In the *Message Mapping Resources* tab, identify and appropriately import the dependent resources of the message mapping objects like function library, message and data types, WSDL, and a few more.

    This step is applicable only if you're creating at least one message mapping object in the previous step. If you're reusing all associated message mapping objects in the previous step, skip the substeps that follow and move to the [next step](generate-f9100ff.md#loiof9100ff320ea4f3db85e200463b34d76__step_i2p_zvj_dkc).

    1.  Enable the option *Import Only Supported Message Mappings* if you like to skip the import of message mapping objects \(and the dependent resources\) that aren't supported by Integration Suite.

        > ### Remember:  
        > By default, the option is disabled letting you import all message mapping objects associated to the leading integration object. By doing so, the unsupported message mapping objects are only partially imported. The specific dependent resources that aren't supported are skipped during the import process.

    2.  For the dependent function library objects associated to the message mapping object, select a Function Libraries artifact in SAP Integration Suite.

        > ### Note:  
        > Both supported and unsupported function libraries can be imported. If any function library is unsupported it will be highlighted in the *Details* column.
        > 
        > On the *Details* column, place the cursor on the row to know why the function library is unsupported.


15. Choose *Reuse Function Libraries* to use the reuse method for all the dependent function library artifacts.

16. Choose *Next Step*.

17. In the *Scenario* step, you'll find the list of artifacts for migration.

    Following details are shown in the *Artifacts for Migration* table.

    -   *Process Orchestration Artifact Name*: Artifact name is auto-populated.

    -   *Scenario Name*: If required you can edit the scenario name.

    -   *Scenario ID*: If required you can edit the scenario ID.

    -   *Package*: Displays the package to which the artifact is assigned. This field is auto-populated, to change the package, choose <span class="SAP-icons-V5"></span> and select the required package form the list.


18. Choose *Review*.

19. In the *Review* step, check all your entries. If needed, use *Edit* option for the associated tab to make the changes.

20. Choose *Generate*.

    A generation request is added in the *Generation Requests* table. The generation may take some time. Choose <span class="SAP-icons-V5"></span> to refresh the generation status.

    Following status could appear:

    -   *Completed*: The generation request is successful and ready to use to for generate step.
    -   *Failed*: The generation request has failed should be created again.

21. For generation requests that are in *Completed* status, on the *Actions* column, choose <span class="SAP-icons-V5"></span> and *Download Report* to get the migration report.

22. For generation requests that are in *Failed* status, on the *Actions* column, choose <span class="SAP-icons-V5"></span> and *Regenerate* to trigger the same request again.

    > ### Note:  
    > A maximum of 2 retries can be done. If the generation still fails, create the request again.




## Results

Once a generation request is triggered, it is added in the *Generation Requests* table with following fields:

**Generation Requests**


<table>
<tr>
<th valign="top">

*Entry*

</th>
<th valign="top">

*Description*

</th>
</tr>
<tr>
<td valign="top">

*Request*

</td>
<td valign="top">

The name of the generation request. This name is specified when you create the generation request and helps you identify it in the list.

</td>
</tr>
<tr>
<td valign="top">

*System*

</td>
<td valign="top">

The source SAP Process Integration/Process Orchestration system associated with the generation request.

</td>
</tr>
<tr>
<td valign="top">

*Created by*

</td>
<td valign="top">

The user who created the generation request.

</td>
</tr>
<tr>
<td valign="top">

*Created on*

</td>
<td valign="top">

The date and time when the extraction request was created.

</td>
</tr>
<tr>
<td valign="top">

*Extraction Request*

</td>
<td valign="top">

The extraction request from which the generation request was created.

</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

Indicates the current state of the generation request.

-   *Completed*

-   *Failed*


> ### Note:  
> The status may take some time to appear, choose <span class="SAP-icons-V5"></span> to refresh the generation status.



</td>
</tr>
<tr>
<td valign="top">

*Actions*

</td>
<td valign="top">

For each generation request you can, choose <span class="SAP-icons-V5"></span> and do the following:

-   *Regenerate*: Only available for the failed requests.
-   *Download Report*: Only available for the completed requests.



</td>
</tr>
</table>

