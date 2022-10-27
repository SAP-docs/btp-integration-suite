<!-- loiobf441dc839034613b059cb508ad610f7 -->

# Spike Arrest

The Spike Arrest policy limits the number of requests forwarded from the point in the processing flow where the policy is attached as a processing step.

You can attach a Spike Arrest policy at the proxy endpoint or the target endpoint. At the proxy endpoint, this policy limits inbound requests. When you attach this policy at the TargetEndpoint, it limits request forwarded to the backend service.

Unlike Quotas, spike arrests are not implemented as counts. Rather, they are implemented as a rate limit which is based on the time the last matching message was processed. If you specify 6 messages per minute, it means that requests can only be submitted at the rate of one per 10 second interval. A second request within 10 seconds on the same API Management server will be rejected. Even with a larger number \(200 per second\), if two requests come in nearly simultaneously to the same API Management server, one will be rejected. Each successful request will update the spike arrest's last processed count.

No counter is maintained for spike arrests, only a time that the last message was successfully passed through the Spike Arrest policy. On a given API Management server, if a request is received now, all subsequent requests will fail until 10 seconds has elapsed. Since Spike Arrest is not distributed, you might see some discrepancy between the actual behavior of the system and your expected results. In general, you should use Spike Arrest to set a limit that throttles traffic to what your backend services can handle. Do not use Spike Arrest to limit traffic from individual clients.

You can attach the policy in the following locations: ![](images/flow_policy_1_1aa837c.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> 
> <!-- The policy will limit the number of calls to 30 per minute for a user by refering to user id in the header -->
> 
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <SpikeArrest async="true" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <Identifier ref="request.header.userid"></Identifier>
>     <MessageWeight ref="request.header.weight"></MessageWeight>
>     <Rate>30pm</Rate>
> </SpikeArrest>
> 
> ```


<table>
<tr>
<th valign="top">

**Elements and Attributes**



</th>
<th valign="top">

**Description**



</th>
</tr>
<tr>
<td valign="top">

Identifier ref



</td>
<td valign="top">

Variable used for uniquely identifying the application or client.



</td>
</tr>
<tr>
<td valign="top">

MessageWeight ref



</td>
<td valign="top">

Specifies the weight defined for each message.

Message weight is used to modify the impact of a single request on the calculation of the SpikeArrest limit. Message weight can be set by variables based on HTTP headers, query parameters, or message body content. For example, if the SpikeArrest Rate is 10 per minute, and an application submits requests with weight 5, then only 2 messages are permitted per minute from that application.



</td>
</tr>
<tr>
<td valign="top">

Rate



</td>
<td valign="top">

Specifies the rate at which to limit the traffic spike \(or burst\).

Valid value: integer per <min\> or <sec\> or <variable\>.



</td>
</tr>
</table>

When a Spike Arrest policy executes, the following Flow variable is populated:

<a name="loiobf441dc839034613b059cb508ad610f7__table_bnr_fjb_n1b"/>Flow Variable


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

<a name="loiobf441dc839034613b059cb508ad610f7__table_sbx_lsx_lz"/>Error Code


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
</table>

Following fault variables are set when the policy triggers an error at runtime:

<a name="loiobf441dc839034613b059cb508ad610f7__table_c4m_r25_h1b"/>Fault Variables


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

The fault variable \[prefix\] is ratelimit.

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

