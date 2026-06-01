<!-- loio7a98cc92d6a249d7b556e594f7676cd5 -->

# **Non-RFC-Compliant Behavior \(OAuthV2 Policy\)**

The OAuthV2 policy generates a token response that includes certain properties that are not Request for Comments \(RFC\)-compliant, specifically deviating from RFC 6749 and related specifications such as RFC 6750.

> ### Note:  
> The table below highlights the non-compliant properties returned by the OAuthV2 policy and their RFC-compliant equivalents:

****


<table>
<tr>
<th valign="top">

OAuthV2 returns:

</th>
<th valign="top">

The RFC-compliant property is:

</th>
</tr>
<tr>
<td valign="top">

"token\_type":"BearerToken"

</td>
<td valign="top">

"token\_type":"Bearer"

</td>
</tr>
<tr>
<td valign="top">

"expires\_in":"3600"

</td>
<td valign="top">

"expires\_in":3600

> ### Note:  
> The expires\_in value must be a numeric value, not a string, as defined by the RFC specification.
> 
> Additionally, for an expired refresh token when grant\_type = refresh\_token, the OAuthV2 policy returns:
> 
> ```
> {"ErrorCode" : "InvalidRequest", "Error" :"Refresh Token expired"}
> ```
> 
> However, the RFC-compliant response should be:
> 
> ```
> {"error" : "invalid_grant", "error_description" :"refresh token expired"}
> ```



</td>
</tr>
</table>

> ### Note:  
> If strict RFC compliance is required, you can implement a transformation policy \(for example, JavaScript or AssignMessage\) to modify the OAuthV2 response into a compliant format.

