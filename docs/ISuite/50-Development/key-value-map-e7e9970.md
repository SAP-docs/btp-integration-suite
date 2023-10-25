<!-- copye7e99707ecbe4be498b917f19441e5c0 -->

# Key Value Map

A key value map lets you create and manage collections of arbitrary key value pairs for any number of API proxies. Each key value pair is stored in a map as an entry.

> ### Note:  
> It’s recommended that you avoid making any concurrent inserts and updates to the same key value map \(KVM\) scoped to the environment level as it may cause loss of data.
> 
> As a work-around, use API proxy scoped key value map.

> ### Caution:  
> Don’t use Key Value Maps to store your logs as this can impact API proxy runtime flow. Instead, use the message logging policy to write your logs to external endpoints.

**Related Information**  


[API Providers](api-providers-deafe3b.md "An API provider defines the connection details for services running on specific hosts whose details you want to access.")

[Manage Certificates](manage-certificates-88fe03d.md "By using certificates, you can ensure that whenever a call is made to your API, there’s a certificate attached to it that confirms the identity of the caller and only if you recognize this identity the API can be processed and return data can be provided.")

