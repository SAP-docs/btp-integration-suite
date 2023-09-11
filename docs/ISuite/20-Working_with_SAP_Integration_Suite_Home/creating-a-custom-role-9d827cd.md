<!-- loio9d827cd46b6c486f8f74482c828e67cd -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Custom Role

Create a custom role for API products in API Management.



<a name="loio9d827cd46b6c486f8f74482c828e67cd__context_qzh_dxk_pkb"/>

## Context

You can restrict access to an API product in API Management using a custom role. That is, only an authorized user can discover and subscribe to API Products that are tagged to a custom role.

> ### Note:  
> If you’re using Integration Suite, refer [Create Roles for Applications Using Existing Role Templates](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/2670fd27fc804ad99313385711d644f6.html?q=creating%20roles) to create a custom role for API Products.
> 
> To create a custom role for API Product, use the *ApplicationDeveloper* role template. Also, ensure that for the *CustomRole* attribute, you choose the value of *Source* as *Static*, and in the *Values*, specify the attribute values and press enter. This value is later used to assign permission while creating an API Product.



## Procedure

1.  Go to your *Subaccount* in *SAP BTP Cockpit* for Cloud Foundry environment.

2.  Choose *Service Marketplace* in the left-hand pane.

3.  In order to create a custom role, choose the *API Management, API Business Hub Enterprise* tile.

4.  Under *Application Plans* for API BusinessHub Enterprise, choose the <span class="SAP-icons"></span> Action icon and select *Manage Roles*.

5.  To add a new custom role, choose :heavy_plus_sign:.

6.  In the *Create Role* dialog, fill the details for:

    -   Role Name
    -   Description
    -   Role Template: Choose *ApplicationDeveloper*.
    -   Attributes: For the *CustomRole* attribute, keep the value of *Source* as *static*. Under *Values* specify the attribute values and press enter.

        > ### Note:  
        > Use only alphanumeric characters for the attribute values. Also, the attribute values shouldn't contain any spaces or special characters except for the hyphen '-' and underscore '\_'.
        > 
        > It is recommended that you use CamelCase for better readability.
        > 
        > The *Next* option on the *Create Role* dialogue will remain greyed out until you press enter after typing the attribute values in the text box.

        ![](images/Static_Custom_Role_a6bade0.png)

        This value is later used to assign permission while creating an API product.

        A new role is created and added to the Roles list.


7.  **Add the created role to *Role Collection*:** Adding a custom role to the role collection ensures that you choose a specific application and role template.

    1.  Navigate to your *Subaccount* \> *Security* \> *Role Collections*. Choose :heavy_plus_sign:and provide a *Name* and *Description* to the new role collection.

    2.  Choose the newly created *Role Collection* and choose *Edit*.

    3.  To select the custom role, choose the <span class="SAP-icons"></span> icon under the *Roles* tab.

    4.  On the *Select: Role* dialog, choose the custom role from the *Role Name* dropdown, select the checkbox under *Roles*, and choose *Add*.

    5.  Choose *Save*.


8.  **Assign role collection to the user**: To assign the created role collection to your authorized email ID:

    1.  Go to the *Users* section and choose *Edit*.

    2.  Enter the user ID of the user that you want to assign to the role collection. If the user only exists in a connected identity provider, you must choose the identity provider and type in the email address.

    3.  \(Optional\) To add more users, choose :heavy_plus_sign: \(Add a user\).

    4.  Save your changes.


    > ### Remember:  
    > Application Developers who are already onboarded in the API business hub enterprise should have the custom role. If any user has been assigned a custom role but hasn’t been onboarded as an application developer in the API business hub enterprise, the application creation fails. In this case, Authgroup.API.Admin can onboard the user as an Application Developer in the portal.

    **Next Steps**

    After completing the above steps, assign permissions while creating a Product in API Portal application. For more information on the same refer, [here](../50-Development/assign-permission-to-a-product-via-ui-09fb892.md).


**Related Information**  


[Create a Product](../50-Development/create-a-product-d769622.md "Explains how to create products to publish a bundle of APIs together.")

[Assign User Roles in API Management](assign-user-roles-in-api-management-911ca5a.md "Use role collections to group together different roles that can be assigned to API Portal and API business hub enterprise users.")

