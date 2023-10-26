<!-- loio6658409a114a4c038572276335bea8b9 -->

# Authorization

This policy evaluates whether a user should be permitted to access a protected API.

Different iFlow sender channels may have different authorizations and roles. For API artifact, different resources may have different authorization and roles configured.

**Policy Settings**


<table>
<tr>
<th valign="top">

Attribute

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

Claim

</td>
<td valign="top">

Claims are assertions that a user or an authorization server makes about itself or another subject. For example, an ID Token will consist of some claims with information about the user, maybe their first and last name, e-mail address, etc.

Enter the claim value as it is expected to appear in the token. For example, user\_name or clientId.

</td>
</tr>
</table>

**Related Information**  


[Authentication](authentication-fa6eec4.md "Different API Proxies may have various authentication mechanisms. The authentication mechanisms that are currently supported are Basic authentication, Client Certificate, and oAuth.")

[JSON Threat Protection](json-threat-protection-c4991a6.md "Minimizes the risk posed by content-level attacks by enabling specific limits on various JSON structures, such as arrays and strings.")

