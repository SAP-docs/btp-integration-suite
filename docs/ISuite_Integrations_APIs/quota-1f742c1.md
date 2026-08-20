<!-- loio1f742c1e1a5c4a21bd83994071ddaea0 -->

# Quota

The Quota policy defines the number of request messages an application can submit to an API over a given period of time.

The period of time can be an hour, a day, or a month and so on. You can apply this policy on the context of request messages.

The Quota policy helps API Providers to restrict the number of calls made to an API. For example, you can restrict access to your applications by defining the number of API calls made as 20 per day or 20,000 over a period of one week.

API Management maintains a counter that keeps track of the number of calls made to the API. Once the counter reaches the Quota limit, all successive calls made to the API are rejected. API Management returns an error message to an API-call made after the Quota limit is exceeded. The Quota policy provides the capability to reset the counters automatically after the stipulated period of time, unless it is explicitly reset by using the Reset Quota policy.

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

FailedToResolveQuotaIntervalReference

</td>
<td valign="top">

Occurs if the **<Interval\>** element is not defined within the **Quota** policy. This element is mandatory and used to specify the interval of time applicable to the quota. The time interval can be minutes, hours, days, weeks, or months as defined with the **<TimeUnit\>** element.

</td>
</tr>
<tr>
<td valign="top">

FailedToResolveQuotaIntervalTimeUnitReference

</td>
<td valign="top">

Occurs if the **<TimeUnit\>** element is not defined within the **Quota** policy. This element is mandatory and used to specify the unit of time applicable to the quota. The time interval can be in minutes, hours, days, weeks, or months.

</td>
</tr>
<tr>
<td valign="top">

InvalidMessageWeight

</td>
<td valign="top">

Occurs if the value of the **<MessageWeight\>** element specified through a flow variable is invalid \(a non-integer value\).

</td>
</tr>
<tr>
<td valign="top">

QuotaViolation

</td>
<td valign="top">

The quota limit was exceeded.

</td>
</tr>
</table>

**Deployment Errors**


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

InvalidQuotaInterval

</td>
<td valign="top">

If the quota interval specified in the **<Interval\>** element is not an integer, then the deployment of the API proxy fails. For example, if the quota interval specified is 0.1 in the **<Interval\>** element, then the deployment of the API proxy fails.

</td>
</tr>
<tr>
<td valign="top">

InvalidQuotaTimeUnit

</td>
<td valign="top">

If the time unit specified in the **<TimeUnit\>** element is unsupported, then the deployment of the API proxy fails. The supported time units are **minute**, **hour**, **day**, **week**, and **month**.

</td>
</tr>
<tr>
<td valign="top">

InvalidQuotaType

</td>
<td valign="top">

If the type of the quota specified by the type attribute in the **<Quota\>** element is invalid, then the deployment of the API proxy fails. The supported quota types are **default**, **calendar**, **flexi**, and **rollingwindow**.

</td>
</tr>
<tr>
<td valign="top">

InvalidStartTime

</td>
<td valign="top">

If the format of the time specified in the **<StartTime\>** element is invalid, then the deployment of the API proxy fails. The valid format is **yyyy-MM-dd HH:mm:ss**, which is the ISO 8601 date and time format. For example, if the time specified in the **<StartTime\>** element is **7-16-2017 12:00:00**, then the deployment of the API proxy fails.

</td>
</tr>
<tr>
<td valign="top">

StartTimeNotSupported

</td>
<td valign="top">

If the **<StartTime\>** element is specified whose quota type is not **calendar** type, then the deployment of the API proxy fails. The **<StartTime\>** element is supported only for the calendar quota type. For example, if the type attribute is set to **flexi** or **rolling window** in the **<Quota\>** element, then the deployment of the API proxy fails.

</td>
</tr>
<tr>
<td valign="top">

InvalidTimeUnitForDistributedQuota

</td>
<td valign="top">

If the **<Distributed\>** element is set to **true** and the **<TimeUnit\>** element is set to **second**, then the deployment of the API proxy fails. The timeunit **second** is invalid for a distributed quota.

</td>
</tr>
<tr>
<td valign="top">

InvalidSynchronizeIntervalForAsyncConfiguration

</td>
<td valign="top">

If the value specified for the **<SyncIntervalInSeconds\>** element within the **<AsynchronousConfiguration\>** element in a **Quota** policy is less than zero, then the deployment of the API proxy fails.

</td>
</tr>
<tr>
<td valign="top">

InvalidAsynchronizeConfigurationForSynchronousQuota

</td>
<td valign="top">

If the value of the **<AsynchronousConfiguration\>** element is set to **true** in a **Quota** policy, which also has asynchronous configuration defined using the **<AsynchronousConfiguration\>** element, then the deployment of the API proxy fails.

</td>
</tr>
</table>

Following fault variables are set when the policy triggers an error at runtime:


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

fault.name=\[fault\_name\]

</td>
<td valign="top">

\[fault\_name\] = The specific error name to check for as listed in the table above. The fault name is the last part of the fault code.

</td>
<td valign="top">

fault.name = "QuotaViolation"

</td>
</tr>
<tr>
<td valign="top">

ratelimit.\[policy\_name\].failed

</td>
<td valign="top">

The \[policy\_name\] is the user-specified name of the policy that threw the fault.

</td>
<td valign="top">

ratelimit.QT-QuotaPolicy.failed = true

</td>
</tr>
</table>

Following is an example of an error response:

> ### Sample Code:  
> Example
> 
> ```
> {  
>    "fault":{  
>       "detail":{  
>          "errorcode":"policies.ratelimit.QuotaViolation"
>       },
>       "faultstring":"Rate limit quota violation. Quota limit  exceeded. Identifier : _default"
>    }
> }
> ```

Following is an example of a fault rule:

> ### Sample Code:  
> Example
> 
> ```
> <FaultRules>
>     <FaultRule name="Quota Errors">
>         <Step>
>             <Name>JavaScript-1</Name>
>             <Condition>(fault.name Matches "QuotaViolation") </Condition>
>         </Step>
>         <Condition>ratelimit.Quota-1.failed=true</Condition>
>     </FaultRule>
> </FaultRules>
> ```

**Related Information**  


[Types of Quota](types-of-quota-3e32f19.md "")

[Static and Dynamic Settings](static-and-dynamic-settings-f21c01f.md "A Quota can be static or dynamic.")

[Designing Quota Policy](designing-quota-policy-2539fb2.md "")

