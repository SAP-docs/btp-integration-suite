<!-- loio2cd47e20b62344379b0f1b09ea184b33 -->

# Configure Load Balancing During Import

You can apply load-balancing functionality to an API proxy, by including the load balancer, and health monitor attributes in a .zip file along with the API proxy content.

You can attach the .zip file while importing an existing API definition in to the Integration Suite. For more information, refer [Import an API Definition](import-an-api-definition-9342a93.md).

You can configure load balancer and health monitor by adding the below attributes to `\APIProxy\APITargetEndPoint\default.xml` in the design time .zip file as shown in the following example:

> ### Sample Code:  
> ```
> <additionalAPIProviders>
>         <provider_id>target1</provider_id>
>         <provider_id>target2</provider_id>
>         <provider_id>target3</provider_id>
>     </additionalAPIProviders>
> 
>  <loadBalancerConfigurations>
>         <maxFailures>5</maxFailures>
>         <fallBackServer>target1</fallBackServer>
>         <algorithm>RoundRobin</algorithm>
>         <serverUnhealthyResponseCode>500,503</serverUnhealthyResponseCode>
>         <isRetry>true</isRetry>
>         <healthMonitor>
>             <intervalInSec>3</intervalInSec>
>             <isEnabled>true</isEnabled>
>             <httpMonitor>{"request":{"connectTimeoutInSec":18,"socketReadTimeoutInSec":30,"port":443,"verb":"GET","path":"/healthcheck"},"successResponse":{"responseCode":201}}</httpMonitor>
>         </healthMonitor>
>     </loadBalancerConfigurations>
> 
> 
> ```

The load-balancing attributes in the sample code are defined in the table below:

**Load Balancer Attributes**


<table>
<tr>
<th valign="top">

Attributes

</th>
<th valign="top">

Definitions

</th>
</tr>
<tr>
<td valign="top">

maxFailures

</td>
<td valign="top">

Specifies the number of failed requests from the API proxy to the API provider that results in the request being redirected to another API provider.

You must set <MaxFailures\> greater than 0 when using the HealthMonitor. When <MaxFailures\> value is configured as 0, the Load Balancer tries to connect to the API provider for each request and never removes the API provider from the rotation.

</td>
</tr>
<tr>
<td valign="top">

fallBackServer

</td>
<td valign="top">

When all the additional providers fail, then all the requests are sent to this fallback server. When the load balancer determines that all API providers are unavailable, all traffic is routed to the fallback server.

</td>
</tr>
<tr>
<td valign="top">

Algorithm

</td>
<td valign="top">

By default *RoundRobin* algorithm is used. But you can also use Weighted and Least Connection algorithms.

The round robin algorithm forwards a request to each API provider in the order in which the API providers are listed in the target endpoint HTTP connection.

The *Weighted* load-balancing algorithm enables you to configure proportional traffic loads for your API providers. The weighted load-balancer distributes request to your API providers in direct proportion to each API provider 's weight. Therefore, the weighted algorithm requires you to set a weight attribute for each API provider as shown in the example below:

> ### Sample Code:  
> ```
> <additionalAPIProviders>
>         <provider_id>target1</provider_id>
>         <provider_id>target2</provider_id>
>         <provider_id>target3</provider_id>
>         </additionalAPIProviders>
> 
>         <loadBalancerConfigurations>
>         <algorithm>Weighted</algorithm>
>         <isRetry>false</isRetry>
>         <fallBackServer>target1</fallBackServer>
>         <serverUnhealthyResponseCode>500,502,503</serverUnhealthyResponseCode>
>         <weigths>2</weigths>
> ```

In this example, two requests are routed to API providers for every request routed to `<provider_id>target2</provider_id>`.

You can also configure the load-balancer to use the *Least Connection* algorithm. This algorithm routes outbound requests to the API providers with fewest open HTTP connections.

```
<algorithm>LeastConnections</algorithm>
        
```



</td>
</tr>
<tr>
<td valign="top">

serverUnhealthyResponseCode

</td>
<td valign="top">

This attribute is added to help ensure that bad HTTP responses, such as 500, increments the failure counter to take an unhealthy server out of load-balancing rotation as soon as possible.

</td>
</tr>
<tr>
<td valign="top">

isRetry

</td>
<td valign="top">

If retry is enabled, a request is sent whenever a response failure occurs, for example I/O error, or HTTP timeout. A request is also sent whenever the response received matches a value set by the <serverUnhealthyResponseCode\>.

</td>
</tr>
</table>

**HealthMonitor with HTTPMonitor/ TCPMonitor Configuration Attributes**


<table>
<tr>
<th valign="top">

Attributes

</th>
<th valign="top">

Definitions

</th>
</tr>
<tr>
<td valign="top">

intervalInSec

</td>
<td valign="top">

The time interval, in seconds, between each polling TCP/HTTP request.

</td>
</tr>
<tr>
<td valign="top">

isEnabled

</td>
<td valign="top">

A boolean that enables or disables the health monitor.

</td>
</tr>
<tr>
<td valign="top">

connectTimeoutInSec

</td>
<td valign="top">

Time in which connection to the TCP/HTTP port must be established, to be considered a success. Failure to connect in the specified interval counts as a failure, incrementing the load balancer's failure count for the API provider.

</td>
</tr>
<tr>
<td valign="top">

socketReadTimeoutInSec

</td>
<td valign="top">

Time, in seconds, in which data must be read from the HTTP service to be considered a success. Failure to read in the specified interval counts as a failure, incrementing the load balancer's failure count for the API provider.

</td>
</tr>
<tr>
<td valign="top">

port

</td>
<td valign="top">

The port on which the HTTP connection to the API provider is established.

</td>
</tr>
<tr>
<td valign="top">

verb

</td>
<td valign="top">

Currently, only GET operation is supported. HTTPMonitor submits a GET request to the API provider.

</td>
</tr>
<tr>
<td valign="top">

path

</td>
<td valign="top">

The path appended to the URL defined in the API provider. Use this path element to configure a 'polling endpoint' on your HTTP service.

</td>
</tr>
<tr>
<td valign="top">

successResponse

</td>
<td valign="top">

Matching options for the inbound HTTP response message generated by the polled API provider. Responses that don’t match increment the failure count by 1.

</td>
</tr>
<tr>
<td valign="top">

responseCode

</td>
<td valign="top">

The HTTP response code expected to be received from the polled API provider.

</td>
</tr>
</table>

**Related Information**  


[Configuring Load Balancing](configuring-load-balancing-503a3aa.md "You can configure load-balancing functionality for an API proxy from the API Management, API Portal.")

