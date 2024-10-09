<!-- loiodcb15076cbdf4ae198df8525732355c8 -->

# Lookup Cache

An OAuth access token is written to the cache using a Populate Cache policy. The OAuth token is retrieved for subsequent requests by a Lookup Cache policy.

At runtime, the LookupCache policy retrieves a value from the cache, assigning the value to the variable you specify with the AssignTo element \(if no value is retrieved, the variable will not be set\). It looks for the value based on a cache key created through configuration that combines the CacheKey and Scope elements. In other words, to retrieve a particular value-added to the cache by a PopulateCache policy, your LookupCache policy must have cache key-related elements configured in the same way as the PopulateCache policy.

You can retrieve cached values with the Lookup Cache policy.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <LookupCache async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <CacheKey>
>         <KeyFragment ref="request.header.userid"></KeyFragment>
>     </CacheKey>
>     <Scope>Exclusive</Scope>
>     <AssignTo>cache-response</AssignTo>
> </LookupCache>
> 
> ```


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

</td>
<td valign="top">

Configures a unique pointer to a piece of data stored in the cache.

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

Enumeration used to construct a prefix for a cache key when a Prefix element is not provided in the CacheKey element.The list of supported values are: Global, Application, Proxy, Target, and Exclusive.

</td>
</tr>
<tr>
<td valign="top">

AssignTo

</td>
<td valign="top">

Specifies the variable where the cache entry is assigned after it has been retrieved from the cache.

</td>
</tr>
<tr>
<td valign="top">

Prefix

</td>
<td valign="top">

Specifies a value to use as a cache key prefix.

</td>
</tr>
<tr>
<td valign="top">

KeyFragment

</td>
<td valign="top">

Specifies a value that should be included in the cache key, creating a namespace for matching requests to cached responses.

</td>
</tr>
</table>

The following predefined Flow variables are available after you customize the behavior of the cache you define in a Lookup Cache policy.

**Flow Variables**


<table>
<tr>
<th valign="top">

Variables

</th>
<th valign="top">

Type

</th>
<th valign="top">

Permission

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

lookupcache.\{policy-name\}.cachename

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

Returns the cache name used in the policy.

</td>
</tr>
<tr>
<td valign="top">

lookupcache.\{policy-name\}.cachekey

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

Returns the key used.

</td>
</tr>
<tr>
<td valign="top">

lookupcache.\{policy-name\}.cachehit

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

True if the policy found a value for the specified cache key.

</td>
</tr>
<tr>
<td valign="top">

lookupcache.\{policy-name\}.assignto

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

Returns the variable to which cache is assigned.

</td>
</tr>
</table>

Lookup Cache policy type defines the following error codes:


<table>
<tr>
<th valign="top">

Error code

</th>
<th valign="top">

Occurs when

</th>
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

InvalidTimeout

</td>
<td valign="top">

The CacheLookupTimeoutInSeconds value must be greater than zero.

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

**Related Information**  


[Populate Cache](populate-cache-17d6ad5.md "An OAuth access token is written to the cache using a Populate Cache policy. The OAuth token is retrieved for subsequent requests by a Lookup Cache policy.")

[Invalidate Cache](invalidate-cache-82fab59.md "The cache can be invalidated explicitly by specifying an HTTP header. When a request that contains the specified HTTP header is received, the cache will be flushed.")

[Response Cache](response-cache-8df3fac.md "")

