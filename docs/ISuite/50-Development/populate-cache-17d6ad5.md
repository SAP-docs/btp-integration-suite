<!-- loio17d6ad5ceb944c20ac26291c0698e0ea -->

# Populate Cache

An OAuth access token is written to the cache using a PopulateCache policy. The OAuth token is retrieved for subsequent requests by a LookupCache policy.

At runtime, the <PopulateCache\> policy writes data from the variable you specified in the <Source\> element to the cache you specified in the <CacheResource\> element. You can use the <CacheKey\>, <Scope\>, and <Prefix\> elements to specify a key that you can use from the <LookupCache\> policy to retrieve the value. Use the <ExpirySettings\> element to configure when the cached value should expire.

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
>         <TimeoutInSec>300</TimeoutInSec>
>     </ExpirySettings>
>     <Source>cache-response</Source>
> </PopulateCache>
> 
> ```

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



</td>
<td valign="top">

Configures a unique pointer to a piece of data stored in the cache.



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



</td>
<td valign="top">

Specifies when the cached value should expire.



</td>
</tr>
<tr>
<td valign="top">

ExpiryDate



</td>
<td valign="top">

Specifies the date on which a cache entry should expire. Use the format mm-dd-yyyy.



</td>
</tr>
<tr>
<td valign="top">

TimeOfDay



</td>
<td valign="top">

The time of day at which a cache entry should expire. Use the format hh:mm:ss.



</td>
</tr>
<tr>
<td valign="top">

TimeoutInSec



</td>
<td valign="top">

The number of seconds after which a cache entry should expire.



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

<a name="loio17d6ad5ceb944c20ac26291c0698e0ea__table_c4m_r25_h1b"/>Fault Variables


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

