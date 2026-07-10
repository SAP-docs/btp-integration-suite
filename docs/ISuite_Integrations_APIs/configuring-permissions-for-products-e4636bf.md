<!-- loioe4636bfe66b6496c8d5495ae1889e7c5 -->

# Configuring Permissions for Products

You can configure permissions for products that include APIs from different business systems. These permissions are a set of rules that define which users or systems are granted or denied access to specific products.



<a name="loioe4636bfe66b6496c8d5495ae1889e7c5__prereq_b2r_4hj_ncc"/>

## Prerequisites

The *AuthGroup.Content.Admin* role collection should be assigned to you.



## Context

You can currently only configure static custom roles for the products. You create these roles in the SAP BTP cockpit using the Application Developer template. Then you add them to role collections to assign to users. For more information, see[Creating and Assigning a Custom Role Collection](creating-and-assigning-a-custom-role-collection-9d827cd.md).



## Procedure

1.  Log on to Developer Hub.

2.  Navigate to the *Admin Center* \> *Manage* \> *Content*.

3.  Choose the *Products* tab.

    Here, you'll find a list of products in both draft and published states.

4.  Choose the product for which you want to set permissions.

    A pane opens on the right side of the screen.

5.  To manage permissions, select the *Permissions* tab in the pane.

    > ### Note:  
    > This action creates a draft. Once the product is in draft state, you can update the permissions and publish it again.

6.  Choose *Edit Permissions*.

    From this page, you can manage the permissions for product discovery and subscription.

7.  Select roles for *Discovery* and *Subscription* as required:

    -   *Discovery*: Controls who can view and discover the product.

    -   *Subscription*: Controls who can subscribe to and use the product.

        > ### Note:  
        > Even if all the standard roles are assigned to an application developer \(such as AuthGroup.API.ApplicationDeveloper\), they must also be explicitly assigned the custom role defined by the organization to create a subscription. If a product’s subscription permissions include this custom role, the application developer will not be able to create a subscription to the product unless they also have that role. This restriction also applies when attempting to create a subscription on behalf of another application developer—the operation will fail if the initiating user does not possess the required custom role, as permission checks are enforced based on the logged-in user rather than the target user.


8.  Choose *Save* to apply the permission changes.

    > ### Note:  
    > The roles listed are the custom roles you previously defined in the SAP BTP Cockpit.

9.  You can choose *Publish* to apply the permission to the product.


