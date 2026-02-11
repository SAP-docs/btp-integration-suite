<!-- loioed9b52c29bd44d26ad00fcb38afb50ce -->

# Creating Scripts in a Script Collection



<a name="loioed9b52c29bd44d26ad00fcb38afb50ce__prereq_cvp_j2n_npb"/>

## Prerequisites

[Creating a Script Collection](creating-a-script-collection-824bff0.md).



## Procedure

1.  Open your script collection artifact and choose *Edit*.

    The resource pane and editor comes up on the left and right sides respectively.

    The script collection artifact consists of the following tabs:

    -   *Script Collection*: Used to create and update scripts.
    -   *Design Guidelines*: Used to view and execute the design guidelines applicable to this artifact.

2.  In the resource pane, perform one of the following tasks:


<a name="task_tb2_tjn_npb"/>

<!-- task\_tb2\_tjn\_npb -->

## Create a Script



<a name="task_tb2_tjn_npb__steps_z5z_zjn_npb"/>

## Procedure

1.  In the resource pane of the *Script Collection* tab, choose *Create* \> *Groovy Script* or *Create* \> *JavaScript* based on your requirement.

2.  Enter a name for the script resource and choose *Create*.

    A script file with default content gets created.

3.  Choose the script file to open it in the editor.

4.  Make necessary changes to the script file as per your requirement and choose *Save*.


<a name="task_pjc_mkn_npb"/>

<!-- task\_pjc\_mkn\_npb -->

## Upload a Script



<a name="task_pjc_mkn_npb__steps_qjc_mkn_npb"/>

## Procedure

1.  In the resource pane of the *Script Collection* tab, choose *Upload*

2.  Choose one of the following:

    -   *Archive*

    -   *Groovy Script*

        1.  *Script 1.x*

        2.  *Script 2.x*: Groovy script 2.x is a future ready script which uses advanced groovy features and utilizes Groovy runtime 4.0.29. For more information about upgrading scripts from 1.x to 2.x see [Upgrading Groovy Script](upgrading-groovy-script-917e014.md)

            > ### Caution:  
            > -   Ensure that you are upgrading correct versions to avoid any runtime failures.
            > 
            > -   When referencing Groovy scripts in a Groovy Script step, always ensure the selected script version matches the step version, else the step may be upgraded or downgraded automatically. For example, if the Groovy script step version is 1.0 and you select the version 2.x of the script resource, the step will be upgraded and vice versa.


    -   *JavaScript*


3.  In the *Source* list, select one of the following options:

    1.  *File System* – upload a file from your local machine.

    2.  *Integration Flow* – to upload a script file from integration flows in your tenant.

        1.  In the *Package* list, select an integration package of your choice.

        2.  In the *Integration Flow* list, select an integration flow of your choice.

            You see a list of scripts that are used in the selected integration flow.

        3.  Select the scripts that you want and choose *Add*.

        4.  Choose *Save* to keep the changes you made to the script collection.




<a name="task_mvq_vyz_c2c"/>

<!-- task\_mvq\_vyz\_c2c -->

## Improve a Script



## Procedure

1.  On the *Script Collection* tab, choose the script you want to improve from the resource pane.

2.  Include the guidelines highlighted in the *Problems* view to improve your script. For more information, see [Fix Script Incompatibilities](fix-script-incompatibilities-7397c42.md).

    **Related Information**

    [Optimize Groovy Scripts with AI](https://help.sap.com/docs/integration-suite/sap-integration-suite/optimize-groovy-scripts-ai?version=CLOUD)


