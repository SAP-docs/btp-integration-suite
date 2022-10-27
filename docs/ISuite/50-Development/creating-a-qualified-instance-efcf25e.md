<!-- loioefcf25efce3f4ab6803e4f64d686a8ca -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Qualified Instance

Create and customize a new qualified instance.



<a name="loioefcf25efce3f4ab6803e4f64d686a8ca__prereq_m5m_kkp_gpb"/>

## Prerequisites

-   You've opened the Message Implementation Guideline \(MIG\) in the edit mode.
-   You've selected both the qualifying node and the node that you want to qualify to include them in your MIG.
-   A qualifier marker from the qualifying node to the node that you want to qualify is available in the *Constraint* column. For more information, see the section *Creating Qualifier Markers* below.
-   If you want to use multiple qualifying nodes\(compound qualification\), ensure that the node to be qualified contains more than one qualifier markers.



<a name="loioefcf25efce3f4ab6803e4f64d686a8ca__steps_jgx_hmd_jpb"/>

## Procedure

1.  On the *Structure* tab, select and right-click the node that you want to qualify.

2.  Choose *Qualify Node* from the context menu.

3.  This opens the *Create Qualified Node* dialog box.

    The *Qualifiers* section of the dialog box displays the list of qualifiers.

4.  For Qualifier that is numbered *1*, choose a qualifier marker from the drop-down list under *Selected Qualifier Marker*.

5.  This will display a list of values that are available for the selected qualifier marker. Choose a value from the list by selecting the checkbox.

    You can choose more than one qualifying values from the list. Choosing multiple values means that the node should qualify either of the selected values.

    You can select the checkbox *No Value* if the node is not present in the payload.

6.  You can also add more qualifiers to qualify the node. To do so, the node to be qualified should have more than one qualifier marker. Choose :heavy_plus_sign: . This adds one more qualifier to the *Qualifiers* list.

    The :heavy_plus_sign: button will be disabled if the qualifier contains only one qualifier marker.

    > ### Note:  
    > You can add a maximum of 3 qualifiers to qualify a node.
    > 
    > Adding more qualifiers means the node now has to meet the conditions mentioned in all the qualifiers.
    > 
    > You can disable or enable a qualifier using the toggle button provided next to each qualifier in the list.

7.  Choose the newly added qualifier that is numbered as *2* and perform steps 4 and 5 to add the qualifying values.

8.  Once you have entered the required qualifiers, choose *Add*.

    The qualifier marker arrow turns blue and has the selected qualifier value\(s\). The *Qualifier* tab in the right pane displays the details of the qualification.

    The readable name of the qualifier value is appended to the original name of the qualified node.

9.  Optional: To customize the qualified instance, perform the following:

    1.  Select or deselect the subnodes as required.

    2.  Edit the properties.

    3.  Customize the codelist values assigned to the selected leaf nodes.



