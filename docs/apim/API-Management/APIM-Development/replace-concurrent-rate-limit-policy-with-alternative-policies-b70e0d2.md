<!-- loiob70e0d26c9a14f8493e9cf90a4cdebd2 -->

# Replace Concurrent Rate Limit Policy with Alternative Policies

The Concurrent Rate Limit policy was designed to cater to slow backend systems, however, the architecture used by it affected the performance of the APIs. Therefore, this policy has been **decomissioned**.

> ### Note:  
> You can use the Spike Arrest policy to limit the number of requests to the backend systems over a specified period of time. You can also use Quota policy to limit the number of request messages that an API proxy allows over a period of time, such as minute, hour, day, week, or month. The Quota policy shouldn’t be used to protect target backend systems against traffic spikes.

If you’re wondering which policy to use to best meet your rate limiting needs, refer the following comparison chart:

**Comparison Between the Quota, Spike Arrest, and Concurrent Rate Limit Policy**


<table>
<tr>
<th valign="top">

Quota

</th>
<th valign="top">

Spike Arrest

</th>
<th valign="top">

Concurrent Rate Limit \(Decomissioned\)

</th>
</tr>
<tr>
<td valign="top">

Use it to limit the number of connections apps can make to your API proxy's target backend over a specific period of time.

</td>
<td valign="top">

Use it to protect your API proxy's target backend against severe traffic spikes and denial of service attacks.

</td>
<td valign="top">

Use it to limit the number of concurrent connections apps can make to your API proxy's target backend.

</td>
</tr>
<tr>
<td valign="top">

Don't use it to protect your API proxy's target backend against traffic spikes. Use the Spike Arrest policy instead.

</td>
<td valign="top">

Don't use it to count and limit the number of connections apps can make to your API proxy's target backend over a specific period of time. Use the Quota policy instead.

</td>
<td valign="top">

Don't use it to limit the number of connections applications can make to your API proxy's target backend over a specific period of time. Use the Quota policy for this purpose.

</td>
</tr>
<tr>
<td valign="top">

The Quota policy stores the count.

</td>
<td valign="top">

The Spike Arrest policy doesn't store the count.

</td>
<td valign="top">

The Concurrent Rate Limit policy stores the count.

</td>
</tr>
<tr>
<td valign="top">

Attach the policy to the **ProxyEndpoint Request Pre-Flow**, generally after the authentication of the user. This enables the policy to check the quota counter at the entry point of your API proxy.

</td>
<td valign="top">

Attach the policy to the **ProxyEndpoint Request Pre-Flow**, generally at the very beginning of the flow. This provides spike protection at the entry point of your API proxy.

</td>
<td valign="top">

This policy must be attached in these three locations:

-   TargetEndpoint Request Pre-Flow

-   TargetEndpoint Response Pre-Flow

-   TargetEndpoint DefaultFaultRule




</td>
</tr>
<tr>
<td valign="top">

HTTP status code when limit has been reached: 500 \(Internal Server Error\) \*

</td>
<td valign="top">

HTTP status code when limit has been reached: 500 \(Internal Server Error\) \*

</td>
<td valign="top">

HTTP status code when limit has been reached: 503 \(Service Unavailable\)

</td>
</tr>
<tr>
<td valign="top">

Good to know facts:

-   Quota counter is stored in Cassandra.

-   Configure the policy to synchronize the counter asynchronously to save resources.

-   Asynchronous counter synchronization can cause a delay in the rate limiting response, which allows calls slightly in excess of the limit you've set.


See [Quota](quota-1f742c1.md) for more information.

</td>
<td valign="top">

Good to know facts:

-   Performs throttling based on the time at which the last traffic was received. This time is stored per message processor.

-   If you specify a rate limit of 100 calls per second, only 1 call every 1/100 second \(10 ms\) is allowed on the message processor. A second call within 10 ms is rejected.

-   Even with a high rate limit per second, nearly simultaneous requests results in rejections.


See [Spike Arrest](spike-arrest-bf441dc.md) for more information.

</td>
<td valign="top">

Good to know facts:

-   Keeps a count of concurrent connections per message processor.

-   While an individual API proxy handles just a few connections collectively, the connections to a set of replicated API proxies pointing to the same backend service swamp the capacity of the service. Use this policy to limit this traffic to a manageable number of connections.

-   This policy is known to slow performance in API proxies that handle a high number of transactions per second \(TPS\). For high-TPS API proxies, if ConcurrentRateLimit slows performance to unacceptable levels, try using SpikeArrest instead.


See [Concurrent Rate Limit](concurrent-rate-limit-8f22baa.md) for more information.

</td>
</tr>
</table>

> ### Example:  
> Refer this example to replace Concurrent Rate Limit policy with Spike Arrest policy.
> 
> In Concurrent Rate Limit, four concurrent connections were allowed. In Spike Arrest, four requests per minute are allowed. You can alter the Spike Arrest Policy based on the number of requests allowed for your backend system.

> ### Sample Code:  
> ```
> <?xml version=*"1.0" encoding="UTF-8" standalone="yes"?>
> <SpikeArrest async="false" continueOnError="false" enabled="true" name="Spike-Arrest-1">
> <DisplayName>Spike-Arrest-1</DisplayName>
>     <Properties/>
>     <Rate>4pm</Rate>
>     <UseEffectiveCount>true</UseEffectiveCount></SpikeArrest>
> 
> ```

> ### Sample Code:  
> ```
> <?xml version=*"1.0" encoding="UTF-8" standalone="yes"?>
> <ConcurrentRatelimit async="false" continueOnError="false" enabled="true" name="Concurrent Rate Lmit-1">
> <DisplayName>Concurrent Rate Lmit-1</DisplayName>
>     <AllowConnections count="4" ttl="7"/>
>     <Distributed>true</Distributed>
>     <StrictOnTtl>true</StrictOnTtl>
>     <TargetIdentifier name=""/>
>     <UseEffectiveCount>true</UseEffectiveCount>
> </ConcurrentRatelimit>
> 
> 
> ```

> ### Note:  
> Concurrent Rate Limit and the Spike Arrest policy aren’t the same and works differently. However, you can tune it to allow specific requests per second, and set the maximum number of requests your backend system receives.

