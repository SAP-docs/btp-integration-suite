<!-- loio3722a394e4364711b2b176f6f5b976ed -->

# Key Value Map

A key value map lets you create and manage collections of arbitrary key value pairs for any number of API proxies. Each key value pair is stored in a map as an entry.

> ### Note:  
> It’s recommended that you avoid making any concurrent inserts and updates to the same key value map \(KVM\) scoped to the environment level as it may cause loss of data.
> 
> As a work-around, use API proxy scoped key value map.

> ### Caution:  
> Don’t use Key Value Maps to store your logs as this can impact API proxy runtime flow. Instead, use the message logging policy to write your logs to external endpoints.

> ### Note:  
> Key names in Key Value Maps don't allow trailing spaces. When you create key names, always check that you haven't included unintended spaces at the end.

