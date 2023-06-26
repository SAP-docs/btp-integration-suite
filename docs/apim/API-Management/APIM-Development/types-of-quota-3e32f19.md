<!-- loio3e32f1938a964d29a66987e7a5240161 -->

# Types of Quota

Quota type is an attribute of the Quota policy that you define while configuring the policy. API Management supports the following three types of Quota:

-    `calendar` type of Quota. For example, `<Quota name="DemoQuota" type="calendar">`

    In the calendar Quota, you explicitly provide a start time. The counter starts the count from the specified start date. The Quota counter is refreshed based on the Interval and TimeUnit that you set. For example, the following Quota of type calendar begins counting at 8.30 am on June 26, 2015, and will refresh once in every 20 minutes.

    > ### Sample Code:  
    > ```
    > 
    > <Quota type="calendar">
    > 	<Identifier ref="request.header.clientId"/>
    > 	<StartTime>2015-06-26 08:30:00</StartTime>
    > 	<Interval>20</Interval>
    > 	<TimeUnit>minute</TimeUnit>
    > 	<Allow count="99"/>
    > 	<MessageWeight ref="request.header.weight"/>
    > 	<Distributed>true</Distributed>
    > 	<Synchronous>true</Synchronous>
    > </Quota>
    > ```

    > ### Note:  
    > If the type is not mentioned, then the Quota defaults to `calendar` type.

    `rollingwindow`: A "rolling window" counter advances by the time interval that you specify. You do not specify a StartTime; instead, the StartTime for the counter is the time when the first message is received from the client plus the interval that you define. A counter is kept for each client ID \(consumer key\). Thus, the counter will reset to zero when the Interval you define has passed. This enables you to configure a Quota in which an app is indefinitely allowed 1000 requests every 24 hours.

    `flexi`: Flexible Quota enforcement causes the counter to begin when the first request message is received from an app. Under flexible Quota enforcement, StartTime is dynamic; every app has its own StartTime based on the time when the first request is received. This enables you to provide Quotas that support one week, one month, or 6 months access to your API, customized for each app.


**Related Information**  


[Static and Dynamic Settings](static-and-dynamic-settings-f21c01f.md "A Quota can be static or dynamic.")

[Designing Quota Policy](designing-quota-policy-2539fb2.md "")

