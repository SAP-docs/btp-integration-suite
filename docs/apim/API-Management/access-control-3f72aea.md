<!-- loio3f72aea270654527afb0a743fa52702a -->

# Access Control

Restrict access to your APIs based on specific Internet Protocol \(IP\) addresses.

This policy is used to selectively allow or deny access for an IP address or group of IP addresses. Use this policy when you want to limit access to APIs to only a specific IP address or group of IP addresses. For example, if you only want computers under the control of your enterprise to access the APIs exposed in your test environment, you can allow \(allowlist\) the IP address range for your internal network. Developers working from home can access these APIs using VPN.

You configure an Access Control policy as follows:

-   Specify match rules for the two permitted actions \(ALLOW or DENY\).

    Specify the IP address \(SourceAddress element\) for each match rule. Also, configure a mask for each IP address. You allow or deny access based on a mask value on the IP address.


-   Mention the order in which the rules are to be executed.

    The system executes the first matching rule in the defined order, and then subsequent matching rules are skipped. If the same rule is configured with both ALLOW and DENY actions, the rule that is defined first is executed and the subsequent rule is skipped.


You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

**How the Access Control policy determines which IP address to validate?**

In an ideal scenario, IP addresses that are served can come from various sources in a request. For instance, the `True-Client-IP` header can contain an IP address and the `X-Forwarded-For` header can contain one or more IP addresses. Also, the API Management configuration and the policy configuration determine which `X-Forwarded-For address(es)` the policy evaluates.

This section describes how you can configure the Access Control policy to determine which IP address it chooses to validate. Following is the logic based on which Access Control policy determines the IP address it chooses to validate:

-   **True-Client-IP header**

    The policy first checks if an IP address is present in the True-Client-IP header. If a valid IP address is present, the policy validates that IP address.

    > ### Caution:  
    > If you're going to use the `True-Clinet-IP` header, then make sure that you trust the source of that address. If you can't ensure that the header contains a trusted address, set `<IgnoreTrueClientIPHeader>` to `true` so that the policy ignores the `True-Client-IP` and instead evaluates the IP address\(es\) in the `X-Forwarded-For` header.

-   **IgnoreTrueClientIPHeader**

    When you set `<IgnoreTrueClientIPHeader>` to `true`, the policy ignores the `True-Client-IP header`and evaluates IP addresses in the `X-Forwarded-For` header, following the behavior you've configured. When the `IgnoreTrueClientIPHeader` attribute is set to false, the policy evaluates the `True-Client-IP header`. By default, `IgnoreTrueClientIPHeader` attribute is set to `false`.

-   **X-Forwarded-For header**

    If the True-Client-IP header doesn’t contain an IP address, or if you've set the`<IgnoreTrueClientIPHeader>` element to `true`, then the policy validates the IP addresses present in the -X-Forwarded-For header. If there are multiple addresses in the X-Forwarded-For header, then those IP addresses, likely belong to the chain of servers that processed a request.

    > ### Note:  
    > API Management, by default, fills the `X-Forwarded-For` header with a single IP address it received from the last external TCP handshake \(such as the Client IP or router\). That is, in API Management, the X-Forwarded-For header is populated with only a single IP address.


