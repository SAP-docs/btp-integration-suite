<!-- loio961d39e57aff4e02b38447651ce64fc6 -->

# Import APIs from External Gateways and Publish on Developer Hub

If you have API specifications from external gateways, you can still make them publicly available. Import the API specifications, add these APIs to products, and publish the associated products in the Developer Hub catalog.



<a name="loio961d39e57aff4e02b38447651ce64fc6__prereq_b2r_4hj_ncc"/>

## Prerequisites

The *AuthGroup.Content.Admin* role collection should be assigned to you.



## Context

To import an API specification, you must first create a product. Then, use the *Add API* option to import and add an API specification to the product. When you publish the product, the API becomes available in the catalog. Once it's available in the catalog, application developers can view the detailss of this API.



## Procedure

1.  Log on to **Developer Hub**.

2.  Navigate to the *Admin Center* and select *Manage Content*.

3.  Select the *Products* tab and choose *Create*.

    The *Create Product* dialog opens.

4.  Enter the name, ID, short text, and description. Then choose *Create Draft*.

    You're redirected to the *Products* tab where you can find the draft product.

    > ### Note:  
    > You only have the*Create Draft* option because the product needs to have at least one API before it can be published.

5.  To add an API to the product, choose *Add APIs*.

6.  Browse and select or drag and drop the required OpenAPI Specification file from your local file system.

    After you select the OpenAPI specification file, the *Add API* dialog is prepopulated with the API details.

7.  Choose *Save* to add the API to the product.

    > ### Note:  
    > You can add only onec file at a time. The supported file types are .json and .edmx, and the maximum file size is 5 MB.

    > ### Note:  
    > You can also remove APIs from the draft product if needed. To remove an API from the product draft, select the API and choose *Remove*.

8.  To make the imported API available for consumption, publish the product:

    1.  Choose *Publish*.

    2.  In the confirmation dialog, choose *Publish* to make the product available in the catalog for public viewing.

    If you need to update the metadata or replace the OpenAPI Specification file for an API imported from an external gateway after publishing, proceed as follows:

    -   Choose *Edit* for the product to move it back to the *Draft* state.
    -   Ensure the product is in *Draft* state, as APIs can be edited only in draft products.

    Then, optionally, perform the following steps to edit the API:

    1.  In the *APIs* tab, select the API you want to modify.
    2.  Choose *Edit*.
    3.  Re-upload the OpenAPI Specification file using *Browse Files* or drag-and-drop.
    4.  When prompted, choose whether to override the existing metadata fields \(Name, Short Text, Description\) with values from the uploaded OpenAPI Specification file.
    5.  Confirm to apply the changes.

        You can update the metadata to match your requirements.

    6.  Choose *Save*.




<a name="loio961d39e57aff4e02b38447651ce64fc6__postreq_js1_2lr_ncc"/>

## Next Steps

You have the option to publish the product or keep it as a draft.

To make this product available for public viewing in the catalog, choose *Publish* at the top of the page.

A confirmation dialog will appear; choose *Yes* to confirm. The product will then be published.

Once published, you'll notice that the product's status changes from *Draft* to *Published*. At this point, application developers can discover the APIs within products, view their details, and download the JSON files and SDKs for those APIs.

