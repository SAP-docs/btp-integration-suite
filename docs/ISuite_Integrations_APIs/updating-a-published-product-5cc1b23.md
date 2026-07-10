<!-- loio5cc1b23cfb2143208dfc91adb3964d5e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Updating a Published Product

After a product has been published, you can update the product and publish it again. While the *Edit* option is available only for a published product, you can't edit it directly. Actions such as updating, removing, adding, and deleting APIs are only possible when the product is in a draft state.



<a name="loio5cc1b23cfb2143208dfc91adb3964d5e__prereq_b2r_4hj_ncc"/>

## Prerequisites

The *AuthGroup.Content.Admin* role collection should be assigned to you.



## Context

The *Edit* option becomes available when the product's status is *Published*. If you choose to edit, the system prompts you to create a draft copy of the product. In this draft state, you can update the APIs in the product. This means you can retrieve the most recent API status from the target system. You can also update the product metadata like name, short text, description.

Additionally, you can remove and add APIs to the product. Once done you can publish the draft or delete the product if you no longer need it.



## Procedure

1.  Log on to Developer Hub.

2.  Navigate to the *Admin Center* \> *Manage* \> *Content*.

3.  Choose the *Products* tab.

    Here, you'll find a list of products in both draft and published states. The *Product Type* column in the Products list identifies the type of each product.

    Products are used to package and publish consumable assets in the Developer Hub catalog. Depending on the type of asset being exposed, products can be created as one of the following types:

    -   *API* – Contains one or more APIs along with their associated documentation. These products are intended for application developers who consume APIs.
    -   *Event* – Contains one or more event-driven interfaces that enable consumers to discover and subscribe to event streams.
    -   *AI* – Contains AI-related artifacts intended for agent and AI-driven consumption. Currently, AI products support MCP Servers.

        > ### Note:  
        > Availability of the MCP Server depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Flaunchpad.support.sap.com%2F%23%2Fnotes%2F2903776).


4.  Select the product you'd like to edit. Remember, the product must be in *Published* state.

5.  On the right pane, select the<span class="SAP-icons-V5"></span> more icon and choose *Edit*.

    A message will pop up indicating that in order to edit a published product, a draft copy must be created.

6.  Choose *Yes* to continue.

    A draft copy of the product is created.

    > ### Note:  
    > If a draft of the product you are attempting to edit already exists, you will receive a warning message asking you to either *Overwrite* the existing draft with the new one, or *Cancel* the "Create Draft" action.

7.  You can now perform the following actions on the draft:

    -   *Update*: Use this option to update the selected API\(s\) of this product after the product was published. This action fetches the most recent API state from the target system. You can track the update progress in the *Scheduled Requests* section.

    -   *Remove*: Use this option to remove the selected API\(s\) from this product.

    -   *Add API*: Use this option to search and add new API\(s\) to this product from the corresponding consumption bundle.

        Select the API from the *Add API* dialog and choose *Add*.

        Your request to add new APIs to this product gets created. You can track the progress of product creation in the scheduled requests.

    -   *Publish* Choose this option to make the product available for public viewing in the catalog.

    -   *Delete:* This option permanently removes the product from the system.



