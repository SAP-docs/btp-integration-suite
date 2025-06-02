<!-- loio3a8b424f685c44f18ef727a8df843882 -->

# IP Filter

The IP filter policy allows or denies calls from specific IP addresses or address ranges.

This policy is used to selectively allow or deny access for an IP address or group of IP addresses. Use this policy when you want to limit access to APIs to only a specific IP address or group of IP addresses. For example, if you only want systems \(computers, mobile, etc\) under the control of your enterprise to access the APIs exposed in your test environment, you can allow \(allowlist\) the IP address range for your internal network. Developers working from home can access these APIs using VPN.

> ### Note:  
> For the IP filter policy to work correctly, the *Client IP Preservation* feature needs to be enabled on the Edge Lifecycle Management. For more information, see [Deploy the Edge Integration Cell Solution](../deploy-the-edge-integration-cell-solution-ab81b84.md).

See the following video for visual instructions on how to add and configure the IP filter policy:



<a name="loio3a8b424f685c44f18ef727a8df843882__section_msg_cjt_c2c"/>

## IP Masking with CIDR Notation

CIDR \(Classless Inter-Domain Routing\)\*\* is a method for specifying a range of IP addresses using a mask. It works with both IPv4 and IPv6, but we'll focus on IPv4 for simplicity, as that's what we support.

IPv4 addresses are divided into groups of numbers separated by periods \(e.g., 198.51.100.1\). Each group represents 8 bits, so the entire IPv4 address is made up of 32 bits.

In binary, the IPv4 address 198.51.100.1 looks like this: 11000110.00110011.01100100.00000001

This breaks down into 4 groups of 8 bits, totaling 32 bits.

With CIDR, a range of IP addresses can be specified by appending a /number \(from 1 to 32\) to the IP address, like this: 198.51.100.1/24

In this case, the number 24 is used as the mask attribute value.

The notation 198.51.100.1/24 means that the first 24 bits must remain fixed, while the remaining bits can be any value from 0 to 255. For example:

> ### Example:  
> 
> <table>
> <tr>
> <th valign="top">
> 
> Fixed Portion
> 
> </th>
> <th valign="top">
> 
> Possible Values for the Last Group
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> 198.51.100.
> 
> </td>
> <td valign="top">
> 
> 0 - 255
> 
> </td>
> </tr>
> </table>
> 
> The mask is applied at the end of the third group. This creates a clean division, essentially resulting in a mask like `198.51.100.*`. Typically, using multiples of 8 for IPv4.
> 
> IPv4: 8, 16, 24, 32
> 
> You can also use other values for finer control, which involves some binary calculation.

> ### Example:  
> Here's an example using a mask of 30, as in `198.51.100.1/30`:
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Fixed Part
> 
> </th>
> <th valign="top">
> 
> Possible Values for the Last Group
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> 11000110.00110011.01100100.000000 \(first 30 bits\)
> 
> </td>
> <td valign="top">
> 
> 00000000, 00000001, 00000010, or 00000011
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> 198.51.100.
> 
> </td>
> <td valign="top">
> 
> 0, 1, 2, or 3
> 
> </td>
> </tr>
> </table>
> 
> With the configuration `<SourceAddress mask="30">198.51.100.1</SourceAddress>`, the following IP addresses would be allowed \(or denied, depending on your rules\):
> 
> -   198.51.100.0
> -   198.51.100.1
> -   198.51.100.2
> -   198.51.100.3



<a name="loio3a8b424f685c44f18ef727a8df843882__section_mwg_y3t_c2c"/>

## Policy Settings


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

Scroll down to the *Rules* section, select *Add* and provide the rules for the two allowed actions \(Allow or Deny\). Each rule should include a range of IP addresses in CIDR notation.

> ### Note:  
> If you want to allow or block IP address, then adhere to the following CIDR notation:
> 
> 
> <table>
> <tr>
> <td valign="top">
> 
> Allow or block a single IP address
> 
> </td>
> <td valign="top">
> 
> -   To allow a single IP address, select *Allow* and use the subnet mask /32 for IPv4.
> 
> -   To block a single IP address, select *Deny* and use the subnet mask /32 for IPv4.
> 
> 
> For example: To allow or deny a single IPv4 address, such as 192.168.1.1, enter the following CIDR notation in the *IP Address* field: 192.168.1.1/32
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Allow or block a range of IP addresses
> 
> </td>
> <td valign="top">
> 
> -   To allow a range of IP addresses, select *Allow*, and use the subnet mask /24 for IPv4.
> 
> -   To block a range of IP addresses, select *Deny* and use the subnet mask /24 for IPv4.
> 
> 
> For example: To allow or deny a range of IPv4 addresses, such as 192.168.1.0`to`192.168.1.255, enter the following CIDR notation in the *IP Address* field: 192.168.1.0/24
> 
> </td>
> </tr>
> </table>

> ### Note:  
> The execution of these rules follows the order in which they are listed in the UI. The topmost rule gets executed first, followed by the ones below it in sequence. If none of the rules match, the default rule is applied.

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


[Quota](quota-2aecf15.md "The Quota policy defines the number of request messages an application can submit to an API endpoint over a given period of time.")

[Surge Protection](surge-protection-3d14745.md "The surge protection policy is designed to protect against traffic surges by controlling the rate at which requests are processed by an API during runtime. This policy acts as a safeguard, reducing the likelihood of downtime and performance issues.")

