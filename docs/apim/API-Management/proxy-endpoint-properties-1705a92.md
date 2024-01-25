<!-- loio1705a92daa37474eab483a1ccb6d9b28 -->

# Proxy Endpoint Properties

ProxyEndpoint HTTPTargetConnection elements define a set of HTTP transport properties. These properties can be used to set transport-level configurations.



You can export the proxy endpoint as a zip file and add the ProxyEndpoint properties to the the APIProxyEndPoint subfolder under the APIProxy parent folder. For more information, see [Export an API Definition](export-an-api-definition-420abb6.md).

Properties are set on ProxyEndpoint HTTPProxyConnection elements as follows:

> ### Sample Code:  
> ```
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <ProxyEndPoint default="true">
>     <name>default</name>
>     <base_path>/sdf</base_path>
>     <properties>
>         <property>
>             <name>temp</name>
>             <value>v1</value>
>         </property>
>     </properties>
>     <routeRules>
>         <routeRule>
>             <name>default</name>
>             <targetEndPointName>default</targetEndPointName>
>             <sequence>1</sequence>
>             <faultRules/>
>         </routeRule>
>     </routeRules>
>     <faultRules/>
>     <preFlow>
>         <name>PreFlow</name>
>     </preFlow>
>     <postFlow>
>         <name>PostFlow</name>
>     </postFlow>
>     <conditionalFlows/>
> </ProxyEndPoint>
> 
> ```

> ### Note:  
> Alternatively, you can navigate to the *Design* \> *APIs* tab, choose the API proxy that you deployed from the APIs list, and select the *Proxy EndPoint* tab. In the *Proxy Endpoint Properties* section, choose *Add* and enter the *Property Name* and the *Value* as defined in the **ProxyEndpoint Transport Property Specification** table.



**ProxyEndpoint Transport Property Specification**

**ProxyEndpoint Transport Property Specification**


<table>
<tr>
<th valign="top">

Property Value

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

X-Forwarded-For

</td>
<td valign="top">

false

</td>
<td valign="top">

On setting it to true, the virtual host's IP address is added to the outbound request as the value of the HTTP `X-Forwarded-For` header.

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

true: HTTP request payloads are not read into a buffer, they are streamed to the TargetEndpoint request flow.And, policies operating on the payload in the ProxyEndpoint request flow are bypassed.

For more information about enabling streaming, see [Enable Streaming of Requests and Responses in an API Proxy](enable-streaming-of-requests-and-responses-in-an-api-proxy-b43d826.md)

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

Default value \(false\): HTTP response payloads are read into a buffer, and policies operating on the payload work as expected.

true: HTTP response payloads are not read into a buffer, they are streamed to the TargetEndpoint request flow.And, policies operating on the payload in the ProxyEndpoint response flow are bypassed.

For more information about enabling streaming, see [Enable Streaming of Requests and Responses in an API Proxy](enable-streaming-of-requests-and-responses-in-an-api-proxy-b43d826.md)

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

api.timeout

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Configure the timeout for individual API proxies.

</td>
</tr>
</table>

**Related Information**  


[Target Endpoint Properties](target-endpoint-properties-edeed6a.md "HTTP transport properties configured in the HTTPTargetConnection element in TargetEndpoint configurations defines a set of properties to set transport level configurations.")

