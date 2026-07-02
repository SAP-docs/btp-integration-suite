<!-- loio5722493d7b994e50a380916e43304ee4 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Using Functions Without a Source Node Mapping

Create and assign a function to a target leaf node with no corresponding source node mapping.



<a name="loio5722493d7b994e50a380916e43304ee4__prereq_qcb_qwn_d4b"/>

## Prerequisites

-   You've opened the MAG in the edit mode.

-   You've a target leaf node that isn't mapped to any source node or doesn't have any constant value assigned to it.




## Procedure

1.  On the target leaf node, choose *Action Menu* \> *Set Function*.

    A mapping line to the target node with a function icon \(<span class="SAP-icons-V5"></span>\) appears. The *Function* tab of the mapping pane is available with the default code snippet in the *XSLT Code* editor.

2.  On the *Function* tab, in the *XSLT Code* editor, edit the code snippet as required. The scope of the function is local by default. You can also create a function to reuse it across the mapping. For more information, see [Creating a Shared Code](creating-a-shared-code-e951f66.md).

3.  To reuse a function from *Shared Code* in the *XSLT Code* editor:

    1.  Select the *Shared Code* option.

    2.  Choose *Replace*.

    3.  Select the shared code that you want to use from the drop-down list.

    4.  Optional: Choose *Edit* to modify the shared code snippet. The changes are saved globally.


4.  To pass a parameter to a function, perform the following:

    1.  On the *Function* tab, choose *Add new parameter*.

    2.  In the *Create New Function Parameter* dialog box, enter the parameter name in the *Function Parameter Name* field and choose *Create*.

    3.  *Choose a Global Parameter* to bind it to the function parameter. For more information on creating global parameters, see [Defining Global Parameters](defining-global-parameters-62fe053.md).

    4.  Select the required global parameter from the *Global Parameters* list. Alternatively, you can also filter for a parameter using *Search*.


5.  Optional: Select the *Confidential Function Content* option if your code snippet contains any confidential information such as a specific business partner ID or any personal information.

    > ### Remember:  
    > You can choose this option if you don't want your code snippet to be published to the Global Index Server used by the proposal service.

6.  *Save* the changes.


