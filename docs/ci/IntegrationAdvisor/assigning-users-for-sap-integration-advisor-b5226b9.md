<!-- loiob5226b95e11b42cd9e257ae6d2b0ee0a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Assigning Users for SAP Integration Advisor



<a name="loiob5226b95e11b42cd9e257ae6d2b0ee0a__prereq_bth_11x_cmb"/>

## Prerequisites

-   You have subscribed to SAP Integration Advisor. For more information, see [Subscribing to SAP Integration Advisor](subscribing-to-sap-integration-advisor-6874eb0.md).

-   You are assigned to the *User & Role Administrator* role in the *Security* section of your subaccount.

-   The users are stored in identity providers that are connected to SAP BTP.
    -   Default identity provider \(SAP ID service\). For more information, see [SAP ID Service](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d6a8db70bdde459f92f2837349f95090.html).

    -   Custom identity provider. For more information, see [User Management](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/228428f9f476449cafd841a68d75b234.html) in SAP Cloud Identity Services - Identity Authentication.




## Context

After subscribing to Integration Advisor from the SAP BTP cockpit, you have to assign the role collection *iadv-content-developer* to the users who want to access the application. This will allow them to use SAP Integration Advisor.

To know more about managing the role collection, see [Working with Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/393ea0b222754311884123ce564779bd.html).

Here's how you can do it:



## Procedure

1.  Log in to the SAP BTP cockpit and navigate to your subaccount.

2.  Choose *Security* \> *Role Collections*.

3.  Choose the role collection *iadv-content-developer*.

4.  Choose *Edit* and navigate to the *Users* section.

5.  Enter the ID of the user that you want to assign to the role collection.

    > ### Note:  
    > You can assign users from default identity providers, and from custom identity providers, to a role collection. Once you enter the user ID, choose the origin key of the identity provider and the e-mail address. The origin key tells you in which identity provider the user is stored. You can also find that detail in *Security* \> *Trust Configuration*.
    > 
    > If the user only exists in a connected identity provider, you must choose the identity provider and type in the e-mail address.

6.  \(Optional\) To add more users, choose :heavy_plus_sign: .

7.  Choose *Save*.

    > ### Note:  
    > If you have logged in to the provisioning application before assigning the role collection, log out and log in again for the changes to reflect in your tenant.
    > 
    > If you want to assign admin access to a user, search for and choose the *iacd-content-administrator* role collection and assign users to it by repeating the steps mentioned above.


