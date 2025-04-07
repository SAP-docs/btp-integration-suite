<!-- loioea561e424f6e44aa985fceedf7fabee7 -->

# Consume APIs

You can consume APIs via Developer Hub. In Developer Hub, an application developer registers, explores the APIs exposed by customers, creates applications, and tests API proxies.

> ### Caution:  
> Effective June 2024, the classic design of Developer Hub will be deprecated and will no longer be accessible. The new design of Developer Hub will be set as your default design from March 2024. For more information, see [User Roles and Responsibilities in Developer Hub](../user-roles-and-responsibilities-in-developer-hub-54b4607.md).

If you've added Developer Hub as a capability with Integration suite, or if you’ve subscribed to Developer Hub as part of the standalone API Management subscription, you have the option to experience the new design of the Developer Hub user interface along with the classic design.

> ### Note:  
> By default, the Site Administrator has an option to switch from classic to new design and set the new design as the default UI using the **Site Editor.** The Site Administrator has the right to enable the configuration to let all the other users switch between the old and the new design. For more information, see [Customize the Visual Format of Developer Hub](customize-the-visual-format-of-developer-hub-2eacd52.md).

![](images/ABHE_Block_509b298.png)

Developer Hub is an application that provides a common platform for Application developers to consume API proxies. Every API Management customer is provided with their own Developer Hub application on cloud. Developer Hub offers capabilities to onboard application developers, explore and test API proxies, create and subscribe to Applications.

Developer Hub supports the following features:

-   **Onboard an Application developer**- To explore the API proxies and subscribe to an Application, an Application developer must be registered to Developer Hub. On registering, the Application developer is provided access to Developer Hub.
-   **Browse Catalog**- Explore the Products \(assembled APIs\) available in the Catalog store, navigate to individual API proxies, read the API Documentation, and view the resources attached to the API proxies.

    As an application developer, when accessing the API details on the API reference page, you can view the supported authentication mechanisms defined in the API specification. This allows you to authorize yourself by providing the necessary credentials for the authentication type and successfully try out the APIs.

    > ### Note:  
    > The open-source Swagger library, which Developer Hub relies on, limits the rendering of API schemas with circular references on deeply nested models, causing slow, improper, or no rendering.

-   **Create Applications** – An Application developer can create on or more applications to consume API proxies. To consume the API proxies, an Application developer must subscribe to an Application \(assembled Products\). It is by subscribing to an Application that you return to the developer the key required to access the API proxies.
-   **Download JSON**- You can download the open API specification for the APIs that are part of Developer Hub in JSON format. This enables the developer to use the metadata of the APIs for various aspects such as code/SDK generation for developing applications.

-   **Download SDK**- You can also download the client software development kit \(SDK\) for developers through a non-commercial license on open source sites. You can use this SDK for developing applications.

-   **Test API Proxies** - You can test the API proxies and understand the runtime behavior of the API proxies better. Use the Test Console to explore the resources associated with an API and execute the operations.

**Related Information**  


[User Roles and Responsibilities in Developer Hub](../user-roles-and-responsibilities-in-developer-hub-54b4607.md "After activating Developer Hub, assign users the necessary roles and role collections to access its various features and functionalities. Once you've assigned the appropriate roles, you can configure and customize Developer Hub to align with your organization's needs.")

