<!-- loio4ac0431ddc80469ca31dcd938edc9076 -->

# Create an API Proxy

Create API proxies.

When you create an API, you can choose from the following options:

-   Import an API: If you have an API definition, you can reuse it by importing it into the API Management. For more information, see [Import an API](import-an-api-9342a93.md).

-   Create from API Management: Create an API proxy from scratch by defining the resources, documentation, and by attaching policies. For more information, see [Create an API](create-an-api-c0842d5.md).


> ### Note:  
> -   API Management supports OData, REST, and SOAP services.
> 
>     An API proxy consists of a virtual host and a base path. The base path can be identical for multiple API proxies, provided API proxies have different virtual hosts. This means, for an API proxy, the combination of the virtual host and base path should be unique.
> 
>     The example below explains the same, where AP1 is proxy 1, AP2 is proxy 2, VH1 is Virtual Host 1, VH2 is the Virtual Host 2, and BP\(A\) is the base path.
> 
>     Example: AP1 = VH1+ BP\(A\)
> 
>     AP2 = VH2 + BP\(A\)

> ### Note:  
> You can see the following tutorial for visual intructions on how to [Create an API Proxy](https://developers.sap.com/tutorials/hcp-apim-create-api.html).

