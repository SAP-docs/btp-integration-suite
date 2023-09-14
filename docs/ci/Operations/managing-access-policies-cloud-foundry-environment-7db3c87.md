<!-- loio7db3c87f6c744016b7eed9838912e123 -->

# Managing Access Policies, Cloud Foundry Environment

Specifics for Access Policies in the Cloud Foundry Environment.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Cloud Foundry environment.



<a name="loio7db3c87f6c744016b7eed9838912e123__section_l4l_hyx_v4b"/>

## Provide Access Using Role Collection

Access policies in the Cloud Foundry environment are coupled with roles based on a specific template and assigned via role collections. Thus, to grant users access to different integration artifacts and their associated data, follow the procedure described here:

1.  Create a new role as described in [Create Roles for Applications Using Existing Role Templates](https://help.sap.com/docs/CP_AUTHORIZ_TRUST_MNG/ae8e8427ecdf407790d96dad93b5f723/2670fd27fc804ad99313385711d644f6.html?version=Cloud).

    1.  Select Role Template `CustomRoleTemplate` for Application `it`.

    2.  Name the role \(we recommend to include the name of the Access Policy\).
    3.  Configure the attribute `custom_role` as `Static` and provide the name of the Access Policy as its value. Confirm your entries by pressing Enter on your keyboard and select *Next*.
    4.  \(Optional\) Select the available role collections, if you want to grant access to the artifacts referenced by the access policy specified.

2.  \(Optional\) Create an new role collection containing the role created for the access policy as described in [Define a Role Collection](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/4b20383efab341f181becf0a947a5498.html?version=Cloud).
3.  Assign a role collection containing the access policy role to the users or groups needing access to referenced artifacts. See: [Assign Role Collections to Users or User Groups](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/31532c77bd61421e9d40d100fd75ef52.html?version=Cloud).

> ### Note:  
> Newly assigned roles work only after login renewal.

The new role collection is assigned to your user and you've access to the restricted integration artifacts and their associated data.

For more information about roles and role collections see:

-   [Create Roles for Applications Using Existing Role Templates](https://help.sap.com/docs/CP_AUTHORIZ_TRUST_MNG/ae8e8427ecdf407790d96dad93b5f723/2670fd27fc804ad99313385711d644f6.html?version=Cloud)

-   [Assign Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/9e1bf57130ef466e8017eab298b40e5e.html) 

**Related Information**  


[Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md "")

