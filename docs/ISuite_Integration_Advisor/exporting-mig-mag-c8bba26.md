<!-- loioc8bba26412d44253b734db432e736203 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Exporting MIG/MAG

You can export a list of message implementation guidelines \(MIG\) or mapping guidelines \(MAG\).



<a name="loioc8bba26412d44253b734db432e736203__section_pyz_csc_4tb"/>

## Procedure

1.  Log in to your application and go to <span class="SAP-icons-V5"></span> Message Implementation Guidelines or :open_book:.

2.  In the overview page, choose *Export* to display the list of MIGs or MAGs available for export.

    To view more details of a MIG/MAG, choose <span class="SAP-icons-V5"></span> More Details under the *Info* column.

    > ### Note:  
    > The *Export* dialog also displays the number of MIGs and MAGs along with the number of versions available in the tenant. If you do a complete content move from one tenant to another, you can compare these numbers between the old and new tenant. This helps you verify if all MIGs and MAGs have been moved successfully without missing anything.

3.  Select the MIG/MAG that you want to export. You can also choose multiple entries from the list.

    > ### Note:  
    > The maximum size limit allowed for exporting MIGs/MAGs is 500 MB. Based on this size, an approximate number of MIGs/MAGs that can be selected per export is displayed on the *Export* dialog box. So, if you want to export all MIGs/MAGs, consider splitting them into multiple export files based on the number displayed.

4.  Use the filter option provided under each column header to search for a particular MIG/MAG. For more information on the filters, see [Filtering MIGs](message-implementation-guidelines-migs-f9f2bab.md#loiof9f2bab3ff3a4d86863199f6531ee695__section_ejb_gxt_d4b) and [Filtering MAGs](mapping-guidelines-mags-42124f4.md#loio42124f465fc0472a8ab0de30aa14edef__section_mags_filter).
5.  Choose *Export* to download the files in the `.zip` format.



<a name="loioc8bba26412d44253b734db432e736203__section_ncn_fpw_pyb"/>

## Exporting a single MIG/MAG

If you want to export only one MIG/MAG, follow the following procedure:

1.  Select and open your MIG/MAG.
2.  Choose <span class="SAP-icons-V5"></span> More Options.
3.  Select *MAG Version \(ZIP\)*/*MIG Version \(ZIP\)* from the list.

    That specific version of the MIG or MAG is downloaded as a `.zip` file.


