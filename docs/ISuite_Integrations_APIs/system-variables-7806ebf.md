<!-- loio7806ebf2a1994449bb660f333a6a5101 -->

# System Variables

Information pertaining to the system is described in system variables.

Every system variable consists of two parts, a prefix `_system` and a function. For example: system.time, system is the prefix and time is the function. Supported system variables are listed in the System Variables table.

**System Variables**


<table>
<tr>
<th valign="top">

Variables

</th>
<th valign="top">

Description

</th>
<th valign="top">

Scope

</th>
<th valign="top">

Type

</th>
<th valign="top">

Permission

</th>
</tr>
<tr>
<td valign="top">

system.timestamp

</td>
<td valign="top">

The timestamp value specifying when the request is received from the client at the ProxyEndpoint. This value is a 64-bit \(long\) integer containing the number of milliseconds elapsed since midnight, on January 1, 1970 UTC.

</td>
<td valign="top">

Proxy Request

</td>
<td valign="top">

Long

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.time

</td>
<td valign="top">

The time, expressed in string form, at which the proxy received a request from a client at the ProxyEndpoint. For example: Wed, 21 Aug 2013 19:16:47 UTC.

This time value is the string representation of the corresponding 32-bit timestamp quantity. For example, 'Wed, 21 Aug 2013 19:16:47 UTC' corresponds to the timestamp value of 1377112607413.

</td>
<td valign="top">

Proxy Request

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.time.year

</td>
<td valign="top">

The year portion of the system.time variable.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.time.month

</td>
<td valign="top">

The month portion of the system.time variable.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.time.day

</td>
<td valign="top">

The day of month portion of the system.time variable.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.time.dayofweek

</td>
<td valign="top">

The day of the week portion of the system.time variable.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.time.hour

</td>
<td valign="top">

The hour portion of the system.time variable.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.time.minute

</td>
<td valign="top">

The minute portion of the system.time variable.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.time.second

</td>
<td valign="top">

The second portion of the system.time variable.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.time.millisecond

</td>
<td valign="top">

The millisecond portion of the system.time variable.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.time.zone

</td>
<td valign="top">

Timezone of the system.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.interface.\{interface\_name\}

</td>
<td valign="top">

IP Address of the system.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.pod.name

</td>
<td valign="top">

The name of the pod where the proxy is running.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.region.name

</td>
<td valign="top">

The name of the data center region where the proxy is running.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

system.uuid

</td>
<td valign="top">

The UUID of the message processor handling the proxy.

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

router.uuid

</td>
<td valign="top">

The UUID of the router handling the proxy

</td>
<td valign="top">

Proxy request

</td>
<td valign="top">

String

</td>
<td valign="top">

Read

</td>
</tr>
</table>

