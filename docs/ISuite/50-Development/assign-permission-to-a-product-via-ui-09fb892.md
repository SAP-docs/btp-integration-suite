<!-- loio09fb892458c54952a1c9abcef141ef97 -->

# Assign Permission to a Product via UI

Assign permission to a product in the SAP Integration Suite .



<a name="loio09fb892458c54952a1c9abcef141ef97__prereq_y5k_q5x_ddb"/>

## Prerequisites

-   You are assigned the `APIPortal.Administrator` role.
-   You must have created a custom role on the SAP BTP Cockpit Cloud Foundry environment. For more information on creating a custom role, refer [here](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/9d827cd46b6c486f8f74482c828e67cd.html "Create a custom role for API Products in API Management.") :arrow_upper_right:.



## Context

Whenever you create a product or edit a draft product, permissions can be added to product. Use this procedure to grant permission to user roles for discovering and subscribing to the product in the API business hub enterprise. Only users who are assigned the required role can discover and subscribe to the product.



## Procedure

1.  Log on to the SAP Integration Suite .

2.  Choose the navigation icon on the left and choose *Design*.

3.  Go to the *Products* tab and choose *Permission*.

    Here, whenever a product is created or a draft product is edited, permissions can be added to product.

4.  Select a role from the *Discovery* dropdown list. Only users who are assigned the selected role can discover this product in the API business hub enterprise.

5.  Select a role from the *Subscription* dropdown list. Only users who are assigned the selected role can subscribe to this product in the API business hub enterprise.

    -   You can change the roles selected for *Discovery* and *Subscription* by choosing *Edit*.

    -   You can remove the roles selected for *Discovery* and *Subscription* by choosing *Remove Role*.



**Related Information**  


[Create a Product](create-a-product-d769622.md "Explains how to create products to publish a bundle of APIs together.")

