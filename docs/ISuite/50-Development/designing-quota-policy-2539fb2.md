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

**Related Information**  


[Quota](quota-1f742c1.md "The Quota policy defines the number of request messages an application can submit to an API over a given period of time.")

[Reset Quota](reset-quota-e18ccb8.md "The Reset Quota policy enables you to reset the limit for a specified Quota policy.")

[Spike Arrest](spike-arrest-bf441dc.md "The Spike Arrest policy limits the number of requests forwarded from the point in the processing flow where the policy is attached as a processing step.")

