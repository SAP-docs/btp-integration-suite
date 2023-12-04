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
    > Ensure that the MAG you are trying to edit is not locked by other users. The *Locked By* field displays the ID of ths user who's currently editing the MAG. You need to have admin rights to unlock it. To know more about the role, see [Assigning Users for SAP Integration Advisor](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/IAT/en-US/b5226b95e11b42cd9e257ae6d2b0ee0a.html "") :arrow_upper_right:

2.  Choose *Mapping* tab to edit the mapping details of the MAG. For more information on mapping nodes, see [Mapping the Source and Target Nodes](mapping-the-source-and-target-nodes-9ea58d6.md) 

3.  Drag the field from *Source* to the field on *Target* that you want to map to or use the *Proposal Service*.

    1.  Choose Proposals: Get Proposals to activate a proposal indicator that displays which fields might be most relevant for you. This is calculated based on the other available MAGs.

    2.  Choose Proposals: Select *Best Proposal* to automatically select all proposed mapping entities or select single proposed mapping entities by clicking on the checkboxes within the mapping list.


    If you want to search for all XSLT snippets and XPath expressions for a certain text pattern and want the list of mapping elements to be filtered by those elements that contain the search pattern, you can use the *Search* field provided above the *Mapping List* table. Use the search field to enter the function pattern and select :mag: . This will display the list of mapping elements pertaining to that function pattern.

    You can also search for a particular value in the *Mapping List* tab by selecting the relevant column name and entering the search value in the filter <span class="SAP-icons"></span> field. This filter option is also available for *Code Value Mapping* tab.

    You can add or manage additional information about each element in the *Properties* tab. You can also view these details by selecting the element.

    The mapping also supports various value transformations. To know about these features, see [Value Transformations](value-transformations-19f8374.md)

4.  You can add or manage additional information or functions about each element by selecting the mapping entity line.


**Related Information**  


[Mapping the Source and Target Nodes](mapping-the-source-and-target-nodes-9ea58d6.md "This topic helps you understand the concepts involved in mapping source and target nodes.")

[Functions](functions-2ea22d0.md "Functions are used to specify a data transformation between source and target nodes.")

[Value Transformations](value-transformations-19f8374.md "These are the special scenarios that you can use while working with an MAG.")

[Simulating a Mapping Guideline](simulating-a-mapping-guideline-b18178b.md "This chapter shows you how to simulate a mapping guideline.")

[Versioning a Mapping Guideline](versioning-a-mapping-guideline-1891fea.md "This chapter shows you how to activate a mapping guideline")

