<!-- loio084e6f298cad4c468224979063d89b55 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Extract

In this Extract phase, data from the source system in analyzed and prepared for the next step, which is Generation.



## Prerequisites

To get started with migration, ensure that:

-   You've connected your SAP Process Integration/SAP Process Orchestration with SAP Integration Suite using SAP BTP destinations. See: [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md)
-   You've evaluated the migration feasibility for your integration object using Migration Assessment. See: [Create a Scenario Evaluation Request](https://help.sap.com/docs/integration-suite/isuite-migration-assessment/create-scenario-evaluation-request?)
-   You've understood the [Supported Patterns](supported-patterns-6affc1a.md)
-   You've created an integration package in Integration Suite for the purpose of migration. See: [Creating an Integration Package](creating-an-integration-package-9126d79.md)



## Context

An automatic migration of integration scenarios from SAP Process Integration/SAP Process Orchestration to your SAP Integration Suite allows you to modernize your integrations. This migration is done in a two phased approach, Extract and Generate. In the extract phase you identify the SAP Process Integration/SAP Process Orchestration system and choose the artifacts to be migrated.

The extracted data includes structural definitions, mappings, routing logic, and other metadata required to understand how the integration currently behaves.

> ### Note:  
> You can select a maximum of 10 integration scenarios only.



## Procedure

1.  Sign in to your SAP Integration Suite tenant.

2.  Choose *Modernize* \> *Integrations*.

3.  On the *Modernize Integrations* page, under the *Extract* tab, choose *Create* to create a new extraction request.

    The *Extract Scenario* wizard opens.

4.  In the *Define Request* step, enter the *Request Name* for this extraction request. A generation request is later mapped to this extraction request.

5.  Choose *Next Step*.

6.  In the *Process Orchestration System* step, select the *Name* of the SAP Process Integration/SAP Process Orchestration System.

    All the systems that are added as a part of [Configuring Connectivity to an SAP Process Orchestration System](IntegrationSettings/configuring-connectivity-to-an-sap-process-orchestration-system-8c36fd2.md) are listed here.

    Based on your configuration, you see the address of the Integration Directory and ES Repository for the system that you select.

7.  Choose *Next Step*.

8.  In the *Process Orchestration Artifacts* step, select an *Object Type*.

    The supported object types are:

    -   *Integrated Configuration*: An object processed on the Java-only runtime of an SAP Process Integration/SAP Process Orchestration System.

    -   *Receiver Determination*: An object supported only in the SAP Process Integration/SAP Process Orchestration System dual-stack installations \(from release 7.31 on dual usage type\) where messages are processed on both the ABAP as well as the Java stack.


9.  In the *Process Orchestration Artifacts* step, choose <span class="SAP-icons-V5"></span> and select the *Names* of the object that you want to migrate and choose *OK*.

    You can use regular expression in any of the filters to locate your objects. You can use the character \* to combine multiple search terms.

    > ### Note:  
    > You can select a maximum of 10 scenarios.

10. Choose *Review*.

11. In the *Review* step, check all your entries. If necessary, use *Edit* option for the associated tab to make changes.

12. Choose *Extract*.

    The extraction request is added to the *Extraction Request* table. The extraction may take some time, choose <span class="SAP-icons-V5"></span> to refresh the extraction status.

    Following status may appear:

    -   *Completed*: The extraction request is successful and ready to use to for generate step.
    -   *Failed*: The extraction request has failed should be created again.

13. For extraction requests that are in *Completed* status, on the *Actions* column, choose <span class="SAP-icons-V5"></span> and *Generate* to create a subsequent generate request. See [Procedure for Generate](generate-f9100ff.md#loiof9100ff320ea4f3db85e200463b34d76__step6_ERS).




## Results

Once an extraction request is triggered, it is added in the *Extraction Requests* table with following fields:

**Extraction Requests**


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

The name of the extraction request. This name is specified when you create the extraction request and helps you identify it in the list.

</td>
</tr>
<tr>
<td valign="top">

*System*

</td>
<td valign="top">

The source SAP Process Integration/Process Orchestration system from which the integration scenarios are extracted.

</td>
</tr>
<tr>
<td valign="top">

*Created by*

</td>
<td valign="top">

The user who created the extraction request.

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

*Status*

</td>
<td valign="top">

Indicates the current state of the extraction request.

-   *Completed*

-   *Failed*


> ### Note:  
> The extraction might take some time to appear, choose <span class="SAP-icons-V5"></span> to refresh the extraction status.



</td>
</tr>
<tr>
<td valign="top">

*Actions*

</td>
<td valign="top">

For each generation request you can, choose <span class="SAP-icons-V5"></span> and do the following:

-   *Generate*: Only available for the completed requests.

    When this option is chosen the [Generate Wizard](extract-084e6f2.md#loio084e6f298cad4c468224979063d89b55__step_Actions) is launched.

-   *Download Log*: Only available if the request is failed.



</td>
</tr>
</table>

