<!-- loio33b706f4f2e148ffb1cb9289d5cda27d -->

# Centralized API business hub enterprise \[Classic Design\]

The centralized API business hub enterprise is a central API catalog, allowing application developers to consume APIs and other assets, from a common platform.

> ### Note:  
> By default, the Site Administrator has an option to switch from classic to new design and set the new design as the default UI using the **Site Editor.** The Site Administrator has the right to enable the configuration to let all the other users switch between the old and the new design.

> ### Note:  
> This document describes the classic design of the API business hub enterprise. To view the documentation for the new design, see [Centralized API business hub enterprise \[New Design\]](centralized-api-business-hub-enterprise-new-design-38422de.md).

> ### Example:  
> Organizations can use the centralized API business hub enterprise as a single platform, where different lines of business publish their APIs, allowing the organization's consumers to access these varied APIs from one location.

Every API Management instance will have an API business hub enterprise application on cloud. One of the various API Business Hub Enterprises is set as a centralized API catalog. This catalog will then receive API proxies, API products, and other assets from each connected API Portal. All the assets published to the centralized API business hub enterprise must be unique.

> ### Remember:  
> You can define different API Management instances to suit a particular stage in the API lifecycle. So you can have Development, Test, and Productive instances. Transport of APIs between the API Portals of these instances is also possible, see [Transport APIs and Its Related Artifacts](../APIM-Development/transport-apis-and-its-related-artifacts-eb83118.md). However, connecting the API Portals having such a relationship to the same API business hub enterprise will violate the uniquness of the assets.

Once the application developers register to centralized API business hub enterprise, they can seamlessly search, explore, and test APIs. They can also create and subscribe to various applications from the API business hub enterprise.

The API business hub enterprise admin identifies which existing or new API Business Hub Enterprise application can accept content from multiple API portals.

