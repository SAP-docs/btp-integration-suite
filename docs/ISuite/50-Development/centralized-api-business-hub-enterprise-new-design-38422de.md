<!-- loio38422de917ee40e1a47df0b368def295 -->

# Centralized API business hub enterprise \[New Design\]

The API business hub enterprise is a central API catalog, allowing application developers to consume APIs and other assets, from a common platform.

> ### Note:  
> By default, the site administrator has the option to switch from the classic design to the new design and set the new design as the default user interface \(UI\) using the *Site Editor*. The site administrator also has the authority to enable a configuration that allows all other users to switch between the old and new designs.
> 
> This document describes the new design of the API business hub enterprise. To view the documentation for the classic design, see [Centralized API business hub enterprise \[Classic Design\]](centralized-api-business-hub-enterprise-classic-design-33b706f.md)

> ### Example:  
> By default, the site administrator has the option to switch from the classic design to the new design and set the new design as the default user interface \(UI\) using the *Site Editor*. The site administrator also has the authority to enable a configuration that allows all other users to switch between the old and new designs.

Each Integration Suite API Management tenant that is enabled will have an API business hub enterprise application in the cloud. Within these API business hub enterprises, one is designated as the centralized API catalog. The centralized catalog will receive API proxies, API products, and other assets from every connected Integration Suite API Management tenant. It is important to note that all assets published to the centralized API business hub enterprise must be unique.

> ### Remember:  
> You can configure multiple API Management instances to cater to different stages of the API lifecycle. For example, you can have separate instances for development, testing, and production. It is also possible to transport APIs between these Integration Suite API Management tenants. For more information, see [Transport APIs and Its Related Artifacts](transport-apis-and-its-related-artifacts-eb83118.md). However, connecting the Integration Suite API Management tenants having such a relationship to the same API business hub enterprise will violate the uniquness of the assets.

Once the application developers register to centralized API business hub enterprise, they can seamlessly search, explore, and test APIs. They can also create and subscribe to various applications from the API business hub enterprise.

The API business hub enterprise admin identifies which existing or newAPI business hub enterprise application can accept content from multiple Integration Suite API Management tenants.

