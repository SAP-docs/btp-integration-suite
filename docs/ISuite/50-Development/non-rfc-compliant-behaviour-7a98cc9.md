<!-- loio7a98cc92d6a249d7b556e594f7676cd5 -->

# Non-RFC\_compliant Behaviour

The OAuthV2 policy generates a token response that includes certain properties that are not RFC-compliant.

The table below lists these non-compliant properties and their corresponding compliant counterparts.

> ### Note:  
> If you require that these elements be compliant, you can create a policy, such as a JavaScript or AssignMessage policy, to transform the policy output into a compliant format.

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

\(The compliant value is a number, not a string.\)

</td>
</tr>
</table>

Also, the error response for an expired refresh token when grant\_type = refresh\_token is:

```
{"ErrorCode" : "InvalidRequest", "Error" :"Refresh Token expired"}
```

However, the RFC-compliant response is:

```
{"error" : "invalid_grant", "error_description" :"refresh token expired"}
```

