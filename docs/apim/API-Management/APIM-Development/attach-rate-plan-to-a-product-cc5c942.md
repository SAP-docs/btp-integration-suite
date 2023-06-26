<!-- loiocc5c942e32df494785c33ba0fc0346f4 -->

# Attach Rate Plan to a Product

Attach a rate plan to a product using the API portal.



<a name="loiocc5c942e32df494785c33ba0fc0346f4__prereq_v3f_lvp_bz"/>

## Prerequisites

-   You are assigned the admin role.

-   You have created a rate plan in the API portal.


> ### Note:  
> You can only attach rate plans to those products that do not have any rate plans associated with them. A product can only be associated with one rate plan. you can also attach a rate plan to a product during the product creation.

> ### Note:  
> If you try changing a rate plan or add a new rate plan to a product, all the existing applications of this product will remain unaffected by the changes. For example, if you add a rate plan to a product associated with the application, which has already been subscribed, this will not impact the current billing of the application.



## Context

You are attaching a rate plan to a product.



## Procedure

1.  Log on to the API portal.

2.  Choose the navigation icon on the left and choose *Develop*.

3.  On the *Develop* page, choose *Products*.

4.  From the list of products available, select the product to which you want to add the rate plan.

5.  On the Product details screen, choose *RATE PLAN*.

6.  Choose *Edit → Add Plan*.

7.  In the *Add Rate Plan* window, select the required rate plan from the list of available rate plans.

    You can click an individual rate plan to view the description and details of that particular rate plan.

8.  Choose *OK*.

    Rate plan will not be applicable to existing applications associated with the product to which the rate plan is attached. However, the rate plan will be applicable, if a new application uses the product to which the rate plan is attached.


**Related Information**  


[Create a Rate Plan](create-a-rate-plan-cfe6a30.md "Create a rate plan using the API portal.")

[Update a Rate Plan](update-a-rate-plan-b8c1e6b.md "Update a rate plan using the API portal.")

[Delete a Rate Plan](delete-a-rate-plan-d4181ad.md "Delete a rate plan using the API portal.")

