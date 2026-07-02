<!-- loio27a02167317547fdbfbb654a31d5d4ae -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Externalized Parameters View

Use this view to compare the default and configured values of the integration flow. The advantage of this view is that you can see the consolidated view of all parameter values externalized.



## Context

The integration developer uses this externalized parameter view to compare the default and configured values for quality assurance.

Default values of parameters can be updated from the *Externalized Parameters* view and the configured value displayed in the read-only fashion.

> ### Note:  
> Modifying the default value of a parameter replaces the current value at all locations. Configured values are always preceded by the default value. Select *Configure* option if any changes are required to the configured value.

This view offers two more options. You can use `Filter by Name/Value` option to filter externalized parameter values either by entering name or by values.

You can use *Remove Used* option to remove unused externalized parameters. This option allows you to permanently remove the parameters that aren’t consumed by any components of an integration flow.

For more information, see [Externalize Parameters of an Integration Flow](externalize-parameters-of-an-integration-flow-45b2a07.md).



<a name="loio27a02167317547fdbfbb654a31d5d4ae__steps_cpw_nfs_hkb"/>

## Procedure

To view and edit externalized parameters, perform the following steps:

1.  Choose the *Externalized Parameters* tab from the *Integration Flow* section, and the table displays all the used and unused externalized parameters.

2.  You can search for and modify the parameter values and description. Choose the <span class="SAP-icons-V5"></span> icon to modify the description. If an icon is not visible, it indicates that no description has been defined for that parameter. Switch to the *Edit* mode of integration flow to define the description.



3.  Choose *Save* to save all your changes.


