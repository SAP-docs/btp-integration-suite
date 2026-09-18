<!-- loio28a8698ebe7044abb2a633d5da41f247 -->

# Integration Content Migration Agent

This agent helps integration developers migrate custom Java-based mapping artifacts used in SAP Process Integration/Process Orchestration integration scenarios to groovy scripts in Cloud Integration capability of SAP Integration Suite.

While migrating integration scenarios via the migration tooling, this agent generates Groovy script equivalents for supported java mappings, helping accelerate modernization efforts and reduce manual redevelopment activities.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through September 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).



## Context

Many SAP Process Integration/SAP Process Orchestration integration scenarios use java mappings to implement custom transformation and processing logic. Since, Cloud Integration does not support the direct execution of these artifacts, integration developers must adapt their integration flows to supported flow steps.

To simplify this transition, the migration tool provides an AI-assisted migration option that generates Groovy scripts from such java mappings that can be incorporated into integration flows.

> ### Note:  
> Currently, only Java Mapping with single Java class \(entry point\) that extends `AbstractTransformation` is supported including lookup service support.

You can watch a short video to understand the steps: 



## When to Use?

Use this agent when the integration scenarios being migrated have following conditions:

-   Contain java mappings.
-   You want to reduce the effort required to manually recreate custom logic in Groovy.
-   You want to accelerate migration projects while preserving existing business functionality as closely as possible.



## What is Generated?

During migration, the feature generates:

-   Reusable and editable Groovy script equivalents of supported java mappings within a script collection artifact. These groovy script are compatible to groovy 4.x runtime. These follow the [Scripts](scripts-fa29f02.md) design guideline under ensure upgrade readiness and help keep your artifacts ready for future upgrades.
-   A lookup integration flow for java mappings that make external lookup service calls. This lookup integration flow is invoked from the generated scripts via ProcessDirect adapter.

**Limitations**:

-   Multiple Java classes with an entry point, with or without external library dependencies.
-   Single Java class with external library dependencies \(open source, custom, or public libraries\).
-   Custom Adapter Module: Class that extends the Module interface as the entry point.



## Prerequisite

Tenant administrator should enable the Integration Content Migration agent from [Artificial Intelligence Settings page](artificial-intelligence-6a6727c.md).



## Procedure

1.  Follow steps until the [Message Mapping Resources step](standard-approach-1b75b4a.md#loio1b75b4a724ce4a48b914b133dd576ce0__flib) for [Standard Approach](standard-approach-1b75b4a.md) and [Message Mapping Resources step](pipeline-approach-efc40f8.md#loioefc40f8409e9444e8f566591c3aa1d3f__flib) for [Pipeline Approach](pipeline-approach-efc40f8.md).
2.  In the *Java Mapping from ESR* step,

    -   In the *Artifact Package* column, select the integration package to which you want to import the java mapping object.

        > ### Tip:  
        > For ease of re-usability, in the *Artifact Package* column, select more or all integration packages so that you can check for the availability of the java mapping object across all selected packages.

    -   Select the *Import Method* based on your requirement:
        -   *Create with AI*: If you're importing this java mapping artifact for the first time in your tenant.
        -   *Reuse*: If you wish to use the groovy script, which was generated while importing this java mapping during previous migrations.

            > ### Note:  
            > If the selected integration package doesn't contain a relevant java mapping artifact, the method is set to *Create with AI* by default.


    -   Choose the *Script Collection Artifact*.

        > ### Note:  
        > If *Create with AI*is selected as the import method and the selected script collection artifact already contains a migrated groovy script for the java mapping, the script will be overwritten with new content.


    > ### Note:  
    > The unsupported java mappings with supported functions and methods on Cloud Integration are migrated directly using groovy script wrapper. More complex Java mappings might not be supported using groovy script wrapper approach. For more information, see [Migrating Java Mappings](https://help.sap.com/docs/migration-guide-po/migration-guide-for-sap-process-orchestration/migrating-java-mappings?ai=true)

3.  Choose *Next Step*.
4.  Refer to the [Scenario Details step](standard-approach-1b75b4a.md#loio1b75b4a724ce4a48b914b133dd576ce0__iflow) for [Standard Approach](standard-approach-1b75b4a.md) and [Scenario Details step](pipeline-approach-efc40f8.md#loioefc40f8409e9444e8f566591c3aa1d3f__scenario) for [Pipeline Approach](pipeline-approach-efc40f8.md).
5.  In the *Review Step* verify the list of java mappings to be converted into groovy scripts. Only the java mappings with import method *Create* are listed here.

    > ### Remember:  
    > Verify the AI-Generated groovy scripts before usage in the integration flow.




## Results

After migration, java mappings are converted into groovy script artifacts within a script collection artifact. These script invoke a lookup integration flow via ProcessDirect adapter. A lookup integration flow is created for java mappings that make external lookup service calls.

The generated scripts are available for further review, editing, testing, maintenance, and reuse as part of the migrated integration solution.

**Related Information**  


[Artificial Intelligence](artificial-intelligence-6a6727c.md "As a tenant administrator, you can activate and manage artificial intelligence features for your organization. These features allow users to simplify integrations, enhance workflow efficiency, and uncover actionable insights for better decision-making.")

[Migration Tooling](migration-tooling-6061016.md "Understand how to consume the migration tooling and the steps involved in the migration.")

