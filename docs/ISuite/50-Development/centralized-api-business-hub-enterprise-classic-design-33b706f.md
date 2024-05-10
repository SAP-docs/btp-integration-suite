<!-- loio33b706f4f2e148ffb1cb9289d5cda27d -->

# Centralized API business hub enterprise \[Classic Design\]

The centralized API business hub enterprise is a central API catalog, allowing application developers to consume APIs and other assets, from a common platform.

> ### Caution:  
> Effective June 2024, the classic design of the API business hub enterprise will be deprecated and will no longer be accessible. The new design of the API business hub enterprise will be set as your default design from March 2024. For more information, see [Configure the API business hub enterprise \[New Design\]](configure-the-api-business-hub-enterprise-new-design-54b4607.md).

> ### Note:  
> This document describes the classic design of the API business hub enterprise. To view the documentation for the new design, see [Centralized API business hub enterprise \[New Design\]](centralized-api-business-hub-enterprise-new-design-38422de.md).

> ### Example:  
> Organizations can use the centralized API business hub enterprise as a single platform, where different lines of business publish their APIs, allowing the organization's consumers to access these varied APIs from one location.

If you have enabled API business hub enterprise and API Management tenant in the same Integration Suite sub-account, they will automatically connect to each other.

> ### Note:  
> Once this connection is established, you will not be able to connect the API Management tenant to any other API business hub enterprise enabled in a different sub-account. However, if you have not enabled API business hub enterprise in the same Integration Suite sub-account where you have enabled API Management tenant, you can connect this API Management tenant to an API business hub enterprise enabled in another sub-account and designate it as a centralized API business hub enterprise.
> 
> This centralized API business hub enterprise can be used to establish connections with multiple API Management tenants and can receive API proxies, API products, and other assets from each connected API Management tenants. It is important to ensure that all assets published to the centralized API business hub enterprise are unique.

> ### Remember:  
> You can configure multipleIntegration Suite API Management tenants to cater to different stages of the API lifecycle. For example, you can have separate instances for development, testing, and production. However, connecting these API Management tenants having such a relationship to the same API business hub enterprise will violate the uniquness of the assets.

Once the application developers register with the centralized API business hub enterprise, they can easily search, explore, and test APIs. They can also create and subscribe to specific types of applications available from the API business hub enterprise.

The API business hub enterprise admin identifies which existing or new API business hub enterprise application can accept content from multiple Integration Suite API Management tenants.

