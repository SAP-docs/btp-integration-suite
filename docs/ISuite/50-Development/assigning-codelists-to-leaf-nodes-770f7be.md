<!-- loio770f7be8425b4632be84ee0c2ed7f0ad -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Assigning Codelists to Leaf Nodes

You can assign codelists to any leaf node of your choice.



<a name="loio770f7be8425b4632be84ee0c2ed7f0ad__prereq_jvs_mlm_fpb"/>

## Prerequisites

-   You’ve opened the message implementation guideline \(MIG\) in edit mode.

-   You've included the leaf node that you want to assign a codelist to in your MIG by selecting it.




## Procedure

1.  In the *Structure* panel, select the leaf node that you want to assign a codelist to.

2.  In the panel that opens, go to the *Codelist* tab.

3.  The field *Selected Codelist* shows the codelist that's currently used in the MIG, with additional details displayed in the subsection *General Information*.

    To change the selected codelist, either select one from the dropdown list, or choose :heavy_plus_sign: to select a codelist through one of the following options:

    -   Choose *MIG Codelists*, if you want to assign a MIG codelist to the leaf node.
    -   Choose *From Type System* and select the desired codelist from the drop-down list, if you want to assign a type system-based codelist to the leaf node.
    -   Choose *From Custom Type System* and select the desired custom type system from the drop-down field nearby. On selecting the custom codelists, the list of available codelists are displayed. Choose the relevant codelist from the list.

    *Selected Codelist* now shows the list of codelists assigned to the leaf node.

    > ### Note:  
    > There can only be one active codelist for a node at any given time and it's the one selected in the drop-down list.

4.  In the subsection *Code Values*, you can see which code values of the codelist are currently used in the MIG.

    To use the codelist as it is, with all values selected, select the checkbox *Use all code values of the codelist*. Alternatively, you can manually select or deselect code values as needed.

    > ### Note:  
    > You can also manually select all code values one by one without selecting the checkbox *Use all code values of the codelist*. In that case, you select all the code values without the decision to use the complete codelist as it is.
    > 
    > This behavior has consequences, for example, if you migrate your MIG to a new message version and the new version provides more code values:
    > 
    > -   If you selected *Use all code values of the codelist* in your old MIG, the checkbox is also selected in your migrated MIG, and you benefit from the extended code values.
    > 
    > -   If you didn't select the checkbox, each code value is migrated by itself, and any new code values stay unselected.

5.  You can search the code values using the following search options:

    1.  *Search*: This is a generic search field

    2.  *ID*: Search for a specific code value ID using this field. You need to enter the exact ID value here for the search to work.

    3.  *Name*: Search for a specific code value using their here. You can enter partial/full name of the code value and the search function provides the results accordingly.

    4.  *Definition*: Search for a specific code value using their definition here. You can enter partial/full definition of the code value and the search function provides the results accordingly.


    To clear the search filters, choose *Reset*.

6.  Optional: Use a code value as an example value by choosing :heavy_plus_sign:.

7.  Optional: Switch between codelists by selecting the desired codelist from the *Selected Codelist* drop-down list.

8.  Optional: Disassociate a codelist from a leaf node by selecting *None* in the *Selected Codelist* drop-down list.


