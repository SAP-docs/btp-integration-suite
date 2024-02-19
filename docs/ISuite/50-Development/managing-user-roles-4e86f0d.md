<!-- loio4e86f0dcb41f49e99ea43e82a0e99c73 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing User Roles

The user role monitor allows a tenant administrator to manage user roles which then can be used during inbound authorization of an integration flow execution.



<a name="loio4e86f0dcb41f49e99ea43e82a0e99c73__section_tvn_fx2_zhb"/>

## How to Access the User Roles Monitor

You open the area with the following action:

In the *Monitor* view, select the *User Roles* tile in the *Manage Security* section. User roles defined by SAP and by the tenant administrator are displayed.



<a name="loio4e86f0dcb41f49e99ea43e82a0e99c73__section_sgz_pry_yhb"/>

## UI Overview

A list of user roles are displayed in a table. For each role, the following attributes are displayed:

**Attributes of Custom Role-Related Entries**


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

Name

</td>
<td valign="top">

Display name of the user role

> ### Note:  
> When creating a new user role, be aware of the following allowed characters in user role names: a-z, A-Z, 0-9, \_ \(underscore\), . \(period\).



</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Description of the user role.

</td>
</tr>
<tr>
<td valign="top">

Owner

</td>
<td valign="top">

The owner of the entry:

-   *Tenant Administrator*

    The entry is owned by the tenant administrator on customer side.

-   *SAP*

    The entry is owned by SAP.




</td>
</tr>
<tr>
<td valign="top">

Actions

</td>
<td valign="top">

Choose one of the two buttons to perform an action. The available actions are:

-   *Edit role* \(:pencil2:\)

    On the subsequent screen, you can edit the description of the selected user role.

-   *Delete role* \(:wastebasket:\)



</td>
</tr>
</table>

> ### Note:  
> The technical user role **ESBMessaging.send** is predefined by SAP and cannot be removed or changed.

To sort and filter the content of the table, choose *Table Settings* \(:gear:\) displayed above the table. On the subsequent screen, you can define how the table entries are to be sorted \(by specifying an attribute and whether the entries are to be sorted for that attribute in ascending or descending order\). You can also filter the table entries for certain attributes.

You also have the option to refresh the table by selecting *Reload content* \(<span class="SAP-icons-V5"></span>\).



<a name="loio4e86f0dcb41f49e99ea43e82a0e99c73__section_iw3_m1f_zhb"/>

## Actions

The following actions are available:

-   *Add*

    After you have chosen *Add*, a subsequent input box appears where you need to specify the role name and the role description. Only the role description is editable afterwards.

-   *Download to JSON*

    A JSON file of the selected user roles is downloaded. You need to import the JSON file in the *Process Integration Runtime* tile to create a service instance in the Cloud Foundry environment that is associated with a user role. Only then, you can call an integration flow endpoint and ensure the processing of the integration flow on the runtime node.

    You can either use a custom role that you created, or use the predefined role **ESBMessaging.send**. The JSON content of the role **ESBMessaging.send** is:

    > ### Sample Code:  
    > ```
    > {
    >  "roles":[
    >  "ESBMessaging.send"
    >  ]
    > }
    > ```

    Instead of downloading the JSON file, you can also use *Copy selected roles in JSON format to the clipboard* \(<span class="SAP-icons-V5"></span>\) at the beginning of the table. In the next step, you can use the copied format to create, as an example, a new service instance.




<a name="loio4e86f0dcb41f49e99ea43e82a0e99c73__section_hpc_kdt_zhb"/>

## Next Steps

For a detailed instruction on how to create a service instance and a service key, visit [Creating Service Instance and Service Key for Inbound Authentication](../40-RemoteSystems/creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md).

Watch the next video to know more about a basic inbound authentication end-to-end scenario.

> ### Note:  
> This video was created before our branding changes related to SAP technology were announced in January 2021.



**Related Information**  


[Basic Authentication with clientId and clientsecret for Integration Flow Processing](../40-RemoteSystems/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md "Use this procedure to connect a sender system to SAP Cloud Integration.")

