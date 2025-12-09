<!-- loio0803ca6cde694cea8daa71c2530c9cbc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with Mapping Guidelines \(MAGs\)

Learn how to work with mapping guidelines, also known as MAGs.



<a name="loio0803ca6cde694cea8daa71c2530c9cbc__prereq_jwx_qhr_gcb"/>

## Prerequisites

-   You've created a mapping guideline \(MAG\). For more information on creating a new MAG, see [Creating Standard Graphical Mapping Guidelines](creating-standard-graphical-mapping-guidelines-a42920e.md).

-   You've opened the MAG that you want to work with, either after creating a new MAG or by choosing one from the *Mapping Guidelines \(MAGs\)* section of the Integration Advisor home page.




<a name="loio0803ca6cde694cea8daa71c2530c9cbc__context_wkr_jtx_ncb"/>

## Context

Once you've created a mapping guideline \(MAG\), you can edit it to change the mapping details to suit your scenario. Additionally, you can also add documentation that provides the users of the MAG with more information on its relevance.

In some scenarios, significant differences between the message implementation guidelines, such as different node hierarchies, difference in the message structure, and so on, can complicate the mapping. To overcome this issue, the application provides you with an approach that helps transform the structure of a source MIG to ensure that its content can be mapped easily with the target MIG structure. To learn more, see [Pretransforming a Message Implementation Guideline](pretransforming-a-message-implementation-guideline-b287e5e.md).



<a name="loio0803ca6cde694cea8daa71c2530c9cbc__steps_xkr_jtx_ncb"/>

## Procedure

1.  Choose *Edit*.

    > ### Note:  
    > Ensure that the MAG you want to edit isn't **locked** by other users. The *Locked By* field displays the ID of the user who's currently editing the MAG. To unlock a MAG, you need admin rights. To learn more about the role, see [Configuring User Access to SAP Integration Suite](../configuring-user-access-to-sap-integration-suite-2c6214a.md).

2.  The *Overview* tab displays the general information that you provided at the time of creation, such as the name, version, source, and target MIGs used in the MAG.

    For standard MAGs, the *Overview* tab includes a *References* section, which lists all overlay MAGs that reference this standard MAG.

3.  In the *Mapping* tab, you can edit the mapping details of the MAG. For more information on mapping nodes, see [Mapping the Source and Target Nodes](mapping-the-source-and-target-nodes-9ea58d6.md).

    -   To create a **mapping**, drag the field from *Source* to the field on *Target* that you want to map to.
    -   You can also use the *Proposal Service* to get a proposal on fields that might be most relevant for you.
        -   Choose Proposals: Get Proposals to activate a proposal indicator that displays which fields might be most relevant for you. This proposal is calculated based on the other available MAGs.
        -   Choose Proposals: Select *Best Proposal* to automatically select all proposed mapping entities or select single proposed mapping entities by clicking on the checkboxes within the mapping list.

    -   The *mapping list* displays all the relevant information of the source and target nodes such as source nodes, target nodes, their cardinality and so on. The *Type* column displays the type of each entry in the mapping list. You can filter and view the mappings that are erroneous and mappings that have proposals using the drop-down filter available above the mapping list table.

    -   To **search** for a particular value in the *Mapping List* tab, select one of the following column headers and enter the search value in the upcoming filter <span class="SAP-icons-V5"></span>.

        -   Source
        -   Source Name
        -   Target
        -   Target Node Name

        This filter option is also available for the *Code Value Mapping* tab.

    -   To **search** for all XSLT snippets and XPath expressions for a certain text pattern and filter the list of mapping elements by those elements that contain the search pattern, use the *Search* field provided above the *Mapping List* table. Enter the function pattern and choose :mag: . This displays the list of mapping elements pertaining to that function pattern.
    -   To **mass validate** all mapping elements that include an XSLT snippet, choose *Validate XSLT Snippets* in the header of the mapping list table. Any mapping element with invalid XSLT snippets is then marked as erroneous in the mapping list. The validation applies to the whole mapping list, independent of any active selection. For more details on the error, check the tool tip in the *Status* column or navigate to the details of the erroneous mapping element.
    -   You can add or manage **additional information or functions** about each element by selecting the mapping entity line.

        The mapping also supports various value transformations. To know about these features, see [Value Transformations](value-transformations-19f8374.md).


4.  In the *Global Parameters* tab, you can declare external parameters that you want to use in your mapping guideline. Before you can consume them during the execution of the mapping guideline, you must fill the parameters outside the mapping, for example, as headers or properties in Cloud Integration.

    > ### Note:  
    > When you create a new global parameter, the value help provides you with the most frequently used parameters from the EDI flow steps of Cloud Integration. These parameters are automatically filled if you either use the EDI Splitter or the EDI Extractor in your integration flow.

5.  Once you've finished editing the mapping guideline, save your changes.


**Related Information**  


[Mapping the Source and Target Nodes](mapping-the-source-and-target-nodes-9ea58d6.md "This topic helps you understand the concepts involved in mapping source and target nodes.")

[Functions](functions-2ea22d0.md "Functions are used to specify a data transformation between source and target nodes.")

[Value Transformations](value-transformations-19f8374.md "These are the special scenarios that you can use while working with an MAG.")

[Simulating a Mapping Guideline](simulating-a-mapping-guideline-b18178b.md "Learn how to simulate a mapping guideline.")

[Versioning a Mapping Guideline](versioning-a-mapping-guideline-1891fea.md "This chapter shows you how to activate a mapping guideline")

