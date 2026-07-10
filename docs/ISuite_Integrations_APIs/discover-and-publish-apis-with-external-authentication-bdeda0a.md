<!-- loiobdeda0a4a1ce46e8874311c994e69d45 -->

# Discover and Publish APIs with External Authentication

APIs within SAP Integration Suite business system can be configured with different authentication providers, such as XSUAA \(SAP-provided OAuth server\) or an external OpenID Connect-based authorization server. This authentication configuration is performed within SAP Integration Suite.



## Prerequisites

The AuthGroup.Content.Admin role collection should be assigned to you.



## Context

When you discover APIs from a registered Integration Suite business system in Developer Hub, each API already carries its authentication provider information. Developer Hub reads the security scheme metadata from the OpenAPI Specification \(OAS\) file associated with each API and classifies it as either tenant XSUAA or External OAuth, reflecting the configuration that was set in the Integration Suite business system.

A product in Developer Hub must be homogeneous, meaning it can only contain APIs that share the same authentication provider. When creating a product from APIs classified as External OAuth, only APIs that share the same external authentication provider is presented for selection. This ensures consistency in how the product is secured and consumed.

For products created with External OAuth APIs, authorization and token management are handled entirely by the external authorization server. Application developers who want to consume these APIs can register a client ID that they have already obtained from the external identity provider, and then use those credentials to access the APIs within the product.



## Procedure

1.  Log on to Developer Hub.

2.  Navigate to the *Admin Center* \> *Manage* \> *Content*.

    A list of all business systems opens.

3.  Select the business system of type *Integration Suite*.

    The list of APIs within the system is displayed.

4.  Use the *Authentication Provider* filter \(placed above the table\) to narrow down the list of APIs and locate the APIs that you want to add to a product.

5.  Select the APIs that you want to add to the product you are about to create.

    Ensure that the APIs you select belong to the same authentication provider.

    > ### Note:  
    > A product can include APIs from only one authentication provider. APIs that use different authentication methods, such as **Tenant XSUAA** and **External OAuth**, can't be combined within the same product.
    > 
    > Supported authorization types:
    > 
    > -   OAuth Scope – Access is controlled solely through OAuth scopes.
    > 
    > -   Developer Key – Access is granted only when the JWT token contains a valid developer key.
    > 
    > -   OAuth Scope OR Developer Key – Access is granted when either the required OAuth scope or a valid developer key is present.
    > 
    > -   OAuth Scope AND Developer Key – Access is granted only when both the required OAuth scope and a valid developer key are present.
    > 
    > 
    > When a developer subscribes to a product, only APIs configured with authorization types that support developer keys \(Developer Key, OAuth Scope OR Developer Key, or OAuth Scope AND Developer Key\) can be invoked using the generated developer credentials. For example, if a product contains four APIs and only two of them are configured with developer-key-based authorization, developers will only be able to invoke those two APIs after subscription. Therefore, when creating products that can be subscribed to by developers, it is recommended to include only APIs that support developer-key-based authorization.

6.  Choose *Create Product*.

7.  On the *Create Product* dialog, provide the following details: Name, ID, Short Text and Description.

    The selected APIs will be listed under *Selected APIs* in the dialog.

8.  Now choose one of the following options:

    -   *Save as Draft*: If you pick this option, the product stays in a *Draft* state and you can publish it whenever you want. It's not available in the catalog until you publish it.

    -   *Publish*: If you choose this option, the product publishes and becomes available in the catalog. You can discover it, but you can't subscribe to the product.

    > ### Note:  
    > Product creation is an asynchronous activity, and you can track its progress on the *Scheduled Request* page.


