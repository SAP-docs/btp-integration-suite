<!-- copy1980cab180b647da9e550644197afef2 -->

# Attach Rate Plan to a Product

Attach a rate plan to a product using the SAP Integration Suite.



<a name="copy1980cab180b647da9e550644197afef2__prereq_v3f_lvp_bz"/>

## Prerequisites

-   You are assigned the admin role.

-   You have created a rate plan in the SAP Integration Suite.


> ### Note:  
> You can only attach rate plans to those products that do not have any rate plans associated with them. A product can only be associated with one rate plan. you can also attach a rate plan to a product during the product creation.

> ### Note:  
> If you try changing a rate plan or add a new rate plan to a product, all the existing applications of this product will remain unaffected by the changes. For example, if you add a rate plan to a product associated with the application, which has already been subscribed, this will not impact the current billing of the application.



## Context

You are attaching a rate plan to a product.



## Procedure

1.  Log on to the SAP Integration Suite.

2.  Choose the navigation icon on the left and choose *Design* \> *APIs*.

3.  On the *Design* \> *APIs* page, choose *Products*.

4.  From the list of products available, select the product to which you want to add the rate plan.

5.  On the Product details screen, choose *RATE PLAN*.

6.  Choose *Edit → Add Plan*.

7.  In the *Add Rate Plan* window, select the required rate plan from the list of available rate plans.

    You can click an individual rate plan to view the description and details of that particular rate plan.

8.  Choose *OK*.

    Rate plan will not be applicable to existing applications associated with the product to which the rate plan is attached. However, the rate plan will be applicable, if a new application uses the product to which the rate plan is attached.


**Related Information**  


[Create a Rate Plan](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/cfe6a30600f148a39a7920dbc7fa1ab2.html "Create a rate plan using the API portal.") :arrow_upper_right:

[Update a Rate Plan](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/b8c1e6b68be74ead8700f7f8be9baa8b.html "Update a rate plan using the API portal.") :arrow_upper_right:

[Delete a Rate Plan](https://help.sap.com/viewer/66d066d903c2473f81ec33acfe2ccdb4/Cloud/en-US/d4181ad418e4446e830c498d672204ff.html "Delete a rate plan using the API portal.") :arrow_upper_right:

