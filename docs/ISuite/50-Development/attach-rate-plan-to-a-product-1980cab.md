<!-- copy1980cab180b647da9e550644197afef2 -->

# Attach Rate Plan to a Product

Attach a rate plan to a product using the SAP Integration Suite.



<a name="copy1980cab180b647da9e550644197afef2__prereq_v3f_lvp_bz"/>

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


 <?sap-ot O2O class="- topic/link " href="cfe6a30600f148a39a7920dbc7fa1ab2.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/lze1710737251935/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/1980cab180b647da9e550644197afef2.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

 <?sap-ot O2O class="- topic/link " href="b8c1e6b68be74ead8700f7f8be9baa8b.xml" text="" desc="" xtrc="link:2" xtrf="file:/home/builder/src/dita-all/lze1710737251935/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/1980cab180b647da9e550644197afef2.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

 <?sap-ot O2O class="- topic/link " href="d4181ad418e4446e830c498d672204ff.xml" text="" desc="" xtrc="link:3" xtrf="file:/home/builder/src/dita-all/lze1710737251935/loiocc0ab4c7365e43bbbee9eae27deb32da_en-US/src/content/localization/en-us/1980cab180b647da9e550644197afef2.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

