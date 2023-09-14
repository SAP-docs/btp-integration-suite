<!-- loio342c20a3e53d4de69ea5a845fa29f0c1 -->

# Consume a Public HTTP Service with Query Parameters

Learn how to properly set the query parameters when calling an HTTP API.

This section shows you how the receiver HTTP adapter is properly configured in order to consume an HTTP-based API.

For more information about the configuration options of the HTTP receiver adapter, check out the chapter [HTTP Receiver Adapter](http-receiver-adapter-2da452e.md).



<a name="loio342c20a3e53d4de69ea5a845fa29f0c1__section_r5w_dyg_gnb"/>

## Implementation

The example integration flow *Modeling Basics - Consume a Public HTTP Service With Query Parameters* is designed in the following way:

![](images/2010_Design-Guidelines-HTTP-Adapter_a7afa3c.png)

The integration flow receives a message through an HTTP adapter. The incoming message contains a header Category that is used in the outbound call.

In a Request Reply step, product data is read from an external source through the HTTP protocol \(using the HTTP receiver adapter\). For our scenario, we use the ESPM WebShop, which is based on the Enterprise Sales and Procurement Model \(ESPM\) provided by SAP. The demo application can be accessed at the following address: [https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html](https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/webshop/index.html).

As an example, for the product category Software, the overall HTTP request is defined as follows: `https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/espm-cloud-web/espm.svc/Products?$select=ProductId,Category,Name,ShortDescription&$filter=Category eq 'Software'&$orderby=Name`.

Hence, in the connection details of the HTTP receiver adapter, the following is configured:

-   The address is defined as follows: [https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/espm-cloud-web/espm.svc/Products](https://refapp-espm-ui-cf.cfapps.eu10.hana.ondemand.com/espm-cloud-web/espm.svc/Products).

-   The query string is defined as follows using query parameters $select, $filter, and $orderby: `$select=ProductId,Category,Name,ShortDescription&$filter=Category eq '${header.Category}'&$orderby=Name`


> ### Note:  
> -   The question mark *?* at the beginning of the query needs to be deleted for the adapter adds it automatically.
> 
> -   The parameters are separated using an ampersand &.
> 
> -   You can use properties and headers within your query string to dynamically configure your service call. Here, we use the header field Category that we passed to the integration flow when calling its end point to filter the result set based on a particular product category.

You can even dynamically override the complete address and query configuration of the adapter by defining the headers CamelHttpUri and CamelHttpQuery, respectively, before calling the HTTP adapter. For more details, see [HTTP Receiver Adapter](http-receiver-adapter-2da452e.md).

**Related Information**  


[HTTP Receiver Adapter](http-receiver-adapter-2da452e.md "Use the HTTP receiver adapter to communicate with target systems using HTTP message protocol.")

