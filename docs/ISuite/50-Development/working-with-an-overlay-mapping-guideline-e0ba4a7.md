<!-- loioe0ba4a7d639c4ae382be44c16768e5da -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with an Overlay Mapping Guideline

Learn how to work with an overlay mapping guideline.



<a name="loioe0ba4a7d639c4ae382be44c16768e5da__section_qvh_gqs_32c"/>

## Context

An Overlay MAG automatically includes all mapping elements from the underlying Base MAG.

> ### Note:  
> If you change a mapping element in the Base MAG, this change is automatically considered in all Overlay MAGs in which this base mapping element is enabled.



## Procedure

1.  Open your overlay MAG and choose *Edit*.

2.  The *Overview* tab displays the general information that you provided at the time of creation such as the name, version, source and target MIGs used in the MAG. The tab also includes a *Base MAG* section, which displays the underlying standard MAG used to create it.

3.  Choose *Mapping* tab to edit the mapping details of the MAG. See [Mapping the Source and Target Nodes](mapping-the-source-and-target-nodes-9ea58d6.md).

4.  Overlay MAGs automatically inherit mappings from their base MAG, which are visible in the *Mapping* tab. You can manage the inherited base mappings by choosing to retain or delete them, and also add new mapping elements specific to this overlay MAG. Newly added mapping elements are displayed in green, while inherited elements from the base MAG appear in blue. The following options are applicable when mapping the source and target elements in an overlay MAG:

    1.  **Retain Base Mapping Element**: No action is required if you want to retain a base mapping element. This mapping element is executed as part of the overlay mapping.

    2.  **Create a new Overlaid Mapping Element**: Drag the field from *Source* to the field on *Target* that you want to map to.

    3.  **Delete a Base Mapping Element**: Simply delete the mapping element in the graphical mapping panel or choose :x: in the *Action* column of the corresponding element in the *Mapping List* table. The deleted mapping elements aren't executed as part of the overlay MAG.

    4.  **Overwrite a Base Mapping Element**: If you want to replace/overwrite a base mapping element with overlay mapping element, select the existing mapping line and choose *Create Editable Copy*. This deletes the base mapping and allow you to create a new overlay mapping.


5.  You can also use the *Proposal* Service to get a proposal on fields that might be most relevant for you.

    1.  Choose Proposals: Get Proposals to activate a proposal indicator that displays which fields might be most relevant for you. This is calculated based on the other available MAGs.

    2.  Choose Proposals: Select *Best Proposal*to automatically select all proposed mapping entities or select single proposed mapping entities by clicking on the checkboxes within the mapping list.


    The mapping list displays all the relevant information of the source and target nodes such as source nodes, target nodes, their cardinality and so on. The *Type* column displays the type of each entry in the mapping list. You can filter and view the mappings that are erroneous and mappings that have proposals using the drop-down filter available above the mapping list table.

6.  You can also search for a particular value in the*Mapping List* tab by selecting the following column headers and entering the search value in the <span class="SAP-icons-V5"></span> Filter.

    -   Source
    -   Source Name
    -   Target
    -   Target Node Name

    This filter option is also available for the *Code Value Mapping* tab.

7.  If you want to search for all XSLT snippets and XPath expressions for a certain text pattern and want the list of mapping elements to be filtered by those elements that contain the search pattern, you can use the *Search* field provided above the *Mapping List* table. Use the search field to enter the function pattern and select :mag: . This displays the list of mapping elements pertaining to that function pattern.

8.  For overlay MAGs, there are search options provided above the mappings table that allow you to filter the mappings in the *Mapping List* table on various criteria:

    1.  *Resultant Mappings*: Displays the mappings that are executed for this overlaid MAG.

    2.  *Overlaid Mappings*: Displays only the mappings created directly within this overlay MAG.

    3.  *Selected Base Mappings*: Displays the selected base MAG mappings inherited by this overlay MAG.

    4.  *Excluded Base Mappings*: Displays the deleted base MAG mappings inherited by this overlay MAG. To restore a deleted base mapping, select the :heavy_plus_sign: button next to the specific mapping.


9.  You can add or manage additional information or functions about each element by selecting the mapping entity line.

    The mapping also supports various value transformations. To learn about these features, see [Value Transformations](value-transformations-19f8374.md)

10. You can combine an Overlay MAG with pretransformation \(PTS\). For this, you have the following options:

    -   **Option 1: Base MAG with PTS and Overlay MAG without PTS**

        If your Base MAG has defined a PTS, the PTS is automatically applied to the Overlay MAG. If you want to use the PTS of the Base MAG unchanged, you don't have to do anything.

    -   **Option 2: Base MAG with PTS and Overlay MAG with modified PTS**

        If your Overlay MAG should execute a different or extended PTS than the Base MAG, create an overlay-specific PTS.

        For the PTS of your Overlay MAG, either create a new \(empty\) PTS or create an editable copy of the PTS of the Base MAG.

        > ### Note:  
        > If your overlay MAG has its own PTS, it always overrules the PTS of the base MAG.

    -   **Option 3: Base MAG without PTS and Overlay MAG with PTS**

        You can create a PTS for your Overlay MAG even if your Base MAG doesn't contain a PTS.

    -   **Option 4: Disable PTS of Base MAG without PTS of Overlay MAG \(Indirectly\)**

        Currently, you can't disable the PTS of the Base MAG without having a PTS in the Overlay MAG. As a workaround, you can create an empty PTS \(PTS without operation\) for your Overlay MAG, which then overrides the PTS of the Base MAG.


    > ### Caution:  
    > If your Overlay MAG uses a different PTS than your Base MAG \(options 2, 3, and 4\), make sure that all the mapping elements you want to reuse from the base MAG are still valid in the context of the overlay MAG.


