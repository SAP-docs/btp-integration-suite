<!-- loioc4991a6c68454851a7edd65d178963f2 -->

# JSON Threat Protection

Minimizes the risk posed by content-level attacks by enabling specific limits on various JSON structures, such as arrays and strings.

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

Name\*

</td>
<td valign="top">

The internal name of the policy. The value of the name attribute can contain letters, numbers, spaces, hyphens, underscores, and periods. This value can’t exceed 255 characters.

</td>
</tr>
<tr>
<td valign="top">

On Error

</td>
<td valign="top">

Determines the behavior when an exception or an error occurs during the policy execution. The default value is abort on error.

</td>
</tr>
<tr>
<td valign="top">

Max Array Element Count

</td>
<td valign="top">

Maximum number of elements allowed in an array. The maximum value is 1,00,000.

</td>
</tr>
<tr>
<td valign="top">

Max Depth

</td>
<td valign="top">

Maximum container depth allowed for objects or arrays. The maximum value is 1,00,000.

</td>
</tr>
<tr>
<td valign="top">

Max Object Count

</td>
<td valign="top">

Maximum number of entries allowed within an object. The maximum value is 1,00,000.

</td>
</tr>
<tr>
<td valign="top">

Max Name Length

</td>
<td valign="top">

Maximum string length allowed for a property name within an object. The maximum value is 1,00,000.

</td>
</tr>
<tr>
<td valign="top">

Max String Value Length

</td>
<td valign="top">

Maximum length allowed for a string value. The maximum value is 1,00,000.

</td>
</tr>
<tr>
<td valign="top">

Max JSON Size

</td>
<td valign="top">

Maximum size allowed for a JSON payload in KB. The maximum value is 10 MB.

</td>
</tr>
</table>

**Related Information**  


[Authentication](authentication-fa6eec4.md "Different API may have various authentication mechanisms. The authentication mechanisms that are currently supported are Basic authentication, Client Certificate, and oAuth.")

[Authorization](authorization-6658409.md "This policy evaluates whether a user should be permitted to access a protected API.")

[API Validation](api-validation-02ff41b.md "The API validation policy enables you to validate incoming request messages against an OpenAPI 3.0 Specification.")

