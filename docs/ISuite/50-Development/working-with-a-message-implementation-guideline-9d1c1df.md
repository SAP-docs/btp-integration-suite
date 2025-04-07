<!-- loio9d1c1df6ab184841a3be60e46560da66 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with a Message Implementation Guideline



<a name="loio9d1c1df6ab184841a3be60e46560da66__prereq_jwx_qhr_gcb"/>

## Prerequisites

You have created a message implementation guideline \(MIG\). For more information on creating a new MIG, see [Creating a New Message Implementation Guideline](creating-a-new-message-implementation-guideline-b894de0.md). You have accessed the MIG that you want to work with by creating a new MIG or choosing one from *Message Implementation Guidelines \(MIGs\)* section of SAP Integration Suite home page.



## Context

Once you have created a message implementation guideline, you need to select the fields that are relevant to your scenario and build the MIG accordingly. You can also get proposals from the application on which fields might be most relevant for you based on existing MIGs.

Here are a few considerations to be mindful of before you work with MIG:

-   In the MIG structure, if there is one or more nodes with the checkbox selected, that node is a mandatory element as defined by the original message template.
-   If you want to edit details associated with the nodes like *Name*, *Simple Type Properties*, *Description*, etc., you must select the checkbox associated with the node.
-   You can maintain the qualifier markers if it was defined by the source template. You can also maintain additional markers by selecting an element that can be qualified, editing the property sheet, and maintain the instance by selecting the qualifier values.



## Procedure

1.  Choose *Edit*.

    > ### Note:  
    > Ensure that the MIG you are trying to edit is not locked by other users. The *Locked By* field displays the ID of ths user who's currently editing the MIG. You need to have admin rights to unlock it. To know more about the role, see [Assigning Users for SAP Integration Advisor](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/b5226b95e11b42cd9e257ae6d2b0ee0a.html "") :arrow_upper_right:

2.  Use <span class="SAP-icons-V5"></span> and <span class="SAP-icons-V5"></span> to expand and collapse nodes.

    > ### Tip:  
    > -   If you want to search for specific elements in the MIG, select the column header. This activates a *Filter* where you can manually enter your filter criteria.
    > -   You can right-click on the expand/collapse icon to perform a bulk expand/collapse or select/deselect operation.

3.  Choose *Get Proposals* to activate a proposal indicator that displays which fields might be most relevant for you. This is calculated based on the other available MIGs.

4.  If you want to edit the properties of a node, select the checkbox associated with the node and choose the element. This will open the *Details* pane in which you can view and change the parameters.

    > ### Note:  
    > You can also add or modify additional notes details in the *Notes* tab.
    > 
    > If the data element refers to a codelist, maintain those details in the *Codelist* tab.
    > 
    > To know more on editing these properties, see [Working with a Node](working-with-a-node-518b54f.md)
    > 
    > Refer to the [Terminology & Glossary for SAP Integration Advisor](../terminology-glossary-for-sap-integration-advisor-9c221b4.md) to get an understanding of Qualifier, Notes and Codelist.

5.  Review the *Message Implementation Guideline* by setting a review status, or comparing the MIG

    1.  *Set Review Status* to describe the editing status of a node regarding its properties

    2.  *Compare the structure*, documentation, properties, code values, status and example values of multiple MIGs



**Related Information**  


[Codelists](codelists-a7a84b0.md "A codelist is a collection of acronyms and their meaningful descriptions that provide a common understanding of the code values between business partners, reducing the risks associated with business collaboration.")

[Qualifying Nodes](qualifying-nodes-09be983.md "You can qualify nodes to provide context to the semantically generic elements of your Message Implementation Guideline (MIG).")

[Primitive Data Types](primitive-data-types-72a8e9e.md "Primitive data types are the basic building blocks that you use to define entities or structure types within a MIG.")

[Simulating a Message Implementation Guideline](simulating-a-message-implementation-guideline-42b45c5.md "This chapter shows you how to simulate a message implementation guideline.")

[Versioning a Message Implementation Guideline](versioning-a-message-implementation-guideline-12784f9.md "This chapter covers the lifecycle of a message implementation guideline, the purpose of each status that a MIG goes through and the procedure to activate the MIG.")

