<!-- loio770f7be8425b4632be84ee0c2ed7f0ad -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working with Codelists

Learn how to work with codelists in message implementation guidelines, edit code values, and assign codelists to leaf nodes.



## Viewing Codelist Details

To view the codelist details, do the following:

1.  In *Design* \> *MIGs*, open a message implementation guideline.
2.  Go to the *Structure* tab.
3.  In the structure, select a node. If there’s a check in the column *Codelist* for that node, a codelist is currently assigned to it.
4.  In the panel next to the structure, go to the *Codelist* tab. Here, you can review the following information:

    -   *Selected Codelist*: View the currently active codelist. There can only be **one active codelist** for a node at a given time, but you can also select none.

        To learn more about changing the codelist or adding more candidates, see [Assigning Codelists to Leaf Nodes](working-with-codelists-770f7be.md#loio770f7be8425b4632be84ee0c2ed7f0ad__section_assign_codelists).

    -   *General Information*: Review details like ID, name, type system, or version.

    -   *Documentation*: View the definition of the codelist.

    -   *Code Values*: View a list of code values of the codelist that are currently used in the MIG.

        To learn more about selecting code values, see [Working with Code Values](working-with-codelists-770f7be.md#loio770f7be8425b4632be84ee0c2ed7f0ad__section_code_values).





<a name="loio770f7be8425b4632be84ee0c2ed7f0ad__section_code_values"/>

## Working with Code Values

In the subsection *Code Values*, you can see which code values of the codelist are currently used in the message implementation guideline.

> ### Note:  
> To work with code values, you must be in edit mode.

To use additional code values in the message implementation guideline, simply select the relevant code value from the list. When searching for a specific code value, narrow down your search by filtering for *Value* \(ID\), *Name*, and/or *Definition*.

The following additional functions are available to you:

-   *Use all code values of the codelist*: To use the codelist as it is, with all values selected, select the checkbox *Use all code values of the codelist*. Alternatively, you can manually select or deselect code values as needed.
-   You can also manually select all code values one by one **without selecting the checkbox** *Use all code values of the codelist*. In that case, you select all the code values without the decision to use the complete codelist as it is.

    Following this behavior has the following consequences, for example, if you migrate your MIG to a new message version and the new version provides more code values:

    -   If you selected *Use all code values of the codelist* in your old MIG, the checkbox is also selected in your migrated MIG, and you benefit from the extended code values.
    -   If you didn't select the checkbox, each code value is migrated by itself, and any new code values stay unselected.

-   *No validation of code values*: If you don't want the extended semantic validation of your MIG to check the value of the field against the code values, select the checkbox *No validation of code values*.

    Use this checkbox if the payload can contain other values beside the code values. If it's selected, the MIG RD XSD won't contain an enumeration for the code values, which means that the semantic validation doesn't check against the code values.

-   To use a code value as an **example value**, choose :heavy_plus_sign:.



<a name="loio770f7be8425b4632be84ee0c2ed7f0ad__section_assign_codelists"/>

## Assigning Codelists to Leaf Nodes

To assign a codelist to a leaf node, or to replace or remove the currently assigned codelist, perform the following steps.



### Prerequisites

-   You’ve opened the message implementation guideline \(MIG\) in edit mode.
-   You've included the leaf node that you want to assign a codelist to in your MIG by selecting it.



### Procedure

1.  In the *Structure* panel, select the leaf node that you want to assign a codelist to.
2.  In the panel that opens, go to the *Codelist* tab.
3.  *Selected Codelist* shows the codelist that's currently used in the MIG, with additional details displayed in the subsection *General Information*. To change the codelist, do one of the following:

    -   Select the desired codelist from the drop-down list, which shows all candidate codelists that you can switch to. To remove a codelist from this drop-down, choose :x:.
    -   To use a codelist that’s not in the drop-down list yet, choose :heavy_plus_sign:. In the upcoming dialog, use one of the following options:

        -   To assign a **MIG codelist** to the leaf node, choose *MIG Codelists*.
        -   To assign a **type system-based codelist** to the leaf node, choose *From Type System* and select the desired type system from the drop-down list, and the desired version from the second drop-down-field, if requested. Upon selecting the type system and version, the list of available codelists is displayed. Choose the needed codelist from the list.
        -   To assign a **codelist from a custom type system**, choose **From Custom Type System** and select the desired custom type system from the drop-down field. Upon selecting the custom type system, the list of available codelists is displayed. Choose the required codelist version from the list.

    -   To remove the active codelist from a leaf node and not assign a new one, select *None*.

    *Selected Codelist* now shows the codelist assigned to the leaf node, if any.

4.  Save the message implementation guideline.

