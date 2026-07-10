<!-- loio08aff917402e4abd8dba2d03e369c12e -->

# Publish SAP S/4HANA APIs from Business Systems

As a content administrator, make your SAP S/4HANA APIs available to developers in your organization by publishing them on Developer Hub.



<a name="loio08aff917402e4abd8dba2d03e369c12e__prereq_b2r_4hj_ncc"/>

## Prerequisites

The *AuthGroup.Content.Admin* role collection should be assigned to you.



## Context

Developer Hub acts as a centralized repository where content administrators can showcase their APIs, and provide corresponding API documentation.

To effectively publish an API, it is crucial to understand how to bundle them together and present them as a cohesive product. A product is essentially a collection of APIs, which includes metadata specific to your business for monitoring or analytics. For instance, you can bundle all CRM-related APIs into a CRM product. Once the required API are included in a product, it can be published to the catalog, allowing application developers to browse through and access it.

You can build a catalog either by creating products that contains APIs from various business systems or by importing API specification.



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

        2.  The name, ID, short text, and description from the consumption bundle are pre-populated. However, you're free to make any changes.
        3.  Review the APIs included in the product. You can remove any API if needed before proceeding.
        4.  After you've checked the product details, choose one of the following options:
        5.  Review the product details and choose
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


 <?sap-ot O2O class="- topic/link " href="f148690b1f7f45e894edaab3c29c701b.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiod8a6092f89b24b5e8531d35c034be3aa_en-US/src/content/localization/en-us/08aff917402e4abd8dba2d03e369c12e.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

[Manage Products](manage-products-4dd3d90.md "As a content administrator, you have the ability to manage a product once it has been created.")

