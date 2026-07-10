<!-- loio8df3fac998f74e0ebd5e8355588057b3 -->

# Response Cache

This policy helps in caching data from a backend resource, thus reducing the number of requests to the resource. When applications make requests to the same URI, use this policy to return cached responses instead of forwarding all the requests to the backend server. This results in improving your API's performance through reduced latency and network traffic.

> ### Note:  
> To cache data from a backend resource, you must add the Response Cache policy twice in the processing pipeline: once in the PreFlow and once in the PostFlow. There is a restriction that allows attaching it only once in each of these flows.

ResponseCache is useful in cases where the backend data used by your API is updated only periodically.

The maximum size for each cached object is 512 kb. You can configure the ResponseCache policy to include HTTP response headers in setting cache entry expiration and cache keys.

You can attach this policy in the following locations:![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> 
>  <ResponseCache async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>                 <CacheKey><Prefix/>
>                	<KeyFragment ref=\"request.uri\" type=\"string\"/>
>                 </CacheKey>
> 				  <Scope>Exclusive</Scope>
>                 <ExpirySettings><ExpiryDate/><TimeOfDay/>
>                 	<TimeoutInSeconds ref="">60</TimeoutInSeconds>
>                 </ExpirySettings>
>                 <SkipCacheLookup>request.header.bypass-cache = \"true\"</SkipCacheLookup>
>                 <SkipCachePopulation/>
> </ResponseCache>
> 
> ```

> ### Note:  
> The element "TimeoutInSec" has been deprecated. It's now been replaced with "TimeoutInSeconds". Additionally, the use of the reference variable `ref="duration_variable"` is not supported with "TimeoutInSec" but works with "TimeoutInSeconds".


<table>
<tr>
<th valign="top">

**Elements & Attributes**

</th>
<th valign="top">

 

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top" colspan="2">

DisplayName \(Optional\)

</td>
<td valign="top">

Label the policy with a different \(from the name attribute\), natural-language name. Use this in addition to the name attribute.

If you omit this element, the value of the name attribute is used.

Syntax: `<DisplayName>Policy Display Name</DisplayName>`

</td>
</tr>
<tr>
<td valign="top" colspan="2">

CacheLookupTimeoutInSeconds \(Optional\)

</td>
<td valign="top">

This element indicates the number of seconds after which an unsuccessful cache search is considered as a missed cache.

Syntax: `<CacheLookupTimeoutInSeconds>60</CacheLookupTimeoutInSeconds>`

</td>
</tr>
<tr>
<td valign="top" colspan="2">

CacheResource \(Optional\)

</td>
<td valign="top">

This element indicates the cache where messages are stored. To use the included shared cache, skip this element.

To administratively clear entries present in the cache, specify a CacheResource by name.

Syntax: `<CacheResource>my_cache_reserve</CacheResource>`

</td>
</tr>
<tr>
<td valign="top" colspan="2">

ExcludeErrorResponse \(Optional\)

</td>
<td valign="top">

The response cache policy currently caches both success and error HTTP responses by default.

The default value is `false`. If you want to exclude caching target responses with HTTP error status codes, set this element to `true`, in which case only responses with status codes from 200 to 205 \(success codes\) are cached.

Syntax: `<ExcludeErrorResponse>true</ExcludeErrorResponse>`

</td>
</tr>
<tr>
<td valign="top" colspan="2">

SkipCacheLookup \(Optional\)

</td>
<td valign="top">

This element \(if the value evaluates to `true`\) indicates that cache lookup should be skipped and the cache should be refreshed.

Syntax: `<SkipCacheLookup>variable-condition</SkipCacheLookup>`

In the following example, the variable for bypass-cache is set to true, indicating that in an incoming header, the cache lookup is skipped and the cache is refreshed.

Example: `<SkipCacheLookup>request.header.bypass-cache = "true"</SkipCacheLookup>`

</td>
</tr>
<tr>
<td valign="top" colspan="2">

SkipCachePopulation \(Optional\)

</td>
<td valign="top">

This element \(if the value evaluates to `true`\) indicates that a write to the cache should be skipped.

Syntax: `<SkipCachePopulation>variable-condition</SkipCachePopulation>`

In the following example, write to cache is skipped if the response status code is 200 or higher.

Example: `<SkipCachePopulation>response.status.code >= 200</SkipCachePopulation>`

</td>
</tr>
<tr>
<td valign="top" colspan="2">

UseAcceptHeader \(Optional\)

</td>
<td valign="top">

This element \(if set to `true`\) indicates that the response cache entry's cache key is appended with values from response accept headers.

The following request headers are used while calculating the cache key:

-   Accept
-   Accept-Language
-   Accept-Charset
-   Accept-Encoding

Syntax: `<UseAcceptHeader>false</UseAcceptHeader>`

</td>
</tr>
<tr>
<td valign="top" colspan="2">

UseResponseCacheHeader \(Optional\)

</td>
<td valign="top">

This element \(if set to `true`\) indicates that HTTP response headers are considered while setting the `time to live` \(TTL\) of the response in the cache.

While setting TTL, the values of the following response headers are considered, and compared with the values set by the `ExpirySettings` element:

-   Cache-Control s-maxage
-   Cache-Control max-age
-   Expires

Syntax: `<UseResponseCacheHeaders>false</UseResponseCacheHeaders>`

</td>
</tr>
<tr>
<td valign="top" colspan="2">

Scope \(Optional\)

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

CacheKey \(Required\)

</td>
<td valign="top">

KeyFragment \(Optional\)

</td>
<td valign="top">

The CacheKey element creates a unique pointer to a piece of data stored in cache, and has a size-limit of 2 KB each. It has two elements, KeyFragment and Prefix.

The KeyFragment element indicates a value to be included in the cache key, in order to create a namepsace for matching requests to cached responses.

You can either provide a key \(a static name\) or a value \(a dynamic variable\) to the KeyFragment element. All the specified fragments combined \(including the prefix\) are concatenated to create the cache key.

> ### Sample Code:  
> Syntax
> 
> ```
> <KeyFragment ref="variable_name"/>
> <KeyFragment>string</KeyFragment>
> ```
> 
> Example:
> 
> ```
> <KeyFragment>AccessToken</KeyFragment>
> <KeyFragment ref="request_id" />
> ```
> 
> At runtime, the KeyFragment values are prepended with scope or prefix.
> 
> ```
> <CacheKey>
>     <Prefix>User_Key</Prefix>
>     <KeyFragment>AccessToken</KeyFragment>
>     <KeyFragment ref="request_id" />
> </CacheKey>
> ```



</td>
</tr>
<tr>
<td valign="top">

Prefix \(Optional\)

</td>
<td valign="top">

The Prefix element indicates a string value that is used as a cache key prefix.

Syntax: `<Prefix>prefix_string</Prefix>`

Use the prefix element along with the CacheKey and Scope elements \(prefix overrides scope\). If you want to specify your own value instead of a scope enumerated value, use prefix instead of scope.

If you define a prefix, it prepends the cache key for entries written to the cache.

> ### Sample Code:  
> Example
> 
> ```
> <CacheKey>
>     <Prefix>User_Key</Prefix>
>     <KeyFragment>AccessToken</KeyFragment>
>     <KeyFragment ref="request_id" />
> </CacheKey>
> ```



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

ExpirySettings \(Required\)

</td>
<td valign="top">

TimeoutInSeconds \(Optional\)

</td>
<td valign="top">

This element indicates when a cache entry should expire. It includes the TimeoutInSeconds, TimeOfDay, and ExpiryDate elements.

When present, "TimeoutInSeconds" overrides both TimeOfDay and ExpiryDate.

The "TimeoutInSeconds" element is a variable with timeout value, which indicates the number of seconds after which a cache entry should expire.

> ### Sample Code:  
> Syntax
> 
> ```
> <ExpirySettings>
>     <TimeoutInSeconds ref="duration_variable">seconds_to_expire</TimeoutInSeconds>
> </ExpirySettings>
> ```



</td>
</tr>
<tr>
<td valign="top">

TimeOfDay

</td>
<td valign="top">

This element is a variable with the expiration time value \(used in the format `hh.mm.ss`\), which indicates the time of the day when a cache entry should expire.

The default time depends on the locale and timezone, which vary according to where the code is running.

> ### Sample Code:  
> Syntax
> 
> ```
> <ExpirySettings>
>     <TimeOfDay ref="time_variable">time_of_expiration	</TimeOfDay>
> </ExpirySettings>
> ```



</td>
</tr>
<tr>
<td valign="top">

ExpiryDate

</td>
<td valign="top">

This element is a variable \(used in the format `mm-dd-yyyy`\) which indicates the date on which a cache entry should expire.

> ### Sample Code:  
> Syntax
> 
> ```
> <ExpirySettings>
>     <ExpiryDate ref="{date_variable}">date_of_expiration</ExpiryDate>
> </ExpirySettings>
> ```



</td>
</tr>
</table>

Some predefined flow variables that are populated when a ResponseCache policy is executed are described in the below table:

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

responsecache.\{policy\_name\}.cachename

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

This variable returns the cache used in the policy.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

This variable returns the cache key used in the policy.

</td>
</tr>
<tr>
<td valign="top">

responsecache.\{policy\_name\}.cachehit

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

True if the policy is executed successfully

</td>
</tr>
<tr>
<td valign="top">

responsecache.\{policy\_name\}.invalidentry

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

True if the cache entry is invalid

</td>
</tr>
</table>

Error messages that are seen when this policy triggers an error are described in the below table:responsecache.\{policy\_name\}.cachekey

**Error Messages**


<table>
<tr>
<th valign="top">

Error Name

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

InvalidTimeout

</td>
<td valign="top">

A negative number value was specified in the <CacheLookupTimeoutInSeconds\> element.

</td>
</tr>
<tr>
<td valign="top">

InvalidCacheResourceReference

</td>
<td valign="top">

The name specified in the <CacheResource\> element does not exist.

</td>
</tr>
<tr>
<td valign="top">

ResponseCacheStepAttachmentNotAllowedReq

</td>
<td valign="top">

The ResponseCache policy was attached more than once in the request path or to multiple request paths. For example, you cannot place it in both the Request PreFlow and PostFlow.

</td>
</tr>
<tr>
<td valign="top">

ResponseCacheStepAttachmentNotAllowedResp

</td>
<td valign="top">

The ResponseCache policy was attached to multiple response paths.

</td>
</tr>
<tr>
<td valign="top">

InvalidMessagePatternForErrorCode

</td>
<td valign="top">

The <SkipCacheLookup\> or the <SkipCachePopulation\> element in a ResponseCache policy contained an invalid condition.

</td>
</tr>
<tr>
<td valign="top">

CannotDeleteStepDefinition

</td>
<td valign="top">

You must detach the policy definition from the proxy flows before you can delete the policy.

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

[Lookup Cache](lookup-cache-dcb1507.md "An OAuth access token is written to the cache using a Populate Cache policy. The OAuth token is retrieved for subsequent requests by a Lookup Cache policy.")

[Invalidate Cache](invalidate-cache-82fab59.md "The cache can be invalidated explicitly by specifying an HTTP header. When a request that contains the specified HTTP header is received, the cache will be flushed.")

