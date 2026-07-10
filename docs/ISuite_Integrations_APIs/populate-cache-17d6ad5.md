<!-- loio17d6ad5ceb944c20ac26291c0698e0ea -->

# Populate Cache

An OAuth access token is written to the cache using a Populate Cache policy. The OAuth token is retrieved for subsequent requests by a Lookup Cache policy.

At runtime, the Populate Cache policy writes data from the variable you specified in the <Source\> element to the cache you specified in the <CacheResource\> element. You can use the <CacheKey\>, <Scope\>, and <Prefix\> elements to specify a key that you can use from the Lookup Cache policy to retrieve the value. Use the <ExpirySettings\> element to configure when the cached value should expire.

You can attach this policy in the following locations:

![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <PopulateCache async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <CacheKey>
>         <KeyFragment ref="request.header.userid"></KeyFragment>
>     </CacheKey>
>     <Scope>Exclusive</Scope>
>     <ExpirySettings>
>        <TimeOfDay ref="time_variable">expiration_time</TimeOfDay>
>        <TimeoutInSeconds ref="duration_variable">seconds_until_expiration</TimeoutInSeconds>
>        <ExpiryDate ref="date_variable">expiration_date</ExpiryDate>
>     </ExpirySettings>
>     <Source>cache-response</Source>
> </PopulateCache>
> 
> ```

> ### Note:  
> The element "TimeoutInSec" has been deprecated. It's now been replaced with "TimeoutInSeconds". Additionally, the use of the reference variable `ref="duration_variable"` is not supported with "TimeoutInSec" but works with "TimeoutInSeconds".
> 
> The ExpirySettings specifies when a cache entry should expire. When present, <TimeoutInSeconds\> overrides both <TimeOfDay\> and <ExpiryDate\>.

Populate cache policy defines the following elements:


<table>
<tr>
<th valign="top">

**Element**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

CacheKey

-   Prefix

-   KeyFragment




</td>
<td valign="top">

Configures a unique pointer to a piece of data stored in the cache.

-   Prefix: Specifies a value to use as a cache key prefix.

-   KeyFragment: Specifies a value that should be included in the cache key, creating a namespace for matching requests to cached responses.




</td>
</tr>
<tr>
<td valign="top">

CacheResource

</td>
<td valign="top">

Specifies the cache where messages should be stored. A default cache is available.

</td>
</tr>
<tr>
<td valign="top">

Scope

</td>
<td valign="top">

Enumeration used to construct a prefix for a cache key when a<Prefix\> element is not provided in the <CacheKey\>element.

</td>
</tr>
<tr>
<td valign="top">

ExpirySettings

-   ExpiryDate

-   TimeOfDay

-   TimeoutInSeconds




</td>
<td valign="top">

Specifies when the cached value should expire.

-   ExpiryDate: Specifies the date on which a cache entry should expire. Use the format mm-dd-yyyy.

-   TimeOfDay: The time of day at which a cache entry should expire. Use the format hh:mm:ss.

-   TimeoutInSeconds: The number of seconds after which a cache entry should expire.




</td>
</tr>
<tr>
<td valign="top">

Source

</td>
<td valign="top">

Specifies the variable whose value should be written to the cache.

</td>
</tr>
</table>

Populate cache policy type defines the following error codes:


<table>
<tr>
<th valign="top">

Error code

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

EntryCannotBeCached

</td>
<td valign="top">

An entry cannot be cached. The message object being cached is not an instance of a class that is Serializable.

</td>
</tr>
<tr>
<td valign="top">

InvalidCacheResourceReference

</td>
<td valign="top">

The cache specified in the <CacheResource\> element does not exist.

</td>
</tr>
<tr>
<td valign="top">

CacheNotFound

</td>
<td valign="top">

The cache specified in the <CacheResource\> element does not exist.

</td>
</tr>
</table>

Following fault variables is set when the policy triggers an error at runtime:

**Fault Variables**


<table>
<tr>
<th valign="top">

Variable Set

</th>
<th valign="top">

Where

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

\[prefix\].\[policy\_name\].failed

</td>
<td valign="top">

\[prefix\]: populatecache

\[policy\_name\]: The name of the policy to check.

</td>
<td valign="top">

populatecache.POP-CACHE-1.failed = true

</td>
</tr>
<tr>
<td valign="top">

fault.\[error\_name\]

</td>
<td valign="top">

\[error\_name\] = The specific error name to check for as listed in the table above.

</td>
<td valign="top">

fault.name Matches "EntryCannotBeCached"

</td>
</tr>
</table>

**Related Information**  


[Lookup Cache](lookup-cache-dcb1507.md "An OAuth access token is written to the cache using a Populate Cache policy. The OAuth token is retrieved for subsequent requests by a Lookup Cache policy.")

[Invalidate Cache](invalidate-cache-82fab59.md "The cache can be invalidated explicitly by specifying an HTTP header. When a request that contains the specified HTTP header is received, the cache will be flushed.")

[Response Cache](response-cache-8df3fac.md "")

