<!-- loiod6503a577334447282de280c68187647 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Manage Access Policies for Edge Integration Cell

Define access policies to specify which Edge Integration Cell artifacts need protection.



<a name="loiod6503a577334447282de280c68187647__prereq_lwd_pgs_kfc"/>

## Prerequisites

To create and edit access policies, users must have the role collection PI\_Administrator. For more details, see [Access Policies](50-Development/access-policies-e0009f3.md).



## Context

Access policies let you restrict access to selected artifacts and their data. In the *Maintain Access Policies* screen, you can create new access policies and define the set of artifacts protected by these policies. For more information, see [Access Policies](50-Development/access-policies-e0009f3.md).

To manage access policies, go to the *Monitor* section of the SAP Integration Suite. You can find the *Access Policies* tile under *Manage Security*.

You can use the *Runtime* dropdown to view a list of all available policies in your different Edge Integration Cells.

<a name="task_bpq_mcv_lfc"/>

<!-- task\_bpq\_mcv\_lfc -->

## Creating Access Policies



## Procedure

1.  Select *All* from the *Runtime* dropdown menu.

2.  In the *Access Policies* table, choose *Create*.

3.  Enter a name and description for the role in the new dialog box.

    > ### Note:  
    > When creating the associated custom role in your subaccount, make sure that you specify the same string under Values. For more information, see [Creating Custom Roles for Access Policies](50-Development/creating-custom-roles-for-access-policies-7db3c87.md).

4.  Select the runtimes where you want to create the new access policy.

5.  Choose *Create* to confirm the creation of the new access policy. The new policy is automatically added to the list.

    To edit or delete an access policy, choose the corresponding icon from the *Actions* column.

    > ### Note:  
    > You can choose *Edit* in the *Access Policies* table to remove the assigned runtime locations and add new ones.


**Related Information**  


[Defining Access Policies](50-Development/defining-access-policies-b0d7950.md "Define an access policy to specify which artifacts are to be protected.")

<a name="task_am1_rbv_lfc"/>

<!-- task\_am1\_rbv\_lfc -->

## Creating Artifact References



## Procedure

1.  To specify the protection of your artifacts, select the newly created access policy from the *Access Policies* list.

2.  In the *References* table that opens, choose *Create*.

3.  Configure the following parameters:

    **Create Artifact Reference**


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    Enter a name for the artifact reference \(mandatory\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description*
    
    </td>
    <td valign="top">
    
    Enter a description \(optional\).

    > ### Example:  
    > If you choose the operator `Matches`, describe the set of integration flows selected by the regular expression \(such as: integration flows processing data for German employees\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Artifact Type*
    
    </td>
    <td valign="top">
    
    Select an artifact type from the list. The default setting is `Integration Flow`.

    For more information about artifact types, see [Defining Access Policies](50-Development/defining-access-policies-b0d7950.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Attribute* 
    
    </td>
    <td valign="top">
    
    Choose one of the following options:

    -   *Name*

        To define the artifact reference based on the name.

    -   *ID*

        To define the artifact reference based on the technical name or: identifier.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Operator
    
    </td>
    <td valign="top">
    
    -   If you select *Equals*, you must enter the exact name or ID of the integration artifact.
    -   If you select *Matches*, the value has to be a valid Java regular expression \(not available for *Integration Package* type\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Value* \(only when as operator you've selected *Equals*\)
    
    </td>
    <td valign="top">
    
    Enter the *ID*or the *Name* of the integration artifact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Expression* \(only when as operator you've selected *Matches*\)
    
    </td>
    <td valign="top">
    
    Enter a regular expression for *ID* or *Name*.

    > ### Example:  
    > The regular expression `myName.*` translates to: all values starting with `myName`.

    > ### Note:  
    > JMS queues, global variables, and global data stores support only names.


    
    </td>
    </tr>
    </table>
    
4.  After completing the configuration, choose *Create*.

    > ### Note:  
    > You can create additional artifact references to protect more artifact types.


<a name="task_kdw_flm_lfc"/>

<!-- task\_kdw\_flm\_lfc -->

## Replicating Access Policies



<a name="task_kdw_flm_lfc__context_bgg_c2v_lfc"/>

## Context

You can replicate access policies across runtimes, allowing them to coexist in multiple runtimes simultaneously.

To replicate policies, follow these steps:



## Procedure

1.  Select *All* from the *Runtime* dropdown menu.

2.  In the *Access Policies* table, search for the access policy you want to copy into different runtimes.

3.  Choose the :pencil2: edit icon from the policy's *Actions* column.

4.  In the dialog box that appears, open the *Runtimes* dropdown and select one or more runtimes where you want to copy the access policy.

5.  Choose *Update*. In the *Access Policies* table, the *Runtimes* column updates to show the number of runtimes assigned to the policy.

6.  Choose the icon on the *Runtimes* column to check the reconciliation status of your policies. The status can be *Fail*, *Success*, or *Pending*.

    > ### Note:  
    > If the runtime location where you want to replicate access policies is offline, the newly defined access policies are temporarily held back, and only apply to design time artifacts. Once the designated runtime comes back online, the access policies are automatically copied to it. Until this reconciliation at the runtime location is complete, the status in the reconciliation column remains as *Pending*.


**Related Information**  


[Managing Access Policies](50-Development/managing-access-policies-318d107.md "Define access policies to restrict the access to integration artifacts and data processed and stored by them.")

