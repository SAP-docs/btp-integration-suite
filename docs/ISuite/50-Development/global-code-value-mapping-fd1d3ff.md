<!-- loiofd1d3ff10e0f406f95924d5f77c7f6b1 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Global Code Value Mapping

Know more about the *Code Value Mapping* tab in the Mapping Guidelines page.

The *Code Value Mapping* tab displays the list of global code value mappings that can be used in your mapping guideline. You can open a code value mapping to view its source and target code values. You can also create a global code value mapping with both 1:1 and N:1 cardinality. To know more, follow the following procedure:

1.  Login to your application and select the *MAGs* section.

2.  In the *Mapping Guidelines* screen, navigate to the *Code Value Mapping* tab and choose *Create* to create a Global Code Value Mapping. This opens the *Create Code Value Mapping* dialog.

3.  Maintain the following fields for *Source Codelist* :
    -   *Type System*: Select the <span class="SAP-icons-V5"></span> value help for this field. This displays the *Standard* type systems available in the tenant. If you want to use a custom code list, select the *Custom* button and select the custom type system from the list.

    -   *Codelist*: Select the codelist using the <span class="SAP-icons-V5"></span> value help button. The button displays the list of codelists available in the type system that you chose in the previous field.
    -   *Version*: Select a version of the codelist

4.  Choose :heavy_plus_sign: to add after maintaining the fields.
5.  If you want to add more source codelists, you can do so by changing the corresponding values of the fields using the <span class="SAP-icons-V5"></span> value help button and then selecting :heavy_plus_sign:.
6.  Select *Next* and maintain the following fields for *Target Codelist*.
    -   Type System

    -   Codelist
    -   Version

7.  Choose *Next* and in the *Mapping Creation* step, you are provided with a summary of your selection.
8.  You can modify the name of this new global code value mapping and if you want to modify your selection, you can do so using the *Edit* button provided under the *Source Codelist* and *Target Codelist*.
9.  At first, no values appear in the *Code Value Mapping* tab. You can populate it as follows:

    1.  Select a value for the *Default Value* field.

    2.  To add an entry in the code values table, choose *Add* \> *One source value*.

    3.  Add all remaining primary source values. For details, check the *Code Value Mapping* section.

    4.  After maintaining the entries, choose <span class="BusinessSuiteInAppSymbols-V2"></span> Sort to reorder the existing code value mappings. This ensures that more accurate mappings are applied first.

    5.  For n:1 code value mappings: Choose <span class="BusinessSuiteInAppSymbols-V2"></span> Reorder to open a *Reorder Source Codelists* dialog, which allows you to move the order of the source codelists using <span class="SAP-icons-V5"></span> Up and <span class="SAP-icons-V5"></span> Down. Choose *OK* to see your changes reflecting in the code values table.


10. After making the necessary changes, choose *Save*.
11. The *Overview* tab of the code value mapping provides an overview of the source and target codelists. The *References* section displays the list of MAGs wherever the codelist is used.
12. You can also edit the *Name* of the code value mapping.



<a name="loiofd1d3ff10e0f406f95924d5f77c7f6b1__section_bdb_ck4_m1c"/>

## Copying a Global Code Value Mapping

If you want to create a code value mapping from an existing code value mapping:

-   You can open the existing code value mapping and choose *Copy*.

-   In the main *Code Value Mapping* tab, you can select the more options <span class="SAP-icons-V5"></span> button and choose *Copy*.

    > ### Note:  
    > Copying a global code value mapping creates a new *Draft* global code value mapping with version set to 1.0.


