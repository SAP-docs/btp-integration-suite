<!-- loioedeed6a4684b49ed917f0e1cc189a62d -->

# Target Endpoint Properties

HTTP transport properties configured in the HTTPTargetConnection element in TargetEndpoint configurations defines a set of properties to set transport level configurations.



You can export the proxy endpoint as a zip file and add the TargetEndpoint properties to the APITargetEndPoint subfolder under the APIProxy parent folder. For more information, see [Export an API Definition](export-an-api-definition-420abb6.md).

Configure the properties on TargetEndpoint HTTPTargetConnection elements:

> ### Sample Code:  
> ```
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <TargetEndPoint>
>     <name>default</name>
>     <url>http://www.abc.com</url>
>     <provider_id>NONE</provider_id>
>     <isDefault>true</isDefault>
>     <properties>
>         <property>
>             <name>temp</name>
>             <value>value</value>
>         </property>
>         <property>
>             <name>test</name>
>             <value>v2</value>
>         </property>
>     </properties>
>     <faultRules/>
>     <preFlow>
>         <name>PreFlow</name>
>     </preFlow>
>     <postFlow>
>         <name>PostFlow</name>
>     </postFlow>
>     <conditionalFlows/>
> </TargetEndPoint>
> 
> ```

> ### Note:  
> Alternatively, you can navigate to the *Design* \> *APIs* tab, choose the API proxy that you deployed from the APIs list, and select the *Target EndPoint* tab. In the *Target Endpoint Properties* section, choose *Add* and enter the *Property Name* and the *Value* as defined in the **TargetEndpoint Transport Property Specification** table.

**TargetEndpoint Transport Property Specification**

**TargetEndpoint Transport Property Specification**


<table>
<tr>
<th valign="top">

Property Name

</th>
<th valign="top">

Default Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

keepalive.timeout.millis

</td>
<td valign="top">

60000 milliseconds

</td>
<td valign="top">

Connection idle timeout for the target connection in the connection pool. If the connection in the pool is idle beyond the specified limit, then the connection is closed.

</td>
</tr>
<tr>
<td valign="top">

connect.timeout.millis

</td>
<td valign="top">

3000 milliseconds

</td>
<td valign="top">

Target connection timeout. returns an HTTP 503 status code if a connection timeout occurs.

</td>
</tr>
<tr>
<td valign="top">

io.timeout.millis

</td>
<td valign="top">

55000 milliseconds

</td>
<td valign="top">

If there’s no data to read for the specified number of milliseconds, or if thesocket is not ready to write data for specified number of milliseconds, then the transaction is treated as a timeout.

-   If a timeout happens while writing the HTTP request, 408, Request Timeout is returned.
-   If a timeout happens while reading the HTTP response, 504, Gateway Timeout is returned.

> ### Note:  
> In general, the default timeout value is 55 seconds for APIs. The APIs created based on the on-premise backend, the value is 54 seconds.
> 
> For the API proxies where the io.timeout.millis value isn’t set explicitly in the target endpoint, the default timeout value of 55 seconds or 54 seconds \(based on the type of the backend system\) is considered in the runtime.
> 
> For the API proxies where the io.timeout.millis value is explicitly set in the target endpoint, the same value is considered in the runtime, provided it’s less than the default 55 seconds/54 seconds. Please note that the older version of API proxies created based on the on-premise backend system before July 2022 will require a redeployment for the timeout propagation to come into effect.
> 
> Also, note that the timeout explained above is not precise, the actual timeout could occur slightly earlier than the timeout value.



</td>
</tr>
<tr>
<td valign="top">

supports.http10

</td>
<td valign="top">

true

</td>
<td valign="top">

If true and the client sends a 1.0 request, the target is also sent a 1.0 request. Otherwise 1.1 request is sent to target.

</td>
</tr>
<tr>
<td valign="top">

supports.http11

</td>
<td valign="top">

true

</td>
<td valign="top">

If true and the client sends a 1.1 request, the target is also sent a 1.1 request, otherwise 1.0 request is sent to target.

</td>
</tr>
<tr>
<td valign="top">

success.codes

</td>
<td valign="top">

N/A

</td>
<td valign="top">

By default, HTTP code 4XX or 5XX are treated as errors, HTTP code 1XX, 2XX, 3XX as success. This property enables explicit definition of success codes, for example, 2XX, 1XX, 505 treats any 100, 200 and 505 HTTP response codes as success.

Setting this property overwrites the default values. Therefore, if you want to add HTTP code 400 to the list of default success codes, set this property as:

```
<Property name="success.codes">1xx,2xx,3xx,400</Property>
```

If you want only HTTP code 400 to be treated as a success code, set the property as:

```
<Property name="success.codes">400</Property>
```

By setting HTTP code 400 as the only success code, the codes 1xx, 2xx, and 3xx are treated as failures.

