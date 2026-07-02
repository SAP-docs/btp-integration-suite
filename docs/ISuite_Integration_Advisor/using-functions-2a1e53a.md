<!-- loio2a1e53a5fd8f4ccbb84fbc79f0c21d32 -->

# Using Functions

Use functions to specify a data transformation between source and target nodes within the Mapping Guidelines \(MAG\) editor.



<a name="loio2a1e53a5fd8f4ccbb84fbc79f0c21d32__prereq_h5k_gtn_d4b"/>

## Prerequisites

-   You've opened the MAG in the edit mode.

-   You've mapped a source leaf node to a target leaf node.




## Procedure

1.  Select the target leaf node that you want to apply the function to.

    The *Function* tab of the mapping pane is available with a default code snippet in the *XSLT Code* editor.

2.  On the *Function* tab, in the *XSLT Code* editor, edit the code snippet as required. The scope of the function is local by default. You can also create a function to reuse it across the mapping. For more information, see [Creating a Shared Code](creating-a-shared-code-e951f66.md).

3.  To reuse a function from *Shared Code* in the *XSLT Code* editor:

    1.  Select the *Shared Code* option.

    2.  Choose *Replace*.

    3.  Select the shared code that you want to use from the drop-down list.

    4.  Optional: Choose *Edit* to modify the shared code snippet. The changes are saved globally.


4.  Choose *Validate* to validate your XSLT code snippet. If there are errors in your code snippet, the validation will display the errors in detail along with the line numbers for easy identification.

    > ### Tip:  
    > Once resolving the errors, re-run the validation to confirm that your code is error-free.

5.  To pass a parameter to a function, perform the following:

    1.  On the *Function* tab, choose *Add new parameter*.

    2.  In the *Create New Function Parameter* dialog box, enter the parameter name in the *Function Parameter Name* field. Choose *Create*.

    3.  *Choose a Global Parameter* to bind it to the function parameter. For more information on creating global parameters, see [Defining Global Parameters](defining-global-parameters-62fe053.md).

    4.  Select the required global parameter from the *Global Parameters* list. Alternatively, you can also filter for a parameter using *Search*.


6.  Optional: Select the *Confidential Function Content* option if your code snippet contains any confidential information such as a specific business partner ID or any personal information.

    > ### Remember:  
    > You can choose this option if you don't want your code snippet to be published to the Global Index Server used by the proposal service.

7.  *Save* the changes.


