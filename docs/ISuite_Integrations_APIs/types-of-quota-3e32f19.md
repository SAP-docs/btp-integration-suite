<!-- loio3e32f1938a964d29a66987e7a5240161 -->

# Types of Quota

Quota type is an attribute of the Quota policy that you define while configuring the policy. API Management supports the following three types of Quota:

-   `calendar` type of Quota. For example, `<Quota name="DemoQuota" type="calendar">`

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


Each quota type defines when the quota counter starts and when it resets, as shown in the following table:


<table>
<tr>
<th valign="top">

Time Unit

</th>
<th valign="top">

Default \(or null\) reset

</th>
<th valign="top">

Calendar reset

</th>
<th valign="top">

Flexi reset

</th>
</tr>
<tr>
<td valign="top">

minute

</td>
<td valign="top">

Start of next minute

</td>
<td valign="top">

One minute after `<StartTime>` 

</td>
<td valign="top">

One minute after first request

</td>
</tr>
<tr>
<td valign="top">

hour

</td>
<td valign="top">

Top of next hour

</td>
<td valign="top">

One hour after `<StartTime>` 

</td>
<td valign="top">

One hour after first request

</td>
</tr>
<tr>
<td valign="top">

day

</td>
<td valign="top">

Midnight GMT of the current day

</td>
<td valign="top">

24 hours after `<StartTime>` 

</td>
<td valign="top">

24 hours after first request

</td>
</tr>
<tr>
<td valign="top">

week

</td>
<td valign="top">

Midnight GMT Sunday at the end of the week

</td>
<td valign="top">

One week after `<StartTime>` 

</td>
<td valign="top">

One week after first request

</td>
</tr>
<tr>
<td valign="top">

month

</td>
<td valign="top">

Midnight GMT of the last day of the month

</td>
<td valign="top">

One month \(28 days\) after `<StartTime>` 

</td>
<td valign="top">

One month \(28 days\) after first request

</td>
</tr>
</table>

**Related Information**  


[Static and Dynamic Settings](static-and-dynamic-settings-f21c01f.md "A Quota can be static or dynamic.")

[Designing Quota Policy](designing-quota-policy-2539fb2.md "")

