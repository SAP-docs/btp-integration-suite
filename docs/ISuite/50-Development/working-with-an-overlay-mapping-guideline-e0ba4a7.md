<!-- loioe0ba4a7d639c4ae382be44c16768e5da -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with an Overlay Mapping Guideline

Learn how to work with an overlay mapping guideline.



<a name="loioe0ba4a7d639c4ae382be44c16768e5da__section_qvh_gqs_32c"/>

## Context

An overlay MAG automatically includes all mapping elements from the underlying Base MAG.

> ### Note:  
> If you change a mapping element in the Base MAG, this change will automatically be considered in all Overlay MAGs \(where this base mapping element is enabled\).



## Procedure

1.  Open your overlay MAG and choose *Edit*.

2.  The *Overview* tab displays the general information you provided at the time of creation such as the name, version, source and target MIGs used in the MAG. The tab also includes a *Base MAG* section, which displays the underlying standard MAG used to create it.

3.  Choose *Mapping* tab to edit the mapping details of the MAG. For more information on mapping nodes, see [Mapping the Source and Target Nodes](mapping-the-source-and-target-nodes-9ea58d6.md).

4.  Overlay MAGs automatically inherit mappings from their base MAG, which are visible in the *Mapping* tab. You can manage the inherited base mappings by choosing to retain or delete them, and also add new mapping elements specific to this overlay MAG. Newly added mapping elements are displayed in green, while inherited elements from the base MAG appear in blue. The following options are applicable when mapping the source and target elements in an overlay MAG:

    1.  **Retain Base Mapping Element**: No action is required if you want to retain a base mapping element. This mapping element will be executed as part of the overlay mapping.

    2.  **Create a new Overlaid Mapping Element**: Drag the field from *Source* to the field on *Target* that you want to map to.

    3.  **Delete a Base Mapping Element**: Simply delete the mapping element in the graphical mapping panel or choose the delete :x: button in the *Action* column of the corresponding element in the *Mapping List* table. The deleted mapping elements will not be executed as part of the overlay MAG.

    4.  **Overwrite a Base Mapping Element**: If you want to replace/overwrite a base mapping element with overlay mapping element, select the existing mapping line and choose *Create Editable Copy*. This will delete the base mapping and allow you to create a new overlay mapping.


5.  You can also use the *Proposal* Service to get a proposal on fields that might be most relevant for you.

    1.  Choose Proposals: Get Proposals to activate a proposal indicator that displays which fields might be most relevant for you. This is calculated based on the other available MAGs.

    2.  Choose Proposals: Select *Best Proposal*to automatically select all proposed mapping entities or select single proposed mapping entities by clicking on the checkboxes within the mapping list.


    The mapping list displays all the relevant information of the source and target nodes such as source nodes, target nodes, their cardinality etc. The *Type* column displays the type of each entry in the mapping list. You can filter and view the mappings that are erroneous and mappings that have proposals using the drop-down filter available above the mapping list table.

6.  You can also search for a particular value in the*Mapping List* tab by selecting the following column headers and entering the search value in the filter <span class="SAP-icons-V5"></span> field.

    -   Source
    -   Source Name
    -   Target
    -   Target Node Name

    This filter option is also available for *Code Value Mapping* tab.

7.  If you want to search for all XSLT snippets and XPath expressions for a certain text pattern and want the list of mapping elements to be filtered by those elements that contain the search pattern, you can use the *Search* field provided above the *Mapping List* table. Use the search field to enter the function pattern and select :mag: . This will display the list of mapping elements pertaining to that function pattern.

8.  You can add or manage additional information or functions about each element by selecting the mapping entity line.

    The mapping also supports various value transformations. To know about these features, see [Value Transformations](value-transformations-19f8374.md)


