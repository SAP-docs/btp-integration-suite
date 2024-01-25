<!-- loio7ac0c09f414f4740960c5a15bc18472b -->

# Load Balancing Across API Providers

Load-balancing is configured to distribute the load efficiently across multiple API providers.

Load-Balancing can be applied to an API proxy only when the API proxy is created with a link to an API provider. For more information on how to link an API proxy to the API provider, refer to the [Create an API Proxy](create-an-api-proxy-c0842d5.md).

To perform all the operations related to the target endpoint, for example, fetching the resources and synchronizing all the operations, the API proxy is linked to an API provider. For load balancing, additional API providers are linked to the API proxy.

> ### Note:  
> All the API providers that are linked to the API proxy must exist in design time.

