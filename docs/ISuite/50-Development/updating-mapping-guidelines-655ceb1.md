<!-- loio655ceb19326d470584b5180884b732ef -->

# Updating Mapping Guidelines

Update a group of mapping guidelines.

You can either update mapping guidelines by **replacing the message implementation guideline \(MIG\)**, or by **replacing the base MAG version in the overlay MAGs**.



<a name="loio655ceb19326d470584b5180884b732ef__section_o4y_vs4_jfc"/>

## Replace MIG in MAGs

In some scenarios, you need to update a message implementation guideline \(MIG\) for a set of mapping guidelines \(MAGs\), for example, by changing the source or target MIG. Instead of manually changing this for each MAG, you can update a set of mapping guidelines.

To update a MAG by replacing the MIG, perform the following steps:

1.  In the MAG overview page, choose *Mass-update MAGs* \> *Replace MIG in MAGs*. The *Update Mapping Guidelines* wizard opens.

2.  In the *Select MAGs* step, select the checkbox of the MAGs that you want to update. You can also use the filter options provided in the screen to search for a particular MAG.
3.  Choose *Next*. The next screen *Select Action and MIG* displays the list of MIGs available in the system for you to choose.
4.  You can choose whether to change the source or target MIG using the radio buttons provided in the screen.
5.  Select the MIG from the list that you want to replace the source/target MIG with and choose *Next*.
6.  The *Compatibility Check* step does a validation check on the MAGs and displays the compatibility check between the MAGs and the MIG that you chose.
7.  The *Compatible* column next to each MAG shows the compatibility check of the MIGs.
8.  Select the MAGs again from the list that you want to update and choose *Apply Changes*.

    > ### Note:  
    > Do not close or leave the browser screen until the update is complete.

9.  A progress bar indicates the progress of the update in the *Results* step. You can also stop the update using the *Stop* button.
10. Once the update is completed, a table displays the result of the MAGs update.
11. The *Additional Info* column provides additional information on the MAG update.
12. Choose *Download* if you want to download the results. The information will be downloaded in the `.xlsx` format.
13. Choose *Close*.



<a name="loio655ceb19326d470584b5180884b732ef__section_sml_ys4_jfc"/>

## Replace Base MAG Version in Overlay MAGs

To update a set of mapping guidelines by replacing the base version in the overlay mapping guidelines, perform the following steps:

1.  In the MAG overview page, choose *Mass-update MAGs* \> *Replace Base MAG Version in Overlay MAGs*. A wizard opens.

2.  In the *Base MAG* step, select the base MAG that you want to update. You can use the search and filter options to search for a particular MAG.

3.  The step *Old Base MAG Version* displays the list of MAG versions available for your base MAG. The column *Overlays* shows the number of overlay MAGs based on each base MAG version.

    Select the base MAG version that you want to replace.

4.  In the step *New Base MAG Version*, select the new MAG version you want to use in your overlay MAGs.

5.  The step *Overlay MAGs* displays all the overlay MAG versions available based on the previously selected old base MAG version. Select the overlay MAGs from the list in which you want to replace the base MAG version and choose *Apply Changes*.

    > ### Note:  
    > Don't close or leave the browser screen until the update is complete.

6.  Finally, in the *Results* step, a progress bar indicates the progress of the update. You can halt the update by choosing *Stop*. Once the update is completed, a table displays the result of the overlay MAGs update.

    To save the results as an .xlsx file, choose *Download*.

    To finish the update, choose *Close*.


