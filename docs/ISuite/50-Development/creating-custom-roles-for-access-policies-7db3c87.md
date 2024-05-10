<!-- loio7db3c87f6c744016b7eed9838912e123 -->

# Creating Custom Roles for Access Policies

Define a custom role to be associated with an access policy.



Access policies are associated with roles based on template *CustomRoleTemplate* and assigned via role collections. To grant users access to different integration artifacts and their associated data, perform the following steps:

1.  In SAP Business Technology Platform cockpit, select your subaccount.

2.  Create a new role as described in [Create Roles for Applications Using Existing Role Templates](https://help.sap.com/docs/CP_AUTHORIZ_TRUST_MNG/ae8e8427ecdf407790d96dad93b5f723/2670fd27fc804ad99313385711d644f6.html?version=Cloud).

    Specify the parameters in the following way:

    -   As *Role Template* select *CustomRoleTemplate*, as *Application* select *it*.

    -   Specify any role name \(we recommend to include the name of the access policy\).

    -   For *custom\_role* select *Static*.

    -   Under *Values* enter the value you've specified as *Role Name* when creating the access policy \(defined in the SAP Integration Suite *Monitor* section, see [Defining Access Policies](defining-access-policies-b0d7950.md)\).

        > ### Note:  
        > After you've specified these parameters, you need to confirm your entries by pressing Enter on your keyboard. If not, you can't select *Next* to proceed with the role creation.

    -   \(Optional\) Select the available role collections, if you want to grant access to the artifacts referenced by the access policy specified.


3.  Create a new role collection and assign the role defined in the previous step to it \(see [Define a Role Collection](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/4b20383efab341f181becf0a947a5498.html?version=Cloud)\).

    Alternatively, you can select an existing role collection and assign the role defined in the previous step to it.

4.  Assign the role collection containing the access policy role to the users or groups needing access to referenced artifacts. See: [Assign Role Collections to Users or User Groups](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/31532c77bd61421e9d40d100fd75ef52.html?version=Cloud).

> ### Note:  
> Newly assigned roles work only after login renewal.

The new role collection is assigned to your user and you've access to the restricted integration artifacts and their associated data.

For more information about roles and role collections see:

-   [Create Roles for Applications Using Existing Role Templates](https://help.sap.com/docs/CP_AUTHORIZ_TRUST_MNG/ae8e8427ecdf407790d96dad93b5f723/2670fd27fc804ad99313385711d644f6.html?version=Cloud)

-   [Assign Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/9e1bf57130ef466e8017eab298b40e5e.html) 

**Related Information**  


[Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md "")

