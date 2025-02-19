<!-- loiocb606e30e4844d51bbaed6cd0fccea99 -->

# Understanding Quota Counters

By default, a Quota policy maintains a single counter, regardless of the number of times it is referenced in an API proxy. The name of the quota counter is based on the name attribute of the policy.

For example, if you create a Quota policy named **`MyQuotaPolicy`** with a limit of 5 requests and place it on multiple flows \(Flow A, B, and C\) in the API proxy. Even though it is used in multiple flows, it maintains a single counter that is updated by all instances of the policy:

-   **Flow A** is executed →**MyQuota Policy** is executed and its counter = 1
-   **Flow B** is executed →**MyQuota Policy** is executed and its counter = 2
-   **Flow A** is executed →**MyQuota Policy** is executed and its counter = 3
-   **Flow C** is executed →**MyQuota Policy** is executed and its counter = 4
-   **Flow A** is executed →**MyQuota Policy** is executed and its counter = 5

The next request to any of the three flows is rejected because the quota counter has reached its limit.

You can define multiple Quota policies in your API proxy and use a different policy in each flow. Each Quota policy maintains its own counter, based on the `name` attribute of the policy. You can also use the `<Class>` or `<Identifier>` elements in the Quota policy to define multiple, unique counters in a single policy. By using these elements, a single policy can maintain different counters based on the app making the request, the app developer making the request, a client ID or other client identifier, and more.

> ### Note:  
> Quota counters are scoped to the API proxy that contains the Quota policy. If multiple API proxies contain Quota policies with the same name, the counters are maintained separately.

**Related Information**  


[Understanding Quota Time Notation](understanding-quota-time-notation-5e2f272.md "All Quota times are set to the Coordinated Universal Time (UTC) time zone.")

[Quota](quota-1f742c1.md "The Quota policy defines the number of request messages an application can submit to an API over a given period of time.")

