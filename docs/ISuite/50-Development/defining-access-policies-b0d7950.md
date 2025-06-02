<!-- loiob0d79501fc374254a0dc7f78d39c6d56 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Defining Access Policies

Define an access policy to specify which artifacts are to be protected.



<a name="loiob0d79501fc374254a0dc7f78d39c6d56__AccessPolicies_generic"/>

## Context

To create and edit access policies, your user must be assigned the role collection *PI\_Administrator*.

To view and define access policies, go to **Monitor** **\>** **Integrations and APIs** **\>** **Manage Security** and select the **Access Policies** tile.

You can use the *Runtime* dropdown to view a list of all available policies in specific runtimes. For more information about access policies, see [Access Policies](access-policies-e0009f3.md).

To create new access policies, perform the following procedure:



## Procedure

1.  Select *All* from the *Runtime* dropdown menu.

2.  On the *Access Policies* table, choose *Create*.

3.  Provide the following details:

    **Create Access Policy**


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
    
    *Role Name*
    
    </td>
    <td valign="top">
    
    Enter a role name \(mandatory\).

    When creating the associated custom role in your subaccount, make sure that you specify the same string under *Values* \(see [Creating Custom Roles for Access Policies](creating-custom-roles-for-access-policies-7db3c87.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description*
    
    </td>
    <td valign="top">
    
    Enter a description for the role specified \(optional\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Runtimes*
    
    </td>
    <td valign="top">
    
    Select the runtime where you want to create a new access policy.
    
    </td>
    </tr>
    </table>
    
4.  Choose *Create*. The access policy is added to the list.

    You can filter the list by searching role names and descriptions, and sort the list by role name. To *Edit* or *Delete* an access policy, choose the corresponding icon on the *Actions* column.

5.  Select the access policy from the list to manage the policy’s artifact references.

6.  On the *References* table, choose *Create*.

7.  Provide the following parameters:

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

    Example:

    If you choose the operator `Matches`, describe the set of integration flows selected by the regular expression \(such as: integration flows processing data for German employees\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Artifact Type*
    
    </td>
    <td valign="top">
    
    Select an artifact type from the list. The default setting is `Integration Flow`.

    There are the following options:

    -   *Integration Package*

        Select to protect all artifacts of a certain integration package \(by selecting the *Integration Package* artifact type\). If you define an artifact reference for a specific integration package, all artifact types are covered.

        Access policies for integration packages and for specific artifact types \(such as integration flows and script collections\) co-exist as described under [Access Policies](access-policies-e0009f3.md).

        > ### Note:  
        > Some artifacts in a package can have pre-existing access policies at the artifact level. To ensure continuity of service, the current action doesn't affect these pre-existing access policy protections. Consider manually cleaning up any existing access policies before creating a new one at the package level.

    -   *Integration Flow*

    -   *API*

    -   *OData API*

    -   *REST API*

    -   *SOAP API*

    -   *Script Collection*

    -   *Value Mapping*

    -   *Message Mapping*

    -   *Message Queue*

    -   *Global Data Store* 

    -   *Global Variable*

    -   *Data Type*

    -   *Message Type*


    > ### Note:  
    > To protect the content of local data stores or local variables, you need to define an access policy for the integration flow associated with the local data store or variable \(using the *Integration Flow* artifact type\). Global data stores and global variables must be protected by the artifact types *Global Data Store* and *Global Variable* respectively. For more information, see [Access Policies Examples](access-policies-examples-f1dc1a7.md).


    
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

    > ### Note:  
    > Example:
    > 
    > The regular expression `myName.*` translates to: all values starting with `myName`.

    > ### Note:  
    > JMS queues, global variables, and global data stores support only names.


    
    </td>
    </tr>
    </table>
    
8.  Once the configuration is completed, choose *Create*. You can create additional artifact references if you want to protect additional artifact types.

    To *Edit* or *Delete* an artifact reference, choose the corresponding icon on the *Actions* column.


<a name="task_kdw_flm_lfc"/>

<!-- task\_kdw\_flm\_lfc -->

## Replicating Access Policies



## Context

You can replicate access policies across runtimes, allowing them to coexist in multiple runtimes simultaneously.

To replicate policies, follow these steps:



## Procedure

1.  Select *All* from the *Runtime* dropdown menu.

2.  In the *Access Policies* table, search for the access policy you want to copy into different runtimes.

3.  Choose the :pencil2: edit icon from the policy's *Actions* colunm.

4.  In the dialog box that appears, open the *Runtimes* dropdown and select one or more runtimes where you want to copy the access policy.

5.  Choose *Update*. In the *Access Policies* table, the *Runtimes* column updates to show the number of runtimes assigned to the policy.

6.  Choose the icon on the *Runtimes* column to check the reconciliation status of your policies. The status can be *Fail*, *Success*, or *Pending*.

    > ### Note:  
    > If the runtime location where you want to replicate access policies is offline, the newly defined access policies are temporarily held back, and only apply to design time artifacts. Once the designated runtime comes back online, the access policies are automatically copied to it. Until this reconciliation at the runtime location is complete, the status in the reconciliation column remains as *Pending*.


