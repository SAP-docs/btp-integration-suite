<!-- loio82fab59f830d41adbf70345cb85d0263 -->

# Invalidate Cache

The cache can be invalidated explicitly by specifying an HTTP header. When a request that contains the specified HTTP header is received, the cache will be flushed.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <!-- The policy will clear the value of userId from the cache -->
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <InvalidateCache async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <CacheKey>
>         <KeyFragment ref="request.header.userid"></KeyFragment>
>     </CacheKey>
>     <Scope>Exclusive</Scope>
>     <PurgeChildEntries>true</PurgeChildEntries>
> </InvalidateCache>
> ```

Invalidate Cache policy defines the following attributes that are common to all policy parent elements:


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Description

</th>
<th valign="top">

Default

</th>
<th valign="top">

Presence

</th>
</tr>
<tr>
<td valign="top">

name

</td>
<td valign="top">

The internal name of the policy. Characters you can use in the name are restricted to: A-Z 0-9.\_\\-$ %.

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Required

</td>
</tr>
<tr>
<td valign="top">

continueOnError

</td>
<td valign="top">

Set to false to return an error when a policy fails. This is expected behavior for most policies.

Set to true to have flow execution continue even after a policy fails.

</td>
<td valign="top">

false

</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

enabled

</td>
<td valign="top">

Set to true to enforce the policy.

Set to false to "turn off" the policy. The policy will not be enforced even if it remains attached to a flow.

</td>
<td valign="top">

true

</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

async

</td>
<td valign="top">

This attribute is deprecated.

</td>
<td valign="top">

false

</td>
<td valign="top">

Deprecated

</td>
</tr>
</table>


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

Enumeration used to construct a prefix for a cache key when a <Prefix\> element is not provided in the <CacheKey\> element.

</td>
</tr>
<tr>
<td valign="top">

CacheContext

</td>
<td valign="top">

Specifies how to construct a cache key when a <Prefix\> element value is not specified, or to clear cache entries added by another API proxy.

</td>
</tr>
<tr>
<td valign="top">

PurgeChildEntries

</td>
<td valign="top">

true to purge child cache entries when invalidating the cache. Default is false.

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

During the policy execution, the following errors can occur:


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

**Related Information**  


[Populate Cache](populate-cache-17d6ad5.md "An OAuth access token is written to the cache using a Populate Cache policy. The OAuth token is retrieved for subsequent requests by a Lookup Cache policy.")

[Lookup Cache](lookup-cache-dcb1507.md "An OAuth access token is written to the cache using a Populate Cache policy. The OAuth token is retrieved for subsequent requests by a Lookup Cache policy.")

[Response Cache](response-cache-8df3fac.md "")