An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <!–- Use case-1 : Allow only a single IP -->
> 
> <AccessControl async='true' continueOnError='false' enabled='true' xmlns='http://www.sap.com/apimgmt'>
>   <IPRules noRuleMatchAction='DENY'>
>     <MatchRule action='ALLOW'>
>       <SourceAddress mask='32'>120.75.68.75</SourceAddress>
>     </MatchRule>
>   </IPRules>
> </AccessControl>
> 
> 
> <!–- Use case -2: Block a range of IP -->
> 
> <AccessControl async='true' continueOnError='false' enabled='true' xmlns='http://www.sap.com/apimgmt'>
>   <IPRules noRuleMatchAction='ALLOW'>
>     <MatchRule action='DENY'>
>       <SourceAddress mask='8'>120.75.68.75</SourceAddress>
>     </MatchRule>
>   </IPRules>
> </AccessControl>
> 
> 
> <!-- Use case-3 : Allow a single IP from an identified range -->
> 
> <!– In the below setting IP 120.75.68.75 is allowed and any other IP in the range 120.75.68.* is blocked -->
> 
> <AccessControl async='true' continueOnError='false' enabled='true' xmlns='http://www.sap.com/apimgmt'>
>   <IPRules noRuleMatchAction='ALLOW'>
>     <MatchRule action='ALLOW'>
>       <SourceAddress mask='32'>120.75.68.75</SourceAddress>
>     </MatchRule>
>      <MatchRule action='DENY'>
>       <SourceAddress mask='24'>120.75.68.75</SourceAddress>
>     </MatchRule>
>   </IPRules>
> </AccessControl>
> 
> <!-- Use case-4 : The access control policy allows value from flow variables -->
> 
> <AccessControl async='true' continueOnError='false' enabled='true' xmlns='http://www.sap.com/apimgmt'>
>   <IPRules noRuleMatchAction='DENY'>
>     <MatchRule action=’ALLOW’>
>       <SourceAddress mask="{kvm.mask.value}">{kvm.ip.value}</SourceAddress>
>     </MatchRule>
>   </IPRules>
> </AccessControl>
> <!--kvm.mask.value and kvm.ip.value are read using Key Value Map Operations policy before it's used in the 
> AccessControl policy-->
>  
> 
> ```

**Element and Attribute Descriptions**


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

IPRules \(Optional\)

</td>
<td valign="top">

This is the parent element containing the rules to allow or deny IP addresses.

</td>
</tr>
<tr>
<td valign="top">

noRuleMatchAction \(Mandatory\)

</td>
<td valign="top">

Defines the action that has to be taken if the match rule isn’t resolved. This element contains child elements that define which IP addresses are permitted or restricted.

Valid value: `ALLOW` or `DENY`

The default value is `ALLOW`.

Syntax: `<IPRules noRuleMatchAction = "ALLOW">`

</td>
</tr>
<tr>
<td valign="top">

MatchRule action \(Mandatory\)

</td>
<td valign="top">

Defines the action that has to be taken if the IP address matches the Source address defined.

Valid value: `ALLOW` or `DENY`

The default value is `ALLOW`.

> ### Sample Code:  
> Example
> 
> ```
> <IPRules noRuleMatchAction = "ALLOW">
>     <MatchRule action = "ALLOW">
>         <SourceAddress mask="32">120.75.68.75</SourceAddress>
>     </MatchRule>
>     <MatchRule action = "DENY">
>         <SourceAddress mask="24">120.75.68.75</SourceAddress>
>     </MatchRule>
> </IPRules>
> ```



</td>
</tr>
<tr>
<td valign="top">

ValidateBasedOn \(Optional\)

</td>
<td valign="top">

To determine which IP addresses should be evaluated, utilize the ValidateBasedOn element when the X-Forwarded-For HTTP header contains multiple IP addresses.

Valid value: X\_FORWARDED\_FOR\_ALL\_IP, X\_FORWARDED\_FOR\_FIRST\_IP, X\_FORWARDED\_FOR\_LAST\_IP

The default value is `X_FORWARDED_FOR_FIRST_IP`.

> ### Sample Code:  
> ```
> <IPRules noRuleMatchAction = "ALLOW">
>     <MatchRule action = "ALLOW">
>         <SourceAddress mask="32">120.75.68.75</SourceAddress>
>     </MatchRule>
>     <MatchRule action = "DENY">
>         <SourceAddress mask="24">120.75.68.75</SourceAddress>
>     </MatchRule>
> </IPRules>
> <ValidateBasedOn>X_FORWARDED_FOR_ALL_IP</ValidateBasedOn>
> 
> ```



</td>
</tr>
<tr>
<td valign="top">

SourceAddress \(Optional\)

</td>
<td valign="top">

This element indicates the IP address range of a client. The valid IP address of the consumer in dotted decimal notation is a valid value. For example, `127.0.0.1`.

</td>
</tr>
<tr>
<td valign="top">

Mask \(Mandatory\)

</td>
<td valign="top">

Use this attribute in conjunction with the `SourceAddress` element. The mask refers to the number of bits in the IP Address that has to be considered. The maximum value of mask is less than or equal to 32.

For example:

```
<IPRules noRuleMatchAction = "ALLOW">
    <MatchRule action = "ALLOW">
        <SourceAddress mask="16">20.10.10.09</SourceAddress>
    </MatchRule>
</IPRules>
```

Then, all the IP Addresses with the pattern `20.10.*` are allowed to access the proxy.

</td>
</tr>
</table>

During the policy execution, the following errors can occur:

**Error Cause**


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

ClientIpExtractionFailed

</td>
<td valign="top">

See fault string.

</td>
</tr>
<tr>
<td valign="top">

IPDeniedAccess

</td>
<td valign="top">

See fault string.

</td>
</tr>
<tr>
<td valign="top">

InvalidIPAddress

</td>
<td valign="top">

See fault string.

</td>
</tr>
<tr>
<td valign="top">

InvalidIPv4Address

</td>
<td valign="top">

See fault string.

</td>
</tr>
<tr>
<td valign="top">

InvalidIPv6Address

</td>
<td valign="top">

See fault string.

</td>
</tr>
<tr>
<td valign="top">

InvalidRulePattern

</td>
<td valign="top">

See fault string.

</td>
</tr>
</table>

Following fault variables are set when the policy triggers an error at runtime:

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

The \[prefix\] is acl.

The \[policy\_name\] is the name of the policy that threw the error.

</td>
<td valign="top">

acl.AC-AllowAccess.failed = true

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

fault.name = "IPDeniedAccess"

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
>          "errorcode":"steps.accesscontrol.IPDeniedAccess"
>       },
>       "faultstring":"Access Denied for client ip : 51.218.253.1"
>    }
> }
> ```

Following is an example of a fault rule:

> ### Sample Code:  
> Example
> 
> ```
> <FaultRule name="IPDeniedAccess">
>     <Step>
>         <Name>AssignMsg-IPDeniedAccess</Name>
>         <Condition>(fault.name Matches "IPDeniedAccess") </Condition>
>     </Step>
>     <Condition>(acl.failed = true) </Condition>
> </FaultRule>
> ```

