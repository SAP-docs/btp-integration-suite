<!-- loio38422de917ee40e1a47df0b368def295 -->

# Centralized Developer Hub 

Developer Hub is a central API catalog, allowing application developers to consume APIs and other assets, from a common platform.

If you have enabled Developer Hub and API Management tenant in the same SAP Integration Suite sub-account, they will automatically connect to each other.

> ### Note:  
> Once this connection is established, you will not be able to connect the API Management tenant to any other Developer Hub enabled in a different sub-account. However, if you have not enabled Developer Hub in the same SAP Integration Suite sub-account where you have enabled API Management tenant, you can connect this API Management tenant to Developer Hub enabled in another sub-account and designate it as a centralized Developer Hub.
> 
> This centralized Developer Hub can be used to establish connections with multiple API Management tenants and can receive API proxies, API products, and other assets from each connected API Management tenants. It is important to ensure that all assets published to the centralized Developer Hub are unique.

> ### Remember:  
> You can configure multipleSAP Integration Suite API Management tenants to cater to different stages of the API lifecycle. For example, you can have separate instances for development, testing, and production. However, connecting these API Management tenants having such a relationship to the same Developer Hub will violate the uniquness of the assets.

Once the application developers register with the centralized Developer Hub, they can easily search, explore, and test APIs. They can also create and subscribe to specific types of applications available from Developer Hub.

The Developer Hub admin identifies which existing or new Developer Hub application can accept content from multiple SAP Integration Suite API Management tenants.

