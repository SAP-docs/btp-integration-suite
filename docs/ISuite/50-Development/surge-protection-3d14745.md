<!-- loio3d14745b85894b28abe780504c107373 -->

# Surge Protection

The surge protection policy is designed to protect against traffic surges by controlling the rate at which requests are processed by an API during runtime. This policy acts as a safeguard, reducing the likelihood of downtime and performance issues.

Let us consider a use case where an API admin or a developer wants to allow only 2000 calls per minute from the clients. To do this, the admin/developer needs to configure the surge protection policy on the request flow to restrict the sudden surge in traffic irrespective of the clients. Unlike the quota policy, the surge protection policy is not client specific.

**Policy Settings**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Name\*

</td>
<td valign="top">

The internal name of the policy. The value of the name attribute can contain letters, numbers, spaces, hyphens, underscores, and periods. This value cannot exceed 255 characters.

</td>
</tr>
<tr>
<td valign="top">

On Error

</td>
<td valign="top">

Determines the behaviour when an exception or an error occurs during the policy execution. The default value is abort on error.

</td>
</tr>
<tr>
<td valign="top">

Calls\*

</td>
<td valign="top">

Specify the number of calls that a client can make to an API endpoint over a duration. For example, 1000 calls over a duration of one hour.

</td>
</tr>
<tr>
<td valign="top">

Duration\*

</td>
<td valign="top">

Determines the period for which the quota is allotted to the client.

Data type: positive integer. For example, 5, 10, ..., 60, etc. that is coupled with the unit \(second, minute, hour, day, week, or month\) in the next field.

> ### Note:  
> The supported interval is between 200 milliseconds and 10 seconds.



</td>
</tr>
<tr>
<td valign="top">

Duration Unit

</td>
<td valign="top">

Represents the unit of time used along with interval.

Supported units are seconds, and milliseconds.

</td>
</tr>
</table>

**Related Information**  


[Quota](quota-2aecf15.md "The Quota policy defines the number of request messages an application can submit to an API endpoint over a given period of time.")

[IP Filter](ip-filter-3a8b424.md "The IP filter policy allows or denies calls from specific IP addresses or address ranges.")

