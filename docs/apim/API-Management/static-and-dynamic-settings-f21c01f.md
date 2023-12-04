<!-- loiof21c01fdfdbd4c8ab48c4f1a76f71d3a -->

# Static and Dynamic Settings

A Quota can be static or dynamic.



## Static Settings

For a static quota, you provide a count, a time interval, and a time unit. In the example below, the application accepts 5000 requests per week.

> ### Sample Code:  
> ```
> 
> <Quota>
> 	<Allow count="5000"/>
> 	<Interval>1</Interval>
> 	<TimeUnit>week</TimeUnit>
> </Quota>
> ```



## Dynamic Settings

Dynamic Quotas enable you to configure a single Quota policy that enforces different Quota settings for different applications; based on the identity of the requesting application. Dynamic Quota values are populated at runtime by resolving an application identifier to an API product. The Identifier can be a field in the request that is unique to each application. For API proxies where OAuth is enforced, you can use `consumer_id` as the Identifier, as demonstrated in the sample policy below:

> ### Sample Code:  
> ```
> 
> <Quota>
> 	<Intervalref="apiproduct.developer.quota.interval"/>
> 	<TimeUnit ref="apiproduct.developer.quota.timeunit"/>
> 	<Allow countRef="apiproduct.developer.quota.limit"/>
> 	<Identifier ref=" consumer_id"/>
> </Quota>
> ```

The example above uses the variable `consumer_id`to identify the requesting application. This works as long as the request message contains a `consumer_id` \(associated with an OAuth-enabled request\).

**Related Information**  


[Designing Quota Policy](designing-quota-policy-2539fb2.md "")

