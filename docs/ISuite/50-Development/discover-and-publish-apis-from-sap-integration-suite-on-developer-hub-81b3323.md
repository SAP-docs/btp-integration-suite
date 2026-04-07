<!-- loio81b3323c0e9840a39020db6925f6e962 -->

# Discover and Publish APIs from SAP Integration Suite on Developer Hub

To make SAP Integration Suite API artifacts publicly available in Developer Hub, organize and categorize them by creating dedicated products. First, discover the APIs from SAP Integration Suite business systems. Then, add these discovered APIs to a product and publish the associated product in the catalog.



<a name="loio81b3323c0e9840a39020db6925f6e962__prereq_b2r_4hj_ncc"/>

## Prerequisites

You've activated Developer Hub in SAP Integration Suite.

The *AuthGroup.Content.Admin* role collection should be assigned to you.

> ### Note:  
> If the authentication policy of an API artifact does not include the OAuth type, the API artifact will not be visible in Developer Hub.



## Procedure

1.  Log on to Developer Hub.

2.  Navigate to the *Admin Center* \> *Manage* \> *Content*.

    A list of all business systems opens.

3.  Select the business system of type *Integration Suite*.

    The list of APIs within the system is displayed.

4.  Select the APIs that you want to add to the product you are about to create.

5.  Choose *Create Product*.

6.  You can choose the APIs you'd like to add or remove from the product. Once you've made your selections, choose *Next*.

7.  Review the product details and choose one of the following options:

    -   *Save as Draft*: If you pick this option, the product stays in a *Draft* state and you can publish it whenever you want. It's not available in the catalog until you publish it.

    -   *Publish*: If you choose this option, the product publishes and becomes available in the catalog. You can discover it, but you can't subscribe to the product.

    > ### Note:  
    > Product creation is an asynchronous activity, and you can track its progress on the *Scheduled Request* page.


