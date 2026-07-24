<!-- loioaebf968a66a24cf2abf27ea293a0ff22 -->

# Security Policies

Security policies enable you to minimizes the risk posed by content-level attacks, and encode and decode usernames and passwords.



## Use

You use security policies in an API artifact to:

-   Authenticate API consumers using supported mechanisms such as Basic authentication, Client Certificate, and OAuth.
-   Authorize users by evaluating whether they are permitted to access a protected API.
-   Validate incoming request messages against an OpenAPI 3.0 specification to ensure they conform to the expected structure.
-   Minimize the risk posed by content-level attacks by enforcing limits on JSON structures such as arrays and strings.
-   Safeguard XML-based applications and APIs against malicious attacks by enforcing rules on XML data to prevent threats such as recursive payloads, excessive node depth, and oversized payloads.
-   Encode and decode usernames and passwords securely during API processing.



## Security Policies


<table>
<tr>
<th valign="top">

Policy

</th>
<th valign="top">

Policy Definition

</th>
<th valign="top">

Runtime Support

</th>
<th valign="top">

Important Notes/Links

</th>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

API may have various authentication mechanisms. The authentication mechanisms that are currently supported are Basic authentication, Client Certificate, and OAuth.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

-   The position of the authentication policy on the flow is immutable and it’s the first policy on the flow.

-   Authentication policy is a mandatory policy and is added to request flow by default. Neither you can remove this policy, nor you can add another authentication policy to the flow.

-   Authentication policy can be added to the request flow only once. All other policies can be added to the flow multiple times.

    For more information, see [Authentication](authentication-fa6eec4.md).




</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

This policy evaluates whether a user should be permitted to access a protected API.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Authorization](authorization-6658409.md).

</td>
</tr>
<tr>
<td valign="top">

API Validation

</td>
<td valign="top">

The *API Validation* policy enables you to validate incoming request messages against an OpenAPI 3.0 Specification.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [API Validation](api-validation-02ff41b.md).

</td>
</tr>
<tr>
<td valign="top">

JSON Threat Protection

</td>
<td valign="top">

Minimizes the risk posed by content-level attacks by enabling specific limits on various JSON structures, such as arrays and strings.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [JSON Threat Protection](json-threat-protection-c4991a6.md).

</td>
</tr>
<tr>
<td valign="top">

XML Threat Protection

</td>
<td valign="top">

This policy safeguards XML-based applications and APIs from malicious attacks. It enforces rules on XML data to prevent threats such as recursive payloads, excessive node depth, and oversized payloads.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [XML Threat Protection](xml-threat-protection-2e04b93.md).

</td>
</tr>
</table>

