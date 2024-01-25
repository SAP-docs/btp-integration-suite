<!-- loio09fb892458c54952a1c9abcef141ef97 -->

# Assign Permission to a Product via UI

Assign permission to a product in the SAP Integration Suite .



<a name="loio09fb892458c54952a1c9abcef141ef97__prereq_y5k_q5x_ddb"/>

## Prerequisites

-   You are assigned the `APIPortal.Administrator` role.
-   You must have created a custom role on the SAP BTP Cockpit Cloud Foundry environment. For more information on creating a custom role, refer [here](../creating-a-custom-role-9d827cd.md).



## Context

Whenever you create a product or edit a draft product, permissions can be added to product. Use this procedure to grant permission to user roles for discovering and subscribing to the product in the API business hub enterprise. Only users who are assigned the required role can discover and subscribe to the product.

> ### Note:  
> Currently, we do not support assigning of permissions to the products defined in the remote API portals that are connected to a centralised API business hub enterprise.
> 
> \*Remote API portals are those that are not in the same subaccount as the centralised API business hub enterprise and are configured via the manage connections. For more information, [Centralized API business hub enterprise \[New Design\]](centralized-api-business-hub-enterprise-new-design-38422de.md) and [Centralized API business hub enterprise \[Classic Design\]](centralized-api-business-hub-enterprise-classic-design-33b706f.md).



## Procedure

1.  Log on to the SAP Integration Suite .

2.  Choose the navigation icon on the left and choose *Engage*.

3.  Go to the *Products* tab and choose *Permission*.

    Here, whenever a product is created or a draft product is edited, permissions can be added to product.

4.  Select a role from the *Discovery* dropdown list. Only users who are assigned the selected role can discover this product in the API business hub enterprise.

5.  Select a role from the *Subscription* dropdown list. Only users who are assigned the selected role can subscribe to this product in the API business hub enterprise.

    -   You can change the roles selected for *Discovery* and *Subscription* by choosing *Edit*.

    -   You can remove the roles selected for *Discovery* and *Subscription* by choosing *Remove Role*.



**Related Information**  


[Create a Product](create-a-product-d769622.md "Explains how to create products to publish a bundle of API proxies together.")

