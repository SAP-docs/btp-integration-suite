<!-- loio81b3323c0e9840a39020db6925f6e962 -->

# Discover and Publish APIs from SAP Integration Suite 

To make SAP Integration Suite API artifacts publicly available in Developer Hub, organize and categorize them by creating dedicated products. First, discover the APIs from SAP Integration Suite business systems. Then, add these discovered APIs to a product and publish the associated product in the catalog.



<a name="loio81b3323c0e9840a39020db6925f6e962__prereq_b2r_4hj_ncc"/>

## Prerequisites

You've activated Developer Hub in SAP Integration Suite.

The *AuthGroup.Content.Admin* role collection should be assigned to you.

> ### Note:  
> If the authentication policy of an API artifact does not include the OAuth type, the API artifact will not be visible in Developer Hub.

> ### Note:  
> You can discover and publish only OData and REST API artifacts. SOAP API artifacts are currently not supported.



## Context

In Developer Hub, APIs are exposed to consumers through products. A product acts as a container that groups one or more APIs and makes them available in the API catalog for discovery. When creating a product from APIs discovered in SAP Integration Suite, certain constraints apply regarding authentication providers and runtime deployments.

Use the *Authentication Provider* filter to narrow down the list of APIs and locate the APIs that you want to add to a product. Ensure that the APIs you select belong to the same authentication provider.

> ### Note:  
> A product can include APIs from only one authentication provider. APIs that use different authentication methods, such as Internal and External OAuth, can't be combined within the same product.

Use the *Runtime* filter to narrow down the list of APIs based on the runtime where the APIs are deployed.

> ### Note:  
> If an API is deployed to multiple runtimes \(for example, Edge Integration Cell 1, Edge Integration Cell 2, and others\), only one runtime deployment can be published within a product.



## Procedure

1.  Log on to Developer Hub.

2.  Navigate to the *Admin Center* \> *Manage* \> *Content*.

    A list of all business systems opens.

3.  Select the business system of type *Integration Suite*.

    The list of APIs within the system is displayed.

4.  Select the APIs that you want to include in the product and choose **Create Product**.

5.  In the *Create Product* dialog, enter the product details:

    -   *Name*: Enter a user-friendly name for the product. This name is displayed in the catalog.
    -   *ID*: Provide a unique identifier for the product. This value is used internally and must be unique across products.
    -   *Short Text*: Add a brief summary of the product. This helps users quickly understand its purpose in the catalog.
    -   *Description*: Provide a detailed description of the product, including its purpose, usage, or any relevant business context.
    -   *Selected APIs*: Review the APIs included in the product. You can remove any API if needed before proceeding.

6.  Choose one of the following options:

    -   *Save as Draft*: If you pick this option, the product stays in a *Draft* state and you can publish it whenever you want. It's not available in the catalog until you publish it.

    -   *Publish*: If you choose this option, the product publishes and becomes available in the catalog. You can discover it, but you can't subscribe to the product.

    > ### Note:  
    > Product creation is an asynchronous activity, and you can track its progress on the *Scheduled Request* page.


