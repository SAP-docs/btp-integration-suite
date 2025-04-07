<!-- loio08aff917402e4abd8dba2d03e369c12e -->

# Discover and Publish APIs from Business Systems on Developer Hub

To make APIs publicly available in the catalog, organize and categorize them by creating dedicated products. First, discover the APIs from various business systems. Then, add these discovered APIs to a product and publish the associated product in the catalog.



<a name="loio08aff917402e4abd8dba2d03e369c12e__prereq_b2r_4hj_ncc"/>

## Prerequisites

The *AuthGroup.Content.Admin* role collection should be assigned to you.



## Procedure

1.  Log on to Developer Hub.

2.  Navigate to the *Admin Center* \> *Manage* \> *Content*.

    A list of all business systems is displayed.

3.  Select a business system to discover the APIs within that business system:

    For SAP S/4 HANA system type, the APIs will be listed within the consumption bundles.

    -   **Create a product from a single consumption bundle**

        > ### Note:  
        > Product creation is an asynchronous activity, and you can track its progress on the *Scheduled Request* page.

        1.  Select the consumption bundle and choose *Create Product*.

        2.  The name, ID, short text, and description from the consumption bundle are pre-populated. However, you're free to make any changes. After you've checked the product details, select *Next*.
        3.  You can choose the APIs you'd like to add or remove from the product. Once you've made your selections, choose *Next*.
        4.  Review the product details and choose one of the following options:
            -   *Save as Draft*: If you pick this option, the product stays in a *Draft* state and you can publish it whenever you want. It's not available in the catalog until you publish it.

            -   *Publish*: If you choose this option, the product publishes and becomes available in the catalog. You can discover it, but you can't subscribe to the product.


    -   **Create products from multiple consumption bundles**

        1.  Select the consumption bundles and choose *Create Product*.

        2.  You can view the consumption bundles you've selected in the *Selected Consumption Bundles* section. At this point you can either publish the product or save the product as a draft.

            > ### Note:  
            > When you select multiple consumption bundles, the system creates a product for each one. It uses the names and descriptions of the selected bundles for these products.

            -   *Save as Draft*: When you select this option, it keeps the products in a draft state. You're free to publish them at any time. However, they're not available in the catalog until you do so..

            -   *Publish*: If you choose this option, the products are published. They become available in the catalog for discovery. However, the products are not available for subscription.




**Related Information**  


[Make APIs Available in the Catalog](make-apis-available-in-the-catalog-f148690.md "As a content administrator, make your APIs available to developers in your organization by publishing them on Developer Hub.")

[Manage Products](manage-products-4dd3d90.md "As a content administrator, you have the ability to manage a product once it has been created.")