</td>
</tr>
<tr>
<td valign="top">

compression.algorithm

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Supported values:

-   gzip: always send message using gzip compression
-   deflate: always send message using deflate compression
-   none: always send message without any compression

For example, when a client submits a request that uses `gzip` compression, API Management forwards the request to target using `gzip` compression. You can configure compression algorithms to be explicitly applied by setting this property on the TargetEndpoint or ProxyEndpoint.

</td>
</tr>
<tr>
<td valign="top">

enable.method.override

</td>
<td valign="top">

false

</td>
<td valign="top">

For the specified HTTP method, sets an X-HTTP-Method-Override header on the outbound request to the target service. For example, `<Property><name>="GET.override.method"</name><value>POST</value></Property>`.

</td>
</tr>
<tr>
<td valign="top">

request.streaming.enabled

</td>
<td valign="top">

false

</td>
<td valign="top">

Default value \(false\): HTTP request payloads are read into a buffer, and policies operating on the payload work as expected.

True: HTTP request payloads are not read into a buffer, they are streamed to the target endpoint. And, policies that operate on the payload in the TargetEndpoint request flow are bypassed.

For more information about enabling streaming, see [Enable Streaming of Requests and Responses in an API Proxy](enable-streaming-of-requests-and-responses-in-an-api-proxy-b43d826.md)

</td>
</tr>
<tr>
<td valign="top">

\*.override.method

</td>
<td valign="top">

N/A

</td>
<td valign="top">

For the specified HTTP method, sets an X-HTTP-Method-Override header on the outbound request. For example, `<Property><name>="GET.override.method"</name><value>POST</value></Property>`.

</td>
</tr>
<tr>
<td valign="top">

response.streaming.enabled

</td>
<td valign="top">

false

</td>
<td valign="top">

Default value \(false\): HTTP response payloads are read into a buffer, and policies that can operate on the payload work as expected.

true: HTTP response payloads aren’t read into a buffer; they’re streamed as-is to the ProxyEndpoint response flow. In this case, any policies that operate on the payload in the TargetEndpoint response flow are bypassed.

For more information about enabling streaming, see [Enable Streaming of Requests and Responses in an API Proxy](enable-streaming-of-requests-and-responses-in-an-api-proxy-b43d826.md)

</td>
</tr>
<tr>
<td valign="top">

request.retain.headers.enabled

</td>
<td valign="top">

true

</td>
<td valign="top">

By default, all HTTP headers on outbound messages are retained. On setting it to true, all HTTP headers present on the inbound request are set on the outbound request.

</td>
</tr>
<tr>
<td valign="top">

request.retain.headers

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Set HTTP headers from the request on the outbound request to the target service. For example, to 'passthrough' the `User-Agent` header, set the value of `request.retain.headers` to User-Agent. Specify multiple HTTP headers as a comma-separated list, for example, User-Agent,Referer,Accept-Language. This property overrides `request.retain.headers.enabled`. If `request.retain.headers.enabled` is set to false, any headers specified in the `request.retain.headers` property are still set on the outbound message.

</td>
</tr>
<tr>
<td valign="top">

response.retain.headers.enabled

</td>
<td valign="top">

true

</td>
<td valign="top">

By default, all HTTP headers on outbound messages are retained. On setting it to true, all HTTP headers present on the inbound response from the target service are set on the outbound response before it’s passed to the ProxyEndpoint.

</td>
</tr>
<tr>
<td valign="top">

response.retain.headers

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Set HTTP headers from the response on the outbound response before it is passed to the ProxyEndpoint. For example, to `passthrough` the `Expires` header, set the value of `response.retain.headers` to Expires. Specify multiple HTTP headers as a comma-separated list, for example, Expires,Set-Cookie. This property overrides `response.retain.headers.enabled`. If`response.retain.headers.enabled` is set to false, any headers specified in the `response.retain.headers` property are still set on the outbound message.

</td>
</tr>
<tr>
<td valign="top">

retain.queryparams

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Set query parameters on the outbound request. For example, to include the query parameter `apikey` from the request message, set retain.queryparams to apikey. Specify multiple query parameters as a comma-separated list, for example, apikey, environment. This property overrides retain.queryparams.enabled.

</td>
</tr>
<tr>
<td valign="top">

retain.queryparams.enabled

</td>
<td valign="top">

true

</td>
<td valign="top">

By default, all query parameters on outbound requests are retained. On setting it to true, all query parameters present on the inbound request are set on the outbound request to the target service.

</td>
</tr>
</table>

**Related Information**  


[Proxy Endpoint Properties](proxy-endpoint-properties-1705a92.md "ProxyEndpoint HTTPTargetConnection elements define a set of HTTP transport properties. These properties can be used to set transport-level configurations.")

