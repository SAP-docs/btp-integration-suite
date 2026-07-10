<!-- loio4ac0431ddc80469ca31dcd938edc9076 -->

# Different Methods of Creating an API Proxy

An API proxy is the data object that contains all the functionality to be executed when an external user wants to access the backend service.

When you create an API, you can choose from the following options:


<table>
<tr>
<td valign="top">

*Import API*

</td>
<td valign="top">

If you have an API definition, you can reuse it by importing it into the Integration Suite. For more information, see [Import an API Definition](import-an-api-definition-9342a93.md).

</td>
</tr>
<tr>
<td valign="top">

*Create*

</td>
<td valign="top">

: Create an API proxy from scratch by defining the resources, documentation, and by attaching policies. For more information, see [Create an API Proxy](create-an-api-proxy-c0842d5.md).

</td>
</tr>
<tr>
<td valign="top">

*Create in API Designer*

</td>
<td valign="top">

Model an API from a specification that contains the single target URL endpoint using the API Designer. For more information, see [Create an API Proxy Using the API Designer](create-an-api-proxy-using-the-api-designer-26e1bbd.md).

</td>
</tr>
</table>

> ### Note:  
> -   Integration Suite supports OData, REST, and SOAP services.
> -   An API proxy consists of a virtual host and a base path. The base path can be identical for multiple API proxies, provided API proxies have different virtual hosts. This means, for an API proxy, the combination of the virtual host and base path should be unique.
> 
>     The example below explains the same, where AP1 is proxy 1, AP2 is proxy 2, VH1 is Virtual Host 1, VH2 is the Virtual Host 2, and BP\(A\) is the base path.
> 
>     Example: AP1 = VH1+ BP\(A\), AP2 = VH2 + BP\(A\)

You can build a real-life API proxy that exposes a Web service from a backend system, and define policies to set rules on the API, for example, to enforce security or control API traffic. To know more, see [Policies](policies-7e4f3e5.md) and [Create a Policy](create-a-policy-c90b895.md).

You can group API proxies together into units that represent all the services needed to perform some larger business under a data object known as a product, or create a product when you want to expose one or more APIs to the application developer. For more information, see [Create a Product](create-a-product-d769622.md).

You can also view the applications you’ve subscribed to. To know more, see [View Applications](view-applications-feac368.md).

**Related Information**  


[Key Components of an API](key-components-of-an-api-19c0654.md "This section introduces you to some of the key components of an API that you need to know before building APIs.")

[Edit an API Proxy](edit-an-api-proxy-a64b952.md "Once you’ve created an API proxy you can further change the proxy, either on the Integration Suite, or by using the embedded API designer.")

[Additional Configurations](additional-configurations-de7285c.md " ")

