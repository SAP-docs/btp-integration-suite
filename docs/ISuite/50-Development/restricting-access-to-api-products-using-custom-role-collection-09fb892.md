<!-- loio09fb892458c54952a1c9abcef141ef97 -->

# Restricting Access to API Products Using Custom Role Collection

You can control access to an API product using a custom role. During product creation, you can define a custom role to restrict product access. By assigning permissions to products through roles, you control which users can discover and subscribe to specific API products.



<a name="loio09fb892458c54952a1c9abcef141ef97__prereq_y5k_q5x_ddb"/>

## Prerequisites

-   The `APIPortal.Administrator` role collection is assigned to you.
-   Create a custom role collection in the SAP BTP Cockpit. To create a custom role collection, see [Creating and Assigning a Custom Role Collection](creating-and-assigning-a-custom-role-collection-9d827cd.md).



## Context

Whenever you create a product or edit a draft product, permissions can be added to product. Use this procedure to grant permission to user roles for discovering and subscribing to the product in the Developer Hub. Only users who are assigned the required role can discover and subscribe to the product.

> ### Note:  
> Currently, we do not support assigning of permissions to the products defined in the remote API portals that are connected to a centralised Developer Hub.
> 
> \*Remote API portals are those that are not in the same subaccount as the centralised Developer Hub and are configured via the manage connections. For more information, [Centralized Developer Hub](../centralized-developer-hub-38422de.md).



## Procedure

1.  Log on to SAP Integration Suite .

2.  Choose the navigation icon on the left and choose *Engage*.

3.  Go to the *Products* tab and choose *Permission*.

    Here, whenever a product is created or a draft product is edited, permissions can be added to product.

4.  Select a role from the *Discovery* dropdown list. Only users who are assigned the selected role can discover this product in the Developer Hub.

5.  Select a role from the *Subscription* dropdown list. Only users who are assigned the selected role can subscribe to this product in the Developer Hub.

    -   You can change the roles selected for *Discovery* and *Subscription* by choosing *Edit*.

    -   You can remove the roles selected for *Discovery* and *Subscription* by choosing *Remove Role*.



**Related Information**  


[Create a Product](create-a-product-d769622.md "Explains how to create products to publish a bundle of API proxies together.")

