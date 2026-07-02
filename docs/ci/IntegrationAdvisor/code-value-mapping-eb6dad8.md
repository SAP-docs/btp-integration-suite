<!-- loioeb6dad8fdf6146cb980ee159738d5b16 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Code Value Mapping

Code value mappings represent the transformation of a code value that is set at the source element into a code value that is required at the target element. They're created within a specific MAG, accessible only by a particular node of that MAG, and are stored them as well.

1.  Go to *Design* \> *MAGs* and select the mapping guideline you want to work with, then navigate to the mapping editor.
2.  Draw a mapping line between the **source node** and the **target node**, both associated with the codelist. This action makes the *Code Value Mapping* tab visible.

    Drawing a line between one source node and one target node creates a 1:1 code value mapping, while drawing lines from multiple source nodes to a single target node establishes an n:1 code value mapping. The first source node you select becomes the primary source. The order in which you draw the mapping lines determines their sequence from left to right in the mapping table.


> ### Example:  
> In an n:1 code value mapping, you mapped the source nodes `AddressTypeCode` and `CountryCode` with the target node `AddressType`. The *Code Value Mapping* tab would display a table with three columns: one for each of the two source nodes and one for the target node. The value mappings defined in the tables are processed from top to bottom, ensuring that the most specific rule is applied first during runtime.



<a name="loioeb6dad8fdf6146cb980ee159738d5b16__section_urh_gdg_zfc"/>

## Adding Code Value Mappings

You can either add code value mappings **manually** or **automatically using the proposal** option.



### Manually Add Code Value Mappings

Choose the source node and select *Code Value Mapping*.

To manually add code value mapping entries one by one, choose *Add* \> *One source value*. A new line is added to the table, with the source field being `(any value)` and the target code value left empty, indicating an error state. Complete the configuration to resolve the error.

To add any source values that are not yet included in the list, choose *Add* \> *All remaining primary source values*. This option facilitates mass operations and makes the process more efficient.

Use *Clear* to remove any incomplete entries from the list.

Once you're finished, the tab displays the code values of the source and target node. The *Source Code Value* displays the list of code values selected for the source node and the *Target Code Value* displays the list of code values selected for the target node. You can change the code value in the source and target node by selecting the value help <span class="SAP-icons-V5"></span> and choosing the relevant value from the list.



### Automatically Add Code Value Mappings from Proposal Service

If you've used the proposal service on the entire MAG and added a code value mapping fro the proposals, the *Code Value Mapping* tab shows the *Proposal* option. This only applies if the code value mapping was added from the proposals.

Select the *Proposal* button for both 1:1 and n:1 mappings to display a list of proposals. You can select the necessary proposals from the list and choose *Add*.



<a name="loioeb6dad8fdf6146cb980ee159738d5b16__section_myr_gdg_zfc"/>

## Setting Default Values

By setting default values in code value mappings you ensure reliability in the value transformation in case specific source code values are missing. To set a default value, perform the following steps:

1.  Open a mapping guideline and switch to the tab *Code Value Mapping*.
2.  To set a default value, choose the value help <span class="SAP-icons-V5"></span> and select a default from the list.

    You can only set a default value from the rules other than the ones mentioned in the mapping list and you can also select only the target code values for the default value.

    The options differ depending on the cardinality:

    -   For **1:1 code value mapping**, you can either pass through the source value directly or select any code from the target code list.

    -   For **n:1 code value mapping**, you can either pass through the value from the primary source or select any code from the target code list.


3.  Save your changes.



<a name="loioeb6dad8fdf6146cb980ee159738d5b16__section_fzj_hdg_zfc"/>

## Organizing Code Value Mappings



### Deleting Code Value Mappings

To delete a code value mapping, choose *Delete* at the beginning of each entry. This allows you to remove code value mappings one by one.



### Copy Code Value Mappings to Different Nodes

To copy a value mapping from another mapping element, choose *Copy* and select a value mapping from the list.



### Sort code value mappings

Use the sort code value mapping <span class="BusinessSuiteInAppSymbols-V2"></span> button to reorder the code value mappings. This way, you can ensure that more specific mappings are applied first and thereby increase the accuracy of mapping each source code value to its corresponding target code value.



### Reorder source codelists

Use the reorder source codelists <span class="BusinessSuiteInAppSymbols-V2"></span> button to adjust the source code list. In the *Reorder Source Codelists* dialog box, select the codelist and adjust the order using the up <span class="SAP-icons-V5"></span> and down <span class="SAP-icons-V5"></span> arrows. To confirm the new order, choose *OK*.



<a name="loioeb6dad8fdf6146cb980ee159738d5b16__section_xgx_hdg_zfc"/>

## Resolving Error States

If any of the following entries are present in your mapping, the corresponding rows are marked as an error:

-   Duplicate code value mappings
-   Empty value mappings
-   No target code value selected
-   None of the source code values selected

Make sure that you fix the errors identified by the rules listed above.



<a name="loioeb6dad8fdf6146cb980ee159738d5b16__section_nb5_ldg_zfc"/>

## Switching to Function

A code value mapping is usually made at the semantic level and generated into a transformation \(XSLT\) function once the runtime artifacts are generated.

To convert your code value mapping into a function, choose *Switch to Function*. This automatically generates a corresponding XSLT function for the code value mapping, under the *Functions* tab.

> ### Caution:  
> This action is irreversible. Switching to function deletes the code value mapping.

The generated default XSLT function is based on `<xsl:choose>`, wherein the source code values are compared against a range of possible values. Each selected source code value is expressed by a `<xsl:when>` clause and the mapped target code value in `<xsl:sequence>`. All source code values that aren’t mapped are written into the output, expressed by `<xsd:otherwise>`. You can change the function according to your requirements.



<a name="loioeb6dad8fdf6146cb980ee159738d5b16__section_vq2_mdg_zfc"/>

## Working with Global Mappings



### Create Global Mapping

You can also create a global mapping out of the local code value mapping by choosing *Create Global Mapping*. This global mapping can be used in other mapping guidelines.



### Assign Global Mapping

You can use the following options only if you have used a standard code list or a global code value mapping created out of a custom codelist.

Choose *Assign Global Mapping* if you want to reference a global mapping to that particular code value. Once you assign a global mapping, the existing mapping is overwritten with the global mapping values and a link to the global mapping appears next to code value mapping.

To remove the global mapping, choose *Detach Global Mapping*. This only removes the global mapping reference while the values are retained local to the mapping guideline.



<a name="loioeb6dad8fdf6146cb980ee159738d5b16__section_f2r_ghh_gqb"/>

## Deprecated Code Values

Code values can deprecate, as shown by the icon <span class="SAP-icons-V5"></span>.

Code values can deprecate for the following reasons:

-   The value is still in the codelist but is deselected in the message implementation guideline.
-   The value was removed from or replaced in that particular version of the codelist.
-   The code value is removed from or replaced in the message implementation guideline. In this case, the domain GUID of the missing value is displayed in the MAG.

You can distinguish between these values using the tooltip provided under the <span class="SAP-icons-V5"></span> icon.

If the deprecated values are found under *Source Code Value*, you can delete them using :wastebasket:provided next to each value.

If the deprecated values are found under *Target Code Value*, you can replace them with an existing value using the value help <span class="SAP-icons-V5"></span>.

You can select deselected values again in the respective message implementation guideline.

> ### Note:  
> When you create a global mapping out of a code value mapping that has deprecated values due to any of the above mentioned scenarios, those values aren't added to the newly created global mapping.
> 
> Also, if your global mapping contains any deprecated values, you can now delete those value directly from the global mapping using the delete :wastebasket: icon provided next to them.

