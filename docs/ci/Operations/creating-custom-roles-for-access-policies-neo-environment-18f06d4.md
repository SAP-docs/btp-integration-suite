<!-- loio18f06d4c8c5244d8927c0e2c5dc1c706 -->

# Creating Custom Roles for Access Policies, Neo Environment

Create custom roles to define access policies in the Neo environment.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.



<a name="loio18f06d4c8c5244d8927c0e2c5dc1c706__section_gvb_2c1_w4b"/>

## Provide Access Using Custom Roles

Access policies in the Neo environment are coupled with custom user roles. Thus, to grant users access to different integration artifacts and their associated data you have to create a custom role.

Go to SAP BTP cockpit and follow the procedure described in [Managing Roles](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/db8175b9d976101484e6fa303b108acd.html).

> ### Caution:  
> The name of the custom role must match the name of the access policy.

> ### Note:  
> -   You must be an administrator to create roles.
> 
> -   The length of the custom role name is limited to a maximum of 200 characters. If this limit is exceeded, the custom role can't be used in an access policy. Leading and trailing spaces aren’t allowed.
> 
> -   Assign the role to users who are to get access once the access policies are active.

> ### Note:  
> Newly assigned roles work only after login renewal.

**Related Information**  


[Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md "")

