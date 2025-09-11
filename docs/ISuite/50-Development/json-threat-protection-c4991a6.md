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

The unique name of the policy within the API artifact. Each policy in an API artifact must have a unique name to prevent naming conflicts.

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

Policy configuration having maximum JSON container depth of 3:

```
{
  "root": {
    "level1": {
      "level2": {
        "level3": {
          "level4": "Exceeds the depth, resulting in failure invalid payload"
        }
      }
    }
  }
}
 
```

```
{
  "root": {
    "level1": {
      "level2": {
        "level3": "Within the limits"
      }
    }
  }
}

```



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

Maximum size allowed for a JSON payload in KB. The maximum value is 10000 KB.

> ### Note:  
> If this field is left empty, a system-enforced runtime limit of 10,000 KB \(where 1 KB = 1000 bytes\) will apply.



</td>
</tr>
</table>

> ### Note:  
> Apart from the **Name** and **On Error** fields \(which are generic\), if you leave the following fields empty, **no validation** is performed for them:
> 
> -   Max Array Element Count
> 
> -   Max Depth
> 
> -   Max Object Count
> 
> -   Max Name Length
> 
> -   Max String Value Length

If the Max JSON Size field is left empty and the incoming payload exceeds 10000 KB, the policy enforces the system-level limit of **10,000 KB**, resulting in a failure. However, if the **On Error** field is set to **Continue**, the error is ignored, and flow execution proceeds.

**Related Information**  


[Authentication](authentication-fa6eec4.md "Different API may have various authentication mechanisms. The authentication mechanisms that are currently supported are Basic authentication, Client Certificate, and oAuth.")

[Authorization](authorization-6658409.md "This policy evaluates whether a user should be permitted to access a protected API.")

[XML Threat Protection](xml-threat-protection-2e04b93.md "An XML Threat Protection policy safeguards XML-based applications and APIs from malicious attacks. It enforces rules on XML data to prevent threats such as recursive payloads, excessive node depth, and oversized payloads.")

[API Validation](api-validation-02ff41b.md "The API validation policy enables you to validate incoming request messages against an OpenAPI 3.0 Specification.")

