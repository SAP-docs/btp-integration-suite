<!-- loio2539fb236c444c24b70df8db8cd732a3 -->

# Designing Quota Policy

You can attach this policy in the following locations:![](images/flow_policy_3_fad1208.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> 
> <Quota type="calendar" async="true" continueOnError="true" enabled="true"> 
> 	<Identifier ref="{ref}"></Identifier> 
> 	<MessageWeight ref="{ref}"></MessageWeight>  
> 	<Allow count="{count}" countRef="{countref}">  
> 	</Allow> 
> 	<SyncIntervalInSeconds>{value}</SyncIntervalInSeconds> 
> 	<SyncMessageCount>{count}</SyncMessageCount> 
> 	</AsynchronousConfiguration> 
> 	<Interval ref="{ref}" type="{type}"></Interval> 
> 	<Distributed>true</Distributed> 
> 	<PreciseAtSecondsLevel>true</PreciseAtSecondsLevel> 
> 	<StartTime>{time}</StartTime> 
> 	<Synchronous>true</Synchronous>  
> 	<TimeUnit ref="{ref}" type="{type}"></TimeUnit>
> </Quota> 
> ```


<table>
<tr>
<th valign="top">

**Elements & Attributes**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

StartTime \(Mandatory\)

</td>
<td valign="top">

Use this attribute only for Quota policies of type calendar. Indicates the date and time when the Quota counter begins counting \(regardless of whether or not any requests have been received from any applications.\) This value is in UTC.

Valid value: date and time, for example 2015-02-09 00:00:00.

</td>
</tr>
<tr>
<td valign="top">

Interval \(Mandatory\)



</td>
<td valign="top">

Specifies the interval of time \(in hours, minutes, or days as defined by TimeUnit\) applicable to the Quota. For example, a value of 24 for the Interval with a TimeUnit of hours means that the Quota is calculated over one day \(24 hours\).

Valid value: integer

The ref attribute identifies the variable that provides the value of the Interval.

</td>
</tr>
<tr>
<td valign="top">

TimeUnit \(Mandatory\)

</td>
<td valign="top">

Valid values: second, minute, hour, day, or month

The ref attribute identifies the variable that provides the value of the TimeUnit.

</td>
</tr>
<tr>
<td valign="top">

Allow \(Mandatory\)

</td>
<td valign="top">

Specifies the maximum number of inbound requests.

</td>
</tr>
<tr>
<td valign="top">

count \(Optional\)

</td>
<td valign="top">

Specifies a message count for the quota.

For example, a value of 200 for the Allow count with duration of 1 month means that the quota is set to be 200 messages per month.

Valid value: integer

Default Value: 2000

</td>
</tr>
<tr>
<td valign="top">

countRef \(Optional\)

</td>
<td valign="top">

This attribute identifies the variable that provides the value of the Quota limit.

If a count reference is specified, it takes precedence over the Allow count value.

Example:

The element Allow count="2000"

`countRef="request.header.allowed_quota"/> has a count header (countRef="request.header.allowed_quota")` along with the count value of 2000.

</td>
</tr>
<tr>
<td valign="top">

Identifier \(Optional\)

</td>
<td valign="top">

The variable used to uniquely identify the client application is referred to as the "Identifier". The "ref" attribute is used to specify the variable that contains the value of the Identifier. If the "ref" attribute is not used, the policy will utilize a single counter that is applied to the quota.

</td>
</tr>
<tr>
<td valign="top">

MessageWeight \(Optional\)

</td>
<td valign="top">

Specifies the weight defined for each message.

Message weight is used to increase impact of request messages that, for example, consume more computational resources than others. For example, you may want to calculate POST messages as being twice as expensive as GET messages. A value representing MessageWeight can be extracted from HTTP headers, query parameters, or an XML or JSON request payload.

</td>
</tr>
<tr>
<td valign="top">

Distributed

</td>
<td valign="top">

When set to true, a central counter is maintained that is continuously updated by all API Management servers.

Note: Always set this value to true.

</td>
</tr>
<tr>
<td valign="top">

PreciseAtSecondsLevel

</td>
<td valign="top">

The default precision for Quotas intervals is one minute. When set to true,

Quota precision is set to record at intervals of one second. Use this setting when you have a Quota that uses minutes as the TimeUnit, and you need to ensure that Quotas are counted and enforced by seconds.

Valid values: true or false

</td>
</tr>
<tr>
<td valign="top">

Synchronous

</td>
<td valign="top">

This setting determines how the distributed Quota counter is updated. If set to true, the quota counter is updated in the central repository synchronously. This means that the update is made at the same time the

API call is quota-checked. When synchronous is set to true, you are guaranteed that no API calls over the quota will be allowed.

Note: Always set this value to true.

</td>
</tr>
<tr>
<td valign="top">

AsynchronousConfiguration\(Optional\)



</td>
<td valign="top">

This configuration element is only required when Synchronous is set to false. This element enables you to configure the synchronization interval among distributed Quota counters. The default synchronous update interval is 10 seconds. You can modify this by adding the child element SyncIntervalInSeconds.

Example

> ### Sample Code:  
> ```
> 
> <Synchronous>false</Synchronous>
> <AsynchronousConfiguration>
> <SyncIntervalInSeconds>15</SyncIntervalInSeconds>
> </AsynchronousConfiguration> 
> ```

Alternatively, you can use the SyncMessageCount option instead, but you cannot use both. SyncMessageCount specifies the number of requests across all API Management message processors between quota updates. The following example specifies that the quota count is updated every 10 requests across all API Management message processors:

> ### Sample Code:  
> ```
> 
> <Synchronous>false</Synchronous>
> <AsynchronousConfiguration>
> <SyncMessageCount>10</SyncMessageCount>
> </AsynchronousConfiguration>
> ```



</td>
</tr>
</table>



<a name="loio2539fb236c444c24b70df8db8cd732a3__section_jpt_gf1_fgc"/>

## Flow variables

The following predefined flow variables are automatically populated when a Quota policy executes. For more information, see [Flow Variables](flow-variables-47f27da.md).


<table>
<tr>
<th valign="top">

Variables

</th>
<th valign="top">

Type

</th>
<th valign="top">

Permissions

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.allowed.count\>* 

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns the allowed quota count.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.used.count\>* 

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns the current quota used within a quota interval.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.available.count\>* 

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns the available quota count in the quota interval.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.exceed.count\>* 

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns 1 after the quota is exceeded.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.total.exceed.count\>* 

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns 1 after the quota is exceeded.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.expiry.time\>* 

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns the UTC time in milliseconds which determines when the quota expires and new quota interval starts.

When the Quota policy type is rollingwindow, this value is not valid because the quota interval never expires.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.identifier\>* 

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns the \(client\) identifier reference attached to the policy.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.class\>* 

</td>
<td valign="top">

String

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns the class associated with the client identifier.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.class.allowed.count\>* 

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns the allowed quota count defined in the class.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.class.used.count\>* 

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns the used quota within a class.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.class.available.count\>* 

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns the available quota count in the class.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.class.exceed.count\>* 

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns the count of requests that exceeds the limit in the class in the current quota interval.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.class.total.exceed.count\>* 

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Returns the total count of requests that exceeds the limit in the class across all quota intervals, so it is the sum of **class.exceed.count** for all quota intervals.

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.\{policy\_name\}.failed\>* 

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

Read-only

</td>
<td valign="top">

Indicates whether or not the policy failed \(true or false\).

</td>
</tr>
</table>



<a name="loio2539fb236c444c24b70df8db8cd732a3__section_d2l_ch1_fgc"/>

## Error reference

This section explains the fault codes and error messages that are returned, and fault variables set by API Management when this policy triggers an error. This information is essential for developing fault rules to handle faults.



### Runtime errors

The table below lists the errors that may occur during policy execution:


<table>
<tr>
<th valign="top">

Fault code

</th>
<th valign="top">

HTTP status

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

`policies.ratelimit.FailedToResolveQuotaIntervalReference` 

</td>
<td valign="top">

500

</td>
<td valign="top">

Occurs if the `<Interval>` element is not defined within the Quota policy. This element is mandatory and used to specify the interval of time applicable to the quota. The time interval can be minutes, hours, days, weeks, or months as defined with the `<TimeUnit>` element.

</td>
</tr>
<tr>
<td valign="top">

`policies.ratelimit.FailedToResolveQuotaIntervalTimeUnitReference` 

</td>
<td valign="top">

500

</td>
<td valign="top">

Occurs if the `<TimeUnit>` element is not defined within the Quota policy. This element is mandatory and used to specify the unit of time applicable to the quota. The time interval can be in minutes, hours, days, weeks, or months.

</td>
</tr>
<tr>
<td valign="top">

`policies.ratelimit.InvalidMessageWeight` 

</td>
<td valign="top">

500

</td>
<td valign="top">

Occurs if the value of the `<MessageWeight>` element specified through a flow variable is invalid \(a non-integer value\).

</td>
</tr>
<tr>
<td valign="top">

`policies.ratelimit.QuotaViolation` 

</td>
<td valign="top">

500

</td>
<td valign="top">

The quota limit was exceeded.

</td>
</tr>
</table>



### Deployment errors


<table>
<tr>
<th valign="top">

Error name

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

`InvalidQuotaInterval` 

</td>
<td valign="top">

If the quota interval specified in the `<Interval>` element is not an integer, then the deployment of the API proxy fails. For example, if the quota interval specified is 0.1 in the `<Interval>` element, then the deployment of the API proxy fails.

</td>
</tr>
<tr>
<td valign="top">

`InvalidQuotaTimeUnit` 

</td>
<td valign="top">

If the time unit specified in the `<TimeUnit>` element is unsupported, then the deployment of the API proxy fails. The supported time units are **minute**, **hour**, **day**, **week**, and **month**.

</td>
</tr>
<tr>
<td valign="top">

`InvalidQuotaType` 

</td>
<td valign="top">

If the type of the quota specified by the **type** attribute in the `<Quota>` element is invalid, then the deployment of the API proxy fails. The supported quota types are **default**, **calendar**, **flexi**, and **rollingwindow**.

</td>
</tr>
<tr>
<td valign="top">

`InvalidStartTime` 

</td>
<td valign="top">

If the format of the time specified in the `<StartTime>` element is invalid, then the deployment of the API proxy fails. The valid format is **yyyy-MM-dd HH:mm:ss**, which is the ISO 8601 date and time format. For example, if the time specified in the `<StartTime>` element is **8-15-2024 12:00:00**, then the deployment of the API proxy fails.

</td>
</tr>
<tr>
<td valign="top">

`StartTimeNotSupported` 

</td>
<td valign="top">

If the `<StartTime>` element is specified whose quota type is not **calendar** type, then the deployment of the API proxy fails. The `<StartTime>` element is supported only for the **calendar** quota type. For example, if the type attribute is set to **flexi** or **rolling window** in the `<Quota>` element, then the deployment of the API proxy fails.

</td>
</tr>
<tr>
<td valign="top">

`InvalidTimeUnitForDistributedQuota` 

</td>
<td valign="top">

If the `<Distributed>` element is set to **true** and the **<TimeUnit\>** element is set to **second**, then the deployment of the API proxy fails. The timeunit **second** is invalid for a distributed quota.

</td>
</tr>
<tr>
<td valign="top">

`InvalidSynchronizeIntervalForAsyncConfiguration` 

</td>
<td valign="top">

If the value specified for the `<SyncIntervalInSeconds>` element within the `<AsynchronousConfiguration>` element in a Quota policy is less than zero, then the deployment of the API proxy fails.

</td>
</tr>
<tr>
<td valign="top">

`InvalidAsynchronizeConfigurationForSynchronousQuota` 

</td>
<td valign="top">

If the value of the `<AsynchronousConfiguration>` element is set to **true** in a Quota policy, which also has asynchronous configuration defined using the `<AsynchronousConfiguration>` element, then the deployment of the API proxy fails.

</td>
</tr>
</table>



<a name="loio2539fb236c444c24b70df8db8cd732a3__section_jwn_jk1_fgc"/>

## Fault variables

The table below outlines the variables that are set when this policy triggers an error:


<table>
<tr>
<th valign="top">

Variables

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

*<fault.name="fault\_name"\>* 

</td>
<td valign="top">

*<fault\_name\>* is the name of the fault, as listed in the **Runtime errors** table above. The fault name is the last part of the fault code.

</td>
<td valign="top">

`fault.name Matches "QuotaViolation"` 

</td>
</tr>
<tr>
<td valign="top">

*<ratelimit.policy\_name.failed\>* 

</td>
<td valign="top">

*<policy\_name\>* is the user-specified name of the policy that threw the fault.

</td>
<td valign="top">

`ratelimit.QT-QuotaPolicy.failed = true` 

</td>
</tr>
</table>



### Error response example:

```
{  
   "fault":{  
      "detail":{  
         "errorcode":"policies.ratelimit.QuotaViolation"
      },
      "faultstring":"Rate limit quota violation. Quota limit  exceeded. Identifier : _default"
   }
}
```



### Fault rule example:

```
<FaultRules>
    <FaultRule name="Quota Errors">
        <Step>
            <Name>JavaScript-1</Name>
            <Condition>(fault.name Matches "QuotaViolation") </Condition>
        </Step>
        <Condition>ratelimit.Quota-1.failed=true</Condition>
    </FaultRule>
</FaultRules>
```

**Related Information**  


[Quota](quota-1f742c1.md "The Quota policy defines the number of request messages an application can submit to an API over a given period of time.")

[Reset Quota](reset-quota-e18ccb8.md "The Reset Quota policy enables you to reset the limit for a specified Quota policy.")

[Spike Arrest](spike-arrest-bf441dc.md "The Spike Arrest policy limits the number of requests forwarded from the point in the processing flow where the policy is attached as a processing step.")

