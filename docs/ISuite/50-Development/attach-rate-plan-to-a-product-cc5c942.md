<!-- loiocc5c942e32df494785c33ba0fc0346f4 -->

# Attach Rate Plan to a Product

Attach a rate plan to a product using the SAP Integration Suite.



<a name="loiocc5c942e32df494785c33ba0fc0346f4__prereq_v3f_lvp_bz"/>

## Prerequisites

-   You are assigned the admin role.

-   You have created a rate plan in the SAP Integration Suite.


> ### Note:  
> A product can only be associated with one rate plan. You can also attach a rate plan to a product during the product creation.

> ### Note:  
> If you change a rate plan or add a new rate plan to a product, all the existing applications of this product will remain unaffected by the changes.
> 
> Consider the following scenario, where you have subscribed to a product P1 \(that doesn't have a rate plan attached to it\) through application A1 in the source developer portal. In this case, the API calls associated with product P1 will not get billed.
> 
> Now if you add a rate plan to product P1, this rate plan will not impact the current billing of application A1 or any other existing subscription. However, if you create a new subscription to product P1, the associated rate plan charges will be applicable.



## Context

You are attaching a rate plan to a product.



## Procedure

1.  Log on to the SAP Integration Suite.

2.  Choose the navigation icon on the left and choose *Configure* \> *APIs*.

3.  On the *Configure* \> *APIs* page, choose *Products*.

4.  From the list of products available, select the product to which you want to add the rate plan.

5.  On the Product details screen, choose *RATE PLAN*.

6.  Choose *Edit → Add Plan*.

7.  In the *Add Rate Plan* window, select the required rate plan from the list of available rate plans.

    You can click an individual rate plan to view the description and details of that particular rate plan.

8.  Choose *OK*.

    Rate plan will not be applicable to existing applications associated with the product to which the rate plan is attached. However, the rate plan will be applicable, if a new application uses the product to which the rate plan is attached.


**Related Information**  


[Create a Rate Plan](create-a-rate-plan-cfe6a30.md "Create a rate plan using the SAP Integration Suite.")

[Update a Rate Plan](update-a-rate-plan-b8c1e6b.md "Update a rate plan using the SAP Integration Suite.")

[Delete a Rate Plan](delete-a-rate-plan-d4181ad.md "Delete a rate plan using the SAP Integration Suite.")

