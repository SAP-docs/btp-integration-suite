<!-- loiobf441dc839034613b059cb508ad610f7 -->

# Spike Arrest

The Spike Arrest policy limits the number of requests forwarded from the point in the processing flow where the policy is attached as a processing step.

You can attach a Spike Arrest policy at the proxy endpoint or at the target endpoint. At the Proxy Endpoint, this policy limits the inbound requests. When you attach this policy at the Target Endpoint, it limits the requests forwarded to the backend service.

Unlike Quotas, spike arrests are not implemented as counts. Rather, they are implemented as a rate limit which is based on the time the last matching message was processed. For example, if you specify 6 messages per minute, it means that the requests can only be submitted at the rate of one per 10 second interval. The second request within the 10 seconds on the same API Management server will be rejected. Even with a larger number of requests \(200 per second\), if two requests come in nearly simultaneously to the same API Management server, one will be rejected. Each successful request will update the spike arrest's last processed count.

No counter is maintained for spike arrests, only the time that the last message was successfully passed through the Spike Arrest policy is maintained. On a given API Management server, if a request is received now, all subsequent requests will fail until the duration of 10 seconds has elapsed. Since Spike Arrest policy is not distributed, you might see some discrepancy between the actual behavior of the system and your expected results. In general, you should use Spike Arrest policy to set a limit that throttles traffic to what your backend services can handle. Do not use Spike Arrest policy to limit traffic from individual clients.

You can attach the policy in the following locations: ![](images/flow_policy_1_1aa837c.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> > ### Sample Code:  
> > ```
> > <!-- The policy will limit the number of calls to 30 per minute by refering to apikey in the header -->
> > 
> > <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> > <SpikeArrest async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
> >     <Identifier ref="request.header.apikey"></Identifier>
> >     <MessageWeight ref="request.header.weight"></MessageWeight>
> >     <Rate>30pm</Rate>
> > </SpikeArrest>
> > ```

**`<Identifier>` element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`Identifier` \(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

String

</td>
<td valign="top">

Flow variable used for identifying the application or client.

> ### Sample Code:  
> ```
> <SpikeArrest async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <Identifier ref="request.header.userid"></Identifier>
> </SpikeArrest>
> ```



</td>
</tr>
</table>

**`ref` attribute of the `<Identifier>` element**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`ref` \(Required\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Identifies the flow variable by which Spike Arrest groups incoming requests.

</td>
</tr>
</table>

**`<MessageWeight>` element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`MessageWeight` \(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Specifies the weight defined for each message.

Message weight modifies the impact of a single request on the calculation of the SpikeArrest limit. Message weight can be set by variables based on HTTP headers, query parameters, or message body content.

For example, if the SpikeArrest Rate is 10 per minute, and an application submits requests with weight 5, then only 2 messages are permitted per minute from that application.

> ### Sample Code:  
> ```
> <SpikeArrest async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <MessageWeight ref="request.header.weight"/>
> </SpikeArrest>
> ```



</td>
</tr>
</table>

**`ref` attribute of the `<MessageWeight>` element**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`ref` \(Required\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Identifies the flow variable that contains the message weight for the specific client. This can be any flow variable, such as an HTTP query param, header, or message body content.

</td>
</tr>
</table>

**`<Rate>` element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`Rate` \(Required\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Interger

</td>
<td valign="top">

Specifies the rate at which to limit the traffic spike \(or burst\).

Valid value: integer per <min\> or <sec\> or <variable\>

> ### Sample Code:  
> ```
> <SpikeArrest async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <Rate>30pm</Rate>
> </SpikeArrest>
> ```



</td>
</tr>
</table>

**`<UseEffectiveCount>` element**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Default

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`UseEffectiveCount` \(Optional\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

Distributes your Spike Arrest count across Message Processors \(MPs\) when using auto-scaling groups.

> ### Sample Code:  
> ```
> <SpikeArrest async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <UseEffectiveCount>true</UseEffectiveCount>
> </SpikeArrest>
> ```



</td>
</tr>
</table>

When a Spike Arrest policy executes, the following Flow variable is populated:

**Flow Variable**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Type

</th>
<th valign="top">

Permission

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

ratelimit.\{policy\_name\}.failed

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

Read-Only

</td>
<td valign="top">

Indicates whether or not the policy failed \(true or false\).

</td>
</tr>
</table>

During the policy execution, the following errors can occur:

**Error Code**


<table>
<tr>
<th valign="top">

Error Name

</th>
<th valign="top">

HTTP Status

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

SpikeArrestViolation

</td>
<td valign="top">

500

</td>
<td valign="top">

The rate limit is exceeded.

</td>
</tr>
<tr>
<td valign="top">

InvalidMessageWeight

</td>
<td valign="top">

500

</td>
<td valign="top">

The message weight value must be an integer.

</td>
</tr>
<tr>
<td valign="top">

FailedToResolveSpikeArrestRate

</td>
<td valign="top">

500

</td>
<td valign="top">

The referenced variable used to specify the rate can't be resolved.

</td>
</tr>
<tr>
<td valign="top">

InvalidAllowedRate

</td>
<td valign="top">

500

</td>
<td valign="top">

If the spike arrest rate specified in the `<Rate>` element of the Spike Arrest Policy is not an integer or if the rate does not have ps or pm as a suffix, then the deployment of the API proxy fails.

</td>
</tr>
</table>

The folFlowing fault variables are set when the policy triggers an error at runtime:

**Fault Variables**


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

The fault variable \[prefix\] is rate limit.

The \[policy\_name\] is the name of the policy that threw the error.

</td>
<td valign="top">

ratelimit.SA-SpikeArrestPolicy.failed = true

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

fault.name Matches "SpikeArrestViolation"

</td>
</tr>
</table>

**Related Information**  


[Quota](quota-1f742c1.md "The Quota policy defines the number of request messages an application can submit to an API over a given period of time.")

[Concurrent Rate Limit](concurrent-rate-limit-8f22baa.md "The Concurrent Rate Limit policy is being decommissioned. The support for the Concurrent Rate Limit policy has come to an end. You can no longer create or update an API proxy with Concurrent Rate Limit policy. If you’re still using the policy and wondering which policy to use to best meet your rate-limiting needs, see Replace Concurrent Rate Limit Policy with Alternative Policies.")

