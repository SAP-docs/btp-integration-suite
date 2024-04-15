<!-- loiob0d79501fc374254a0dc7f78d39c6d56 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Defining Access Policies

Define an access policy to specify which artifacts are to be protected.



To create and edit access policies, your user must be assigned the role collection *PI\_Administrator*.

For more information about access policies, see [Access Policies](access-policies-e0009f3.md).

Perform the following steps:

1.  Go to the *Manage Security* section and choose the *Access Policies* tile. The list of existing access policies is displayed.

2.  To create a new access policy, choose :heavy_plus_sign: and provide the details as follows:

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
    </table>
    
    The access policy is added to the list.

    You can filter the list by searching in role names and descriptions and sort the list by role name.

3.  Select the access policy from the list, and next to *Artifact References* choose :heavy_plus_sign:.

    Specify the following parameter follows:

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

        Access policies for integration packages and for specific artifact types \(such like integration flows and script collections, for example\) co-exist as described under [Access Policies](access-policies-e0009f3.md).

    -   *Integration Flow*

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
    
    You can create additional artifact references if you like to protect additional artifact types.

4.  Once you have completed the configuration of the artifact references, select *Create*.


To *Edit* or *Delete* an access policy, choose the corresponding item from the *Actions* menu of the respective row.

To *Edit* or *Delete* an artifact reference, choose the corresponding action button of the respective row.

