<!-- loioa42920e9cfd841cd9be7bfe2de2427b0 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a New Mapping Guideline

Creating a New Mapping Guideline: Use SAP Integration Advisor to create a standard mapping guideline for implementing mapping between systems that adhere to B2B type system standards. Choose MAGs, select source and target MIGs, and review and modify details before creating the guideline.



<a name="loioa42920e9cfd841cd9be7bfe2de2427b0__prereq_z41_qfr_gcb"/>

## Prerequisites

-   You have accessed SAP Integration Suite.



<a name="loioa42920e9cfd841cd9be7bfe2de2427b0__context_thb_1tx_ncb"/>

## Context

A mapping guideline can be used as a source, reference, or guidance, for implementing mapping between systems that adhere to B2B type system standards. You use this procedure to create a new standard mapping guideline.



<a name="loioa42920e9cfd841cd9be7bfe2de2427b0__steps_uhb_1tx_ncb"/>

## Procedure

1.  Choose *MAGs* from the left pane of the application.

2.  In the *Mapping Guidelines* page, Choose *Create*.

3.  Select the MIG that you want to use as the source in your MAG in the *Source MIG* step.

4.  Select the MIG that you want to use as the target in your MAG in the *Target MIG* step.

5.  The *MAG Creation* step displays the following information:

    -   *General Information*: Contains the *Name*, *Version* and *Status* of the MAG. You can edit the name of the MAG here.

    -   *Source and Target MIGs*: Displays the details of the source and target MIGs you chose in the previous steps.
    -   *Documentation*: Contains the *Summary* for the MAG. You can add the summary detail for this field.
    -   *Source Business Context*: Displays the business context details maintained in the source MIG. You can modify this information.
    -   *Target Business Context*: Displays the business context details maintained in the target MIG. You can modify this information.

6.  Choose *Create* after reviewing your choices.

7.  Once created, the newly created MAG will have the label *Base* below its name to distinguish it from the overlay MAGs.


<a name="task_s25_mgn_tcc"/>

<!-- task\_s25\_mgn\_tcc -->

## Create MAG from an existing MAG

Create a new Mapping Guideline by copying an existing Mapping Guideline.



<a name="task_s25_mgn_tcc__steps_j3g_5gn_tcc"/>

## Procedure

1.  In the *Mapping Guidelines* tab, select the <span class="SAP-icons-V5"></span> next to the MAG that you want to copy and choose *Copy*.

2.  The copy functionality has two options:

    1.  *Copy MAG Only*: This option creates only a copy of the MAG.

    2.  *Copy MAG and Referenced MIGs*: This option creates a copy of both the MAG and the MIGs referenced in it.


    Choose an option based on your requirement to copy and create a new MAG.




<a name="task_s25_mgn_tcc__result_qgb_wmr_gcb"/>

## Results

You have successfully created a mapping guideline. For more information on how you can work with a MAG, see [Working with a Mapping Guideline \(MAG\)](working-with-a-mapping-guideline-mag-0803ca6.md).

