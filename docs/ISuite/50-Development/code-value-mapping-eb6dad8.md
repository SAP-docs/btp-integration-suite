<!-- loioeb6dad8fdf6146cb980ee159738d5b16 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Code Value Mapping

Code value mappings represent the transformation of a code value that is set at the source element into a code value that is required at the target element. The strings for each element could be different, but the semantics and definition of both the elements should be the same.

The *Code Value Mapping* tab appears only if both the source and target elements in a mapping have code values. The proposal service of MAG provides a proposal of the mapped code values in the target structure. You can also change the proposal or add code value mappings based on your requirement following the steps below.

> ### Note:  
> Code Value Mapping allows you to only map between pre-defined sets of values and it does not support mapping a non-value. If you want to use your own implementation, it is recommended to create an XSLT code. To know more, see [Functions](functions-2ea22d0.md).

1.  Choose the source node and select *Code Value Mapping*.

    The tab displays the code values of the source and target node. The *Source Code Value* displays the list of code values selected for the source node and the *Target Code Value* displays the respective code values by the proposal service.

2.  If you want to copy a value mapping from another mapping element, choose *Copy* and select a value mapping from the list.
3.  A code value mapping is usually made at the semantic level and generated into a transformation \(XSLT\) function once the runtime artifacts are generated. But if you need to convert your code value mapping into a function, choose *Switch to Function*. This automatically generates a corresponding XSLT function for the code value mapping, under the *Functions* tab.

    This action cannot be reversed. Switching to function will delete the code value mapping.

    The generated default XSLT function is based on `<xsl:choose>`, wherein the source code values are compared against a range of possible values. Each selected source code value is expressed by a `<xsl:when>` clause and the mapped target code value in`<xsl:sequence>`. All source code values that aren’t mapped are written into the output, expressed by `<xsd:otherwise>`. You can change the function according to your requirements.

4.  You can change the code value in the target node by selecting the value help <span class="SAP-icons-V5"></span> and choosing the relevant value from the list.

You can use the following options only if you have used a standard code list or a global code value mapping created out of a custom codelist.

1.  Choose *Assign Global Mapping* if you want to reference a global mapping to that particular code value.

    Once you assign a global mapping, the existing mapping will be overwritten with the global mapping values and a link to the global mapping appears next to *Code Value Mapping*. If you want to remove the global mapping, then choose*Detach Global Mapping*. This will only remove the global mapping reference and the values will be retained local to the mapping guideline.

2.  You can also create a global mapping out of the local code value mapping by choosing *Create Global Mapping*. This global mapping can be used in other mapping guidelines.



<a name="loioeb6dad8fdf6146cb980ee159738d5b16__section_wry_mmf_tyb"/>

## N:1 Code Value Mapping

The code value mapping now supports N:1 mapping cardinality. You can map more than one source node with a target node for both local and global code value mapping.

> ### Note:  
> You can create a global code value mapping out of a N:1 local code value mapping.
> 
> You can also assign a global code value mapping to this mapping.

1.  Once the mapping is set, the *Code Value Mapping* tab appears with the following details.

2.  The *Default Value* field allows you to set a default value for the mapping in case no mapping values are matched for the target code value. Select the value help <span class="SAP-icons-V5"></span> and set a default from the list. You can only set a default value from the rules other than the ones mentioned in the table below and you can also select only the target code values for the default value.
3.  The table displays the source code values from left to right in the top-down order of the source MIG node.The target code values are displayed at the rightmost-end of the table.

    Let us take for example, you have mapped the source nodes `AddressTypeCode` and `CountryCode` with the target node `AddressType`. The *Code Value Mapping* tab would display a table with three columns - two for each source node and one for the target node.

4.  You can now start setting the code values using the value help <span class="SAP-icons-V5"></span> button provided for each entry in the table.

    > ### Note:  
    > If the following entries are present in your mapping, the corresponding rows will be marked as an error:
    > 
    > -   Duplicate code value mappings
    > 
    > -   Empty value mappings
    > -   No target code value selected
    > -   None of the source code values selected

5.  Choose the Add :heavy_plus_sign: button provided above the table to add more code values.
6.  The sort code value mapping <span class="BusinessSuiteInAppSymbols-V2"></span> button reorders the code value mappings to ensure that more specific mappings are applied first thereby increasing the accuracy of mapping each source code value to its corresponding target code value.
7.  The reorder source codelists <span class="BusinessSuiteInAppSymbols-V2"></span> button allows you to adjust the source code list. Select the button and in the *Reorder Source Codelists* dialog box, select the codelist and adjust the order using the up <span class="SAP-icons-V5"></span> and down <span class="SAP-icons-V5"></span> arrows and choose *OK*.
8.  If you had applied the *Proposal* service and then tried 1:1 code value mapping, the proposals are automatically applied to the target code values. In case of N:1 code value mapping, the proposals are not applied automatically. You need to choose the *Proposal* option provided under the *Code Value Mapping* tab to apply proposals on the code values.

    > ### Note:  
    > The *Proposal* option appears under the *Code Value Mapping* tab only if you have used the Proposal service on the entire MAG and there are value mappings proposed for this code value mapping.

9.  Selecting the *Proposal* button for N:1 mapping displays the list of proposals. You can select the necessary proposals from the list and choose *Add*.



<a name="loioeb6dad8fdf6146cb980ee159738d5b16__section_f2r_ghh_gqb"/>

## Deprecated Code Values

The <span class="SAP-icons-V5"></span> icon next to a code value denotes that the code value is deprecated.

A deprecated code value occurs when

1.  The value is still in the codelist but is deselected in the message implementation guideline.

2.  The value gets removed or replaced from that particular version of the codelist.
3.  The code value is removed or replaced from the message implementation guideline. In this case, the domain GUID of the missing value is displayed in MAG.

You can distinguish between these values using the tooltip provided under the <span class="SAP-icons-V5"></span> icon.

If the deprecated values are found under *Source Code Value*, you can delete them using :wastebasket:provided next to each value.

If the deprecated values are found under *Target Code Value*, you can replace them with an existing value using <span class="SAP-icons-V5"></span>.

For the deselected values, you can select them again in the respective message implementation guideline.

> ### Note:  
> When you create a global mapping out of a code value mapping that has deprecated values due to any of the above mentioned scenarios, then those values will not be added to the newly created global mapping.
> 
> Also, if your global mapping contains any deprecated values, you can now delete those value directly from the global mapping using the delete :wastebasket: icon provided next to them.

