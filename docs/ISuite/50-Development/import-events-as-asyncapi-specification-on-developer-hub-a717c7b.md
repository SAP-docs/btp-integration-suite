<!-- loioa717c7bf9ea74619a564ef0a344d97d2 -->

# Import Events as AsyncAPI Specification on Developer Hub 

Organize and categorize events by creating dedicated products in the catalog. Import events using an AsyncAPI specification, add them to products, and make them publicly available by publishing the associated products in the catalog.



<a name="loioa717c7bf9ea74619a564ef0a344d97d2__prereq_b2r_4hj_ncc"/>

## Prerequisites

The *AuthGroup.Content.Admin* role collection should be assigned to you.



<a name="loioa717c7bf9ea74619a564ef0a344d97d2__context_yn1_qml_gdc"/>

## Context

To import an AsyncAPI specification, you must first create a product. Then, use the *Add Event* option to import and add an AsyncAPI specification to the product. When you publish the product, the event becomes available in the catalog. Once it's available in the catalog, application developers can view the details of this event.

> ### Note:  
> The supported AsyncAPI versions are 2.0.0 and 2.5.0.



<a name="loioa717c7bf9ea74619a564ef0a344d97d2__steps_zn1_qml_gdc"/>

## Procedure

1.  Log on to **Developer Hub**.

2.  Choose *Admin Center* and select *Manage Content*.

3.  Choose the *Products* tab and choose *Create*.

    The *Create Product* dialog opens.

4.  Select *Event* as the product type, provide a name, ID, short text, and description for the product, and then select *Create Draft*.

    You're redirected to the *Products* tab where you can find the draft product.

    > ### Note:  
    > You only have the*Create Draft* option because the product needs to have at least one event before it can be published.

5.  To add an event to the product, choose *Add Event*.

6.  Browse and select or drag and drop the required AsyncAPI Specification file from your local file system.

    After you select the AsyncAPI specification file, the *Add Event* dialog is prepopulated with the event details.

7.  Choose *Save* to add the event to the product.

    > ### Note:  
    > You can add only one AsyncAPI Specification file at a time. The supported file type is .json and the maximum file size is 5 MB.

    > ### Note:  
    > You can also remove events from the draft product if needed. To remove an event from the product draft, select the event and choose *Remove*.

8.  To make the imported events available for consumption, publish the product:

    1.  Choose *Publish*.

    2.  In the confirmation dialog, choose *Publish* to make the product available in the catalog for public viewing.

    If you need to update the metadata or replace the AsyncAPI Specification file for an event imported from an external gateway after publishing, proceed as follows:

    -   Choose *Edit* for the product to move it back to the *Draft* state.
    -   Ensure the product is in *Draft* state, as events can be edited only in draft products.

    Then, optionally, perform the following steps to edit the API:

    1.  In the *Events* tab, select the event you want to modify.
    2.  Choose *Edit*.
    3.  Re-upload the AsyncAPI Specification file using *Browse Files* or drag-and-drop.
    4.  When prompted, choose whether to override the existing metadata fields \(Name, Short Text, Description\) with values from the uploaded AsyncAPI Specification file.
    5.  Confirm to apply the changes.

        You can update the metadata to match your requirements.

    6.  Choose *Save*.




<a name="loioa717c7bf9ea74619a564ef0a344d97d2__postreq_js1_2lr_ncc"/>

## Next Steps

You have the option to publish the product or keep it as a draft.

To make this product available for public viewing in the catalog, choose *Publish* at the top of the page.

A confirmation dialog will appear; choose *Yes* to confirm. The product will then be published.

Once published, you'll notice that the product's status changes from *Draft* to *Published*. At this point, application developers can discover events within products, view their details, and download the JSON files for these events.

