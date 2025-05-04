<!-- loio0803ca6cde694cea8daa71c2530c9cbc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with a Mapping Guideline \(MAG\)



<a name="loio0803ca6cde694cea8daa71c2530c9cbc__prereq_jwx_qhr_gcb"/>

## Prerequisites

You've created a mapping guideline \(MAG\). For more information on creating a new MAG, see [Creating a New Mapping Guideline](creating-a-new-mapping-guideline-a42920e.md). You've accessed the MAG that you want to work with by creating a new MAG or choosing one from *Mapping Guidelines \(MAGs\)* section of Integration Advisor home page.



<a name="loio0803ca6cde694cea8daa71c2530c9cbc__context_wkr_jtx_ncb"/>

## Context

Once you've created a mapping guideline \(MAG\), you can edit it to change the mapping details to suit your scenario. Additionally, you can also add documentation that provides the users of the MAG with more information on its relevance.

There could be scenarios where there are significant differences between the Message Implementation Guidelines such as different node hierarchies, difference in the message structure etc., that mapping in such cases get difficult. To overcome this, the application provides you with an approach that helps transform the structure of a source MIG to ensure its content can be mapped easily with the traget MIG structure. To know more, see [Pretransformation of a Message Implementation Guideline](pretransformation-of-a-message-implementation-guideline-b287e5e.md) 



<a name="loio0803ca6cde694cea8daa71c2530c9cbc__steps_xkr_jtx_ncb"/>

## Procedure

1.  Choose *Edit*.

    > ### Note:  
    > Ensure that the MAG you are trying to edit is not locked by other users. The *Locked By* field displays the ID of ths user who's currently editing the MAG. You need to have admin rights to unlock it. To know more about the role, see [Configuring User Access to SAP Integration Suite](../configuring-user-access-to-sap-integration-suite-2c6214a.md)

2.  The *Overview* tab displays the general information you provided at the time of creation such as the name, version, source and target MIGs used in the MAG.

3.  Choose *Mapping* tab to edit the mapping details of the MAG. For more information on mapping nodes, see [Mapping the Source and Target Nodes](mapping-the-source-and-target-nodes-9ea58d6.md) 

4.  Drag the field from *Source* to the field on *Target* that you want to map to.

5.  You can also use the *Proposal Service* to get a proposal on fields that might be most relevant for you.

    1.  Choose Proposals: Get Proposals to activate a proposal indicator that displays which fields might be most relevant for you. This is calculated based on the other available MAGs.

    2.  Choose Proposals: Select *Best Proposal* to automatically select all proposed mapping entities or select single proposed mapping entities by clicking on the checkboxes within the mapping list.


    The mapping list displays all the relevant information of the source and target nodes such as source nodes, target nodes, their cardinality etc. The *Type* column displays the type of each entry in the mapping list. You can filter and view the mappings that are erroneous and mappings that have proposals using the drop-down filter available above the mapping list table.

6.  You can also search for a particular value in the *Mapping List* tab by selecting the following column headers and entering the search value in the filter <span class="SAP-icons-V5"></span> field.

    -   Source
    -   Source Name
    -   Target
    -   Target Node Name

    This filter option is also available for *Code Value Mapping* tab.

7.  If you want to search for all XSLT snippets and XPath expressions for a certain text pattern and want the list of mapping elements to be filtered by those elements that contain the search pattern, you can use the *Search* field provided above the *Mapping List* table. Use the search field to enter the function pattern and select :mag: . This will display the list of mapping elements pertaining to that function pattern.

8.  To mass validate all mapping elements that include an XSLT snippet, choose *Validate XSLT Snippets* in the header of the mapping list table. Any mapping element with invalid XSLT snippets is then marked as erroneous in the mapping list. The validation applies to the whole mapping list, independent of any active selection. For more details on the error, check the tool tip in the *Status* column or navigate to the details of the erroneous mapping element.

9.  You can add or manage additional information or functions about each element by selecting the mapping entity line.

    The mapping also supports various value transformations. To know about these features, see [Value Transformations](value-transformations-19f8374.md)


**Related Information**  


[Mapping the Source and Target Nodes](mapping-the-source-and-target-nodes-9ea58d6.md "This topic helps you understand the concepts involved in mapping source and target nodes.")

[Functions](functions-2ea22d0.md "Functions are used to specify a data transformation between source and target nodes.")

[Value Transformations](value-transformations-19f8374.md "These are the special scenarios that you can use while working with an MAG.")

[Simulating a Mapping Guideline](simulating-a-mapping-guideline-b18178b.md "This chapter shows you how to simulate a mapping guideline.")

[Versioning a Mapping Guideline](versioning-a-mapping-guideline-1891fea.md "This chapter shows you how to activate a mapping guideline")

