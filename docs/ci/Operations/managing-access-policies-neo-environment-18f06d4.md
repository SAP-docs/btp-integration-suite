<!-- loio18f06d4c8c5244d8927c0e2c5dc1c706 -->

# Managing Access Policies, Neo Environment

Specifics for Access Policies in the Neo Environment.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.



<a name="loio18f06d4c8c5244d8927c0e2c5dc1c706__section_gvb_2c1_w4b"/>

## Provide Access Using Custom Roles

Access policies in the Neo environment are coupled with custom user roles. Thus, to grant users access to different integration artifacts and their associated data you must:

Create a `Custom Role`. Go to the SAP BTP cockpit and follow the procedure described in [Managing Roles](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/db8175b9d976101484e6fa303b108acd.html).

> ### Caution:  
> The name of the custom role must match the name of the access policy that you created!

> ### Note:  
> -   You must be an Administrator to create roles.
> 
> -   To be used for an access policy, the length of the custom role name is limited to a maximum of 200 characters. Leading and trailing spaces aren’t allowed.
> 
> -   Assign the role to users who are to get access, once the access policies are active.

> ### Note:  
> Newly assigned roles work only after login renewal.

**Related Information**  


[Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md "")

