<!-- loio7945bef8852343688e2d39c9f8646845 -->

# Edit an Event Product

After publishing an event product, you can create a draft version to modify its details, update the events included in the product, manage rate plans and broker configurations, and then republish the draft to make the changes available to consumers.



<a name="loio7945bef8852343688e2d39c9f8646845__prereq_b2r_4hj_ncc"/>

## Prerequisites

-   The *AuthGroup.Content.Admin* role collection should be assigned to you.

-   Events must be shared before they can be added to a product. If an event is not shared, go to the Advanced Event Mesh portal and mark the event as shared.




## Procedure

1.  Log on to Developer Hub.

2.  Navigate to the *Admin Center* \> *Manage* \> *Content*.

3.  On the *Products* tab, select the published event product that you want to edit.

4.  Choose **Edit**.

    A draft version of the product is created for editing.

    If a draft already exists for the selected product, a warning message is displayed. Choose *Overwrite* to replace the existing draft with a new draft based on the current published version, or choose *Cancel* to keep the existing draft.

5.  Update the required product information using the available tabs, and choose *Save* to apply your changes.

    -   *Overview* – Edit the product name, short description, and description.
    -   *Events* – Add or remove events associated with the product.
    -   *Rate Plans* – Add or remove rate plans associated with the product.
    -   *Brokers* – Add or remove brokers and update the protocols through which consumers can access the product's events.
    -   *Permissions* – Modify the roles that can discover and subscribe to the product.

6.  Choose *Publish*.

    The draft is published and the updated version becomes available to consumers.




## Results

The event product is updated with the latest configuration. The published version reflects the changes made in the draft, and consumers can access the updated product based on the configured events, rate plans, permissions, and broker settings.

