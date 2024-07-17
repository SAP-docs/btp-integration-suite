<!-- loio02ff41b314f84daaacc75128a27fd0a2 -->

# API Validation

The API validation policy enables you to validate incoming request messages against an OpenAPI 3.0 Specification.

This policy supports validation of the request body \(limited to application/json\), headers, and query parameters for incoming request messages. The validation process is based on an OpenAPI 3.0 Specification, provided in either JSON or YAML format. This validation functionality is applicable to both OData and REST API artifacts.

In the OpenAPI Specification, you can define the expected headers and query parameters for each API endpoint. The specification allows you to mark certain headers and query parameters as required \(mandatory\) or optional.

When a request is made to an API endpoint, the server implementing the API will validate the incoming headers and query parameters against the defined specification. If a required header or query parameter is missing, or if any of the provided headers or query parameters do not match the expected format or values, the server will respond with an error indicating the validation failure.

> ### Note:  
> For the request path, there is a strict validation. This means that in the request URL, after the base path segment, the subsequent URL segments must be registered as valid paths in the Swagger definition. For example, if you have an API modeled with the base path`/test123` and you want the API validation checks to be performed on `https://<custom domain>/test123/`, the expectation is that the trailing slash`'/'` after `/test123` is explicitly defined as the valid path in the API specification. It's important to note that the base path itself \("/test123"\) will not be accessible. Only the paths that are added after the base path and explicitly defined in the API specification will be accessible.

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

Payload

</td>
<td valign="top">

Determines whether the payload needs to be validated against the provided API specification.

> ### Note:  
> If the payload option is enabled, the incoming request body should be of the type application/JSON.



</td>
</tr>
<tr>
<td valign="top">

Query Parameters

</td>
<td valign="top">

Determines whether the query parameters need to be validated against the provided API specification.

</td>
</tr>
<tr>
<td valign="top">

Headers

</td>
<td valign="top">

Determines whether the headers need to be validated against the provided API specification.

</td>
</tr>
</table>

> ### Note:  
> If you include any additional headers or query parameters in the request that are not defined in the OpenAPI Specification, these additional parameters are allowed to pass through. The server will check if the additional parameters conform to any validation rules specified in the specification, such as data type, format, or allowed values. Also, both mandatory and optional headers and query parameters are validated against the OpenAPI Specification.

> ### Note:  
> OpenAPI Specification version 2.0 is not supported by the API validation policy.

**Related Information**  


[Authentication](authentication-fa6eec4.md "Different API may have various authentication mechanisms. The authentication mechanisms that are currently supported are Basic authentication, Client Certificate, and oAuth.")

[Authorization](authorization-6658409.md "This policy evaluates whether a user should be permitted to access a protected API.")

[JSON Threat Protection](json-threat-protection-c4991a6.md "Minimizes the risk posed by content-level attacks by enabling specific limits on various JSON structures, such as arrays and strings.")

