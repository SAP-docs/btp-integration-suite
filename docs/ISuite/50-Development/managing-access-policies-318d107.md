<!-- loio318d107538644d1483c49eb97542b8da -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing Access Policies

Access Policies let you restrict the access to integration artifacts and their associated data.



<a name="loio318d107538644d1483c49eb97542b8da__section_f4d_sqx_4pb"/>

## Access Policies

In SAP Integration Suite, user permissions are granted in such a way that all tasks can be performed on all artifacts and data. Access policies provide a way to restrict access to selected artifacts and their data.

The access policies are consumed in the design and runtime of integration artifacts. The scope includes the protection of:

-   Integration flows, API-based integration artifacts, message mappings, value mappings, and script collection artifacts in designer – restrict creation and upload of artifacts. Also, restrict the actions edit, copy, download, delete, and simulate existing artifacts.

    > ### Remember:  
    > With access policies in place, an unauthorized user is still allowed to view a protected resource.

-   Integration flows, API-based integration artifacts, message mappings, value mappings, and script collection artifacts at a package level – restrict create, edit, upload and configure artifacts. Also, restrict the actions export, publish, or delete the package if access to at least one artifact is restricted.

-   Integration packages – restrict importing a package and copying a package from *Discover* view to the *Design* workspace.

-   All processing of integration artifacts – business data collected or created during the execution of all integration artifacts. That is, restrict the access to the `Message Processing Log Attachments`, `Trace Data`, data in the JMS queues, data stores, and variables.

-   All integration artifacts from the excecution of the following operations: deploy and undeploy, restart, download, log level change and configure archiving.

The scope of the access policy applies to accessing the resources via web UI and APIs. Restrictions other than the access to business data are provided only on a "separation of concerns" level.

> ### Remember:  
> If the access to a particular resource is restricted because of access policies, you're notified via a specific error message displayed on the screen.

To restrict access via access policies, proceed as follows.



> ### Note:  
> You can also retrieve access policies \(read and write operations\) by an OData V2 application programming interface \(API\). You find the API and its documentation on SAP Business Accelerator Hub at: [Security Content](http://help.sap.com/disclaimer?site=https%3A%2F%2Fapi.sap.com%2Fapi%2FSecurityContent%2Fresource).



<a name="loio318d107538644d1483c49eb97542b8da__section_wr5_5b2_v4b"/>

## Create an Access Policy

> ### Note:  
> To manage access policies, you must have the Administrator role.

1.  Go to the *Manage Security* section and choose the *Access Policies* tile. The list of existing access policies is displayed.

2.  To create a new access policy, choose :heavy_plus_sign: and provide the details as follows:

    **Create Access Policy.**


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
    
    Enter a role name \(mandatory\). The role name is the name of a custom role that you've to create in your subscriber account.
    
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
    
3.  Refresh the content to see the new access policy. You can filter the list by searching in role names and descriptions, and sort the list by role name.

4.  To add *Artifact References* to a specific access policy, select the access policy from the list, and choose :heavy_plus_sign:. Provide the details as mentioned in the table that follows:

    **Create Artifact References.**


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
    
    Enter an artifact name \(mandatory\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description*
    
    </td>
    <td valign="top">
    
    Enter an artifact description \(optional\), which isn’t necessarily the description of the artifact: if you choose the operator `Matches`, describe the set of artifacts selected by the regular expression \(for example: integration artifacts processing data for German employees\).
    
    </td>
    </tr>
    <tr>
    <td valign="top" colspan="2">
    
    *Condition*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Artifact Type*
    
    </td>
    <td valign="top">
    
    Select an artifact type from the list. By default, preset as `Integration Flow`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Attribute* 
    
    </td>
    <td valign="top">
    
    Choose either the name or the ID of the integration artifact.

    > ### Note:  
    > An integration artifact protects the local data stores and variables associated to it. Global data stores and global variables must be protected by the artifact types `Global Data Store` and `Global Variable` respectively.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Operator
    
    </td>
    <td valign="top">
    
    -   If you select *Equals*, you must enter the exact name or ID of the integration artifact.
    -   If you select *Matches*, the value has to be a valid Java regular expression.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Value*
    
    </td>
    <td valign="top">
    
    If you choose *Equals*, enter the *ID*or the *Name*of the integration artifact.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Expression*
    
    </td>
    <td valign="top">
    
    Is shown only if you choose *Matches*.

    Enter a regular expression for *ID* or *Name*;

    > ### Note:  
    > JMS queues, global variables, and global data stores support only names.


    
    </td>
    </tr>
    </table>
    
5.  Select *Create*.

6.  To provide users access to artifacts referenced in access policies, you have to follow the steps described in:

    -   [Managing Access Policies, Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/IAT/en-US/18f06d4c8c5244d8927c0e2c5dc1c706.html "Specifics for Access Policies in the Neo Environment.") :arrow_upper_right: or

    -   [Managing Access Policies](managing-access-policies-7db3c87.md)


    otherwise no user will be able to access those artifacts!


To *Edit* or *Delete* an access policy, choose the corresponding item from the *Actions* menu of the respective row.

To *Edit* or *Delete* an artifact reference, choose the corresponding action button of the respective row.

