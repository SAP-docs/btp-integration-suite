<!-- loio961d39e57aff4e02b38447651ce64fc6 -->

# Create Products by Importing API Specifications

As a content administrator, you can discover APIs from various business systems and publish them as products in the Developer Hub catalog. However, if you have an API specification from an external gateway, you can still create a product and make it available in the catalog.



<a name="loio961d39e57aff4e02b38447651ce64fc6__prereq_b2r_4hj_ncc"/>

## Prerequisites

The *AuthGroup.Content.Admin* role collection should be assigned to you.



## Context

To import an API specification, you must first create a product. Then, use the *Add API* option to import and add an API specification to the product. When you publish the product, the API becomes available in the catalog. Once it's available in the catalog, application developers can view the detailss of this API.



## Procedure

1.  Log on to the **Developer Hub**.

2.  Navigate to the *Admin Center* \> *Manage* \> *Content*.

3.  Choose the *Products**Create*

    The *Create Product* dialog opens.

4.  Enter the name, ID, short text, and description and choose *Create Draft tab and choose*.

    > ### Note:  
    > You only have the*Create Draft* option because the product needs to have at least one API before it can be published.

    You're redirected to the *Products* tab where you can find the draft product.

5.  In the right pane, choose *Add API* to add an API to the product.

6.  tab and chooseBrowse and select or drag and drop the required OpenAPI Specification file from your local file system.

    After you select the API specification file, the *Add API* dialog is prepopulated with the API details.

7.  Choose *Save* to add the API to the product.

    > ### Note:  
    > You can add only one OpenAPI Specification file at a time. The supported file types are .json and .edmx, and the maximum file size is 5 MB.

    > ### Note:  
    > You can also remove APIs from the draft product if needed. To remove an API from the product draft, select the API and choose*Remove*.




<a name="loio961d39e57aff4e02b38447651ce64fc6__postreq_js1_2lr_ncc"/>

## Next Steps

You can choose *Publish* to make this product available on the catalog for public viewing.

Once published, you'll see that the status of the product has chaged from *Draft* to *Published*. Application developers can now discover APIs within products, view details, and download the JSON files and SDKs for those APIs.

