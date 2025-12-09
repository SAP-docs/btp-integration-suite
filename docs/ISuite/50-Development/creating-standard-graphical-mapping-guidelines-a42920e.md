<!-- loioa42920e9cfd841cd9be7bfe2de2427b0 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating Standard Graphical Mapping Guidelines

Use SAP Integration Advisor to create a standard mapping guideline for implementing mapping between systems that adhere to B2B type system standards. Choose MAGs, select source and target MIGs, and review and modify details before creating the mapping guideline.



<a name="loioa42920e9cfd841cd9be7bfe2de2427b0__prereq_z41_qfr_gcb"/>

## Prerequisites

You've accessed SAP Integration Suite.



<a name="loioa42920e9cfd841cd9be7bfe2de2427b0__context_thb_1tx_ncb"/>

## Context

A mapping guideline can be used as a source, reference, or guidance, for implementing mapping between systems that adhere to B2B type system standards. You use this procedure to create a new standard mapping guideline.



<a name="loioa42920e9cfd841cd9be7bfe2de2427b0__steps_uhb_1tx_ncb"/>

## Procedure

1.  Navigate to *Design* \> *MAGs*.

2.  In the *Mapping Guidelines* page, choose *Create* \> *Graphical MAG: Standard*.

3.  In the *Source MIG* step, select the MIG that you want to use as the source in your MAG .

4.  In the *Target MIG* step, select the MIG that you want to use as the target in your MAG.

5.  The *MAG Creation* step displays the following information:

    -   *General Information*: Contains the *Name*, *Version*, and *Status* of the MAG. You can edit the name of the MAG here.

    -   *Source and Target MIGs*: Displays the details of the source and target MIGs you chose in the previous steps.
    -   *Documentation*: Contains the *Summary* for the MAG. You can add the summary detail for this field.
    -   *Source Business Context*: Displays the business context details maintained in the source MIG. You can modify this information.
    -   *Target Business Context*: Displays the business context details maintained in the target MIG. You can modify this information.

6.  Review your choices, then choose *Create*.

    Once created, the newly created MAG has the label *Base* below its name to distinguish it from the overlay MAGs.


<a name="task_s25_mgn_tcc"/>

<!-- task\_s25\_mgn\_tcc -->

## Create MAG from an existing MAG

Create a new mapping guideline by copying an existing mapping guideline.



<a name="task_s25_mgn_tcc__steps_j3g_5gn_tcc"/>

## Procedure

1.  In the *Mapping Guidelines* tab, select <span class="SAP-icons-V5"></span> More Options next to the MAG that you want to copy and choose *Copy*.

2.  Then, choose one of the following copy options, based on your requirements:

    1.  *Copy* \> *Copy MAG Only*: This option creates only a copy of the MAG, reusing the MIGs from the copied MAG.

    2.  *Copy* \> *Copy MAG and Referenced MIGs*: This option creates a copy of both the MAG and the MIGs referenced in it.

    3.  *Copy MAG with MIGs...*: This option creates a copy of the MAG and lets you choose if source MIG, target MIG, or both should be copied as well.


    A new copy of the mapping guidelines opens, and you can work with it right away.




<a name="task_s25_mgn_tcc__result_qgb_wmr_gcb"/>

## Results

You've created a new mapping guideline as a copy of an existing mapping guideline.



## Next Steps

To learn how to work mapping guidelines, see [Working with Mapping Guidelines \(MAGs\)](working-with-mapping-guidelines-mags-0803ca6.md).

To learn how to create overlay mapping guidelines, see [Creating Overlay Graphical Mapping Guidelines](creating-overlay-graphical-mapping-guidelines-3e550b1.md).

