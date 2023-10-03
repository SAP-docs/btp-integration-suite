<!-- loiobcf7f21956574a7389f24fd8a2364850 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Additional Configurations for Trading Partner Management

Procedure to create and assign a role collection to an user.

The role *AuthGroup\_TenantPartnerDirectoryConfigurator* is required to provide you access to:

-   Activate agreements and publish their content into Partner Directory

-   Deactivate agreements

The role cannot be assigned directly to a user. In order to get the access, you need to create a role collection and assign this role to a role collection and then assign that role collection to an user. To do so, follow the steps mentioned below:

1.  Login to your BTP cockpit nad navigate to your subaccount.

2.  On the left pane, navigate to *Security* \> *Role Collections*.
3.  The screen displays the list of role collections available for the subaccount. Choose *Create New Role Collection* :heavy_plus_sign: button to create a role collection.
4.  In the *Create Role Collection* dialog, enter a meaningful name in the *Name* field and enter a description in the *Description* field.
5.  Choose *Create*.
6.  Using the search bar above the role collections table, search for and open your role collection.
7.  Choose *Edit* to edit your role collection.
8.  Under the *Roles* tab, select the value help <span class="SAP-icons"></span> button under the *Role Name* column.
9.  In the resulting dialog, search for *AuthGroup\_TenantPartnerDirectoryConfigurator* in the *Role Name* field.
10. Once the result appears, select the role by selecting the checkbox next to it and choose *Add*. The role is now assigned to the role collection.
11. If you want to assign users to this role collection, navigate to the *Users* tab and search for the user using their mail address and choose add :heavy_plus_sign: to assign the user.
12. Choose *Save* to save your changes. Your user now has the access to activate and deactivate trading partner agreements.

