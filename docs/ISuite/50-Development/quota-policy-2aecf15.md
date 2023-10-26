<!-- loio2aecf15b996f4e26ae395268d22f16df -->

# Quota Policy

The Quota policy defines the number of request messages an application can submit to an API endpoint over a given period of time.

The period of time can be an hour, a day, or a month and so on. You can apply this policy on the context of request messages.

The Quota policy helps API providers to restrict the number of calls made to an API. For example, you can restrict access to your applications by defining the number of API calls made as 20 per day or 20,000 over a period of 1 week.

See the following video for visual instructions on how to add and configure the Quota policy:

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

The value of the name attribute can contain letters, numbers, spaces, hyphens, underscores, and periods. This value cannot exceed 255 characters.

</td>
</tr>
<tr>
<td valign="top">

On Error

</td>
<td valign="top">

Determines the behavior when an exception or an error occurs during the policy execution. The default value is abort on error.The internal name of the policy. The value of the name attribute can contain letters, numbers, spaces, hyphens, underscores, and periods. This value can’t exceed 255 characters.

</td>
</tr>
<tr>
<td valign="top">

Mode

</td>
<td valign="top">

Select the type of the policy that you want to configure. For example, if you want to explicitly provide a start time, select Calendar. For more information, see [Modes of the Quota Policy](modes-of-the-quota-policy-61b36a1.md).

</td>
</tr>
<tr>
<td valign="top">

Start Time \(UTC\)\*

</td>
<td valign="top">

The internal name of the policy. The value of the name attribute can contain letters,Determines the start of the Quota window. This property can only be specified if the mode is set to *Calendar* and *Fixed*.

Enter the date and time when the Quota counter begins counting.

Timestamp format in UTC format: 2015-02-09 00:00:00.

</td>
</tr>
<tr>
<td valign="top">

Calls\*

</td>
<td valign="top">

Specify the number of calls that a client can make to an API endpoint over a duration. For example, 1000 calls over a duration of 1 hour.

</td>
</tr>
<tr>
<td valign="top">

Duration\*

</td>
<td valign="top">

Determines the period for which the quota is allotted to the client.

Data type: positive integer. For example, 5, 10, ..., 60, etc. that is coupled with the unit \(second, minute, hour, day, week, or month\) in the next field.

</td>
</tr>
<tr>
<td valign="top">

Duration Unit

</td>
<td valign="top">

Represents the unit of time used along with interval.

Supported units are second, minute, hour, day, week, or month.

</td>
</tr>
<tr>
<td valign="top">

Quota Identifier\*

</td>
<td valign="top">

Represents a unique identifier for the client or the application against which the quota is allotted. For example, you can define that the *Quota Identifier\** is determined dynamically by reading a value from a request header such as $\{request.header.appId\}. Refer the table for the supported expressions for the quota identifier.

</td>
</tr>
</table>

**Supported Expressions for Requestor Key**


<table>
<tr>
<th valign="top">

Expressions for Requestor Key

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

$\{request.header.<headerName\>\}

</td>
<td valign="top">

This expression represents a header in the incoming request message where the name of the header is denoted by <headerName\>. For example, you can use the clientID, and username as the <headerName\>.

</td>
</tr>
<tr>
<td valign="top">

$\{request.query.<queryParamName\>\}

</td>
<td valign="top">

This expression represents a query parameter in the incoming request message where the name of the query parameter is denoted by <queryParamName\>. For example, you can use the clientID, and username as the <queryParamName\>.

</td>
</tr>
</table>

> ### Note:  
> When the quota limit specified in the policy is reached, the subsequent calls to the API proxy are rejected with the response code 429 \( request limit exceeded\). The rejection period lasts until the end of the quota window. Let's illustrate this with the following example:
> 
> The quota window opens at 00:00 \(12 AM\) and ends at 00:05 \(12:05 AM\). Let us assume that the quota allotted is three requests in the specified period of 5 minutes. At 00:03, if the quota limit is reached, the subsequent requests post 00:03 are rejected until the window is reset at 00:05.

**Related Information**  


[Surge Protection](surge-protection-3d14745.md "The surge protection policy protects the backend against sudden traffic spikes.")

[IP Filter](ip-filter-3a8b424.md "The IP filter policy allows or denies calls from specific IP addresses or address ranges.")

