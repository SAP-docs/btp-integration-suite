<!-- loio3a8b424f685c44f18ef727a8df843882 -->

# IP Filter

The IP filter policy allows or denies calls from specific IP addresses or address ranges.

This policy is used to selectively allow or deny access for an IP address or group of IP addresses. Use this policy when you want to limit access to APIs to only a specific IP address or group of IP addresses. For example, if you only want systems \(computers, mobile, etc\) under the control of your enterprise to access the APIs exposed in your test environment, you can allow \(allowlist\) the IP address range for your internal network. Developers working from home can access these APIs using VPN.

> ### Note:  
> For the IP filter policy to work correctly, the *Client IP Preservation* feature needs to be enabled on the Edge Lifecycle Management. For more information, see [Deploy the Edge Integration Cell Solution](../deploy-the-edge-integration-cell-solution-ab81b84.md).

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

Name

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

Rules

</td>
<td valign="top">

Scroll down to the *Rules* section, select *Add* and provide the rules for the two allowed actions \(ALLOW or DENY\). Each rule should include either a single IP address or an IP address range in CIDR notation, such as 182.168.0.5/32. Access will be permitted or denied based on the mask value applied to the IP address.

> ### Note:  
> Only IPv4 addresses are supported.



</td>
</tr>
<tr>
<td valign="top">

Default Rule

</td>
<td valign="top">

If the client IP of the incoming calls doesn’t fall within the range of the IPs that you have set in the rules, then the default rule will get applied to the incoming request.

The default value is set to *Deny*. Select *Allow* to permit calls from specific IP addresses.

</td>
</tr>
<tr>
<td valign="top">

Allow Headers

</td>
<td valign="top">

Specify the list of headers from where you intend to fetch the client IP.

> ### Note:  
> The order in which you select these headers determines the order in which the client IPs are fetched from the incoming request.

Set of supported headers -

-   X-Forwarded-For

-   CF-Connecting-IP

-   True-Client-IP

-   X-Real-IP




</td>
</tr>
</table>

**Related Information**  


[Quota Policy](quota-policy-2aecf15.md "The Quota policy defines the number of request messages an application can submit to an API endpoint over a given period of time.")

[Surge Protection](surge-protection-3d14745.md "The surge protection policy protects the backend against sudden traffic spikes.")

