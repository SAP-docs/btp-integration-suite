<!-- loioba066bbe0f214056a033454a0df918de -->

# Update Properties

Update the Type System version in your agreements.



## Context

*Update Properties* allows you to update the version of a Type System for a group of agreements.

> ### Note:  
> The Type System version can be updated only for agreements that were created using the *Copy* mode.



<a name="loioba066bbe0f214056a033454a0df918de__steps_nxp_wfq_pcc"/>

## Procedure

1.  Login to your application.

2.  Navigate to *Design* \> *B2B Scenarios*.

3.  Choose *Cross Actions* \> *Update Agreements*.

4.  In the *Choose Action* dialog, select *Update Properties*.

5.  Enter a meaningful name in the *Action Name* field.

6.  The *Update Property* field is set to *Type System Version* by default.

7.  Provide a description in the *Description* field and choose *Create*.

8.  In the *Select Agreements* step, you need to select the agreements for which the Type System Version has to be updated. You can filter for a specific agreement using the filter options provided in this step:

    > ### Note:  
    > Choose *Go* without maintaining any filters to view all agreements present in the system.


    <table>
    <tr>
    <th valign="top">

    Field Name
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Agreement Name**
    
    </td>
    <td valign="top">
    
    Allows you to filter agreements based on their name. You can select one or more names from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Agreement Template Name**
    
    </td>
    <td valign="top">
    
    Allows you to filter agreements based on their template name. You can select one or more names from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Binding Mode**
    
    </td>
    <td valign="top">
    
    Set to *Copy* by default. Only agreements created using **Copy** can be modified using this feature.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Trading Partner**
    
    </td>
    <td valign="top">
    
    Allows you to filter agreements based on the trading partner. You can select one or more partners from the drop-down list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Activation Status**
    
    </td>
    <td valign="top">
    
    Allows you to filter agreements based on their activation status. You can select either *Active* or *Draft*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Created By**
    
    </td>
    <td valign="top">
    
    Allows you to filter agreements based on the email address of the user who created the agreement.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Last Modified Date**
    
    </td>
    <td valign="top">
    
    Allows you to filter agreements based on its last modified date.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Type System**
    
    </td>
    <td valign="top">
    
    Select the Type System from the drop-down list for which you need to update the version. This field is mandatory.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Current Type System Version**
    
    </td>
    <td valign="top">
    
    Choose the current version of the selected Type System from the list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Type System Source**
    
    </td>
    <td valign="top">
    
    Choose the Type System source. You have 3 options to choose from:

    -   Company

    -   Partner
    -   Company and Partner


    
    </td>
    </tr>
    </table>
    
9.  After maintaining the necessary filters, choose *Go*.

10. The agreements pertaining to the filter criteria are displayed in the *Agreements* table below the filters.

11. Select the agreements using the checkbox next to their name and choose *Next*.

    If you want to select all the filtered agreements, select the checkbox near the *Name* column header.

12. The next step *Update Type System Version* allows you to select the target Type System version. The version you choose will be applied to all the agreements you chose in the previous step. The fields *Type System* and *Current Type System Version* are auto-filled based on the values you chose in the previous step. Set the target version for the type system from the drop-down list for the field *Target Type System Version* and choose *Next*.

13. The *Review* step displays a summary of all the choices you made in the previous steps. You can modify them again using the *Edit* button provided in each section. Choose *Finish* to complete the update.

14. The *Actions Logs* table displays the progress of your task. Open your log to view the task in detail.


**Related Information**  


[Update MIG Version](update-mig-version-c47533b.md "Update the MIG detail in your Agreement transaction.")

[Import and Export Agreements](import-and-export-agreements-09400a2.md "Import and export Agreements.")

[Activate/Deactivate Agreements](activate-deactivate-agreements-e068e37.md "Activate or deactivate your Agreement transactions.")

