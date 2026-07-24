<!-- loio6658409a114a4c038572276335bea8b9 -->

# Authorization

This policy evaluates whether a user should be permitted to access a protected API.

Different integration flow sender channels can use different authorization configurations and roles. Similarly, different API resources within the same API artifact can be protected using different authorization settings.



## How Authorization Validation Works

When a request is sent to an API endpoint protected using the Authorization policy, API Management validates the incoming JWT token and developer key based on the configured **Authorization Type**.

Depending on the selected authorization type, the runtime validates:

-   OAuth scopes present in the JWT token
-   Developer key present in the JWT token
-   Or both



## Policy Settings

**General**


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

The unique name of the policy within the API artifact. Each policy in an API artifact must have a unique name to prevent naming conflicts.

</td>
</tr>
</table>

**Policy Settings**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Description

</th>
<th valign="top">

Notes

</th>
</tr>
<tr>
<td valign="top">

Authoriztion Type

</td>
<td valign="top">

Specifies the authorization mechanism required to access the API.

-   *OAuth Scope or Developer Key* \(Default\): Access is granted using either OAuth scopes or a developer subscription \(clientid\).
-   *OAuth Scope and Developer Key*: Both OAuth scopes and a developer subscription \(clientid\) are required for access.
-   *OAuth Scope Only*: Access is controlled solely through OAuth scopes.
-   *Developer Key Only*: Access is controlled solely through a developer subscription \(clientid\).



</td>
<td valign="top">

Refer to the **Authorization Types** section for the details.

When *Authentication* is set to *External OIDC*, use the *OAuth Scope AND Developer Key* authorization type.

For *Tenant XSUAA*, you can use the following authorization types:

-   Scope only
-   Developer Key only
-   OAuth Scope OR Developer Key



</td>
</tr>
<tr>
<td valign="top">

Scope Key

</td>
<td valign="top">

The name of the JWT claim where the scope information is present.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Scope

</td>
<td valign="top">

The specific scope\(s\) that must be present in the token for the request to be authorized.

Please make sure that the user attempting to invoke the API endpoint is assigned at least one of the roles defined in the scope field.

> ### Note:  
> By default, the *Scope* field is populated with *API.invoke*, a technical user role predefined by SAP that cannot be modified or removed. This role enables access to APIs and MCP servers via the credentials created as part of the service keys for a Process Integration Runtime instance.

> ### Note:  
> Either the role entered in the scope field should be preconfigured in the *User Roles* section of the *Monitor* view under the *Manage Security* section or you must add the role you've entered in the scope field in *User Roles*. To learn how to configure the role, see [Managing User Roles](managing-user-roles-4e86f0d.md).

For example, if you’ve configured a role called `APIArtifactUser` in *User Roles*, you must enter the role exactly as it is \(including case sensitivity\) in the scope field or vice versa.

Once the `APIArtifactUser` role is configured in *User Roles*, it is automatically added to the *Roles* in SAP BTP Cockpit.

To execute an API with the Authorization policy successfully on the runtime node, the `APIArtifactUser` role should be associated to the *Process Integration Runtime* instance. For step-by-step instruction on how to create a *Process Integration Runtime* instance, see [Invoke an API or an MCP Server Artifact by Obtaining Credentials through Process Integration Runtime](invoke-an-api-or-an-mcp-server-artifact-by-obtaining-credentials-through-process-integrat-b63baa2.md).

</td>
<td valign="top">

Assume that an API is protected using the Authentication and Authorization policy, and authentication is done via an external Identity Provider \(IdP\).

1.  After successful authentication, the IDP issues a JWT token like this:

    > ### Sample Code:  
    > ```
    > {
    >   "iss": "https://idp.example.com",
    >   "sub": "user123",
    >   "aud": "api://order-service",
    >   "exp": 1710000000,
    >   "scp": "orders.read orders.write"
    > }
    > ```

    In this example, the scopes are not in the standard scope claim. They are present in a custom claim called scp.

2.  Your API should allow access only if the caller has the scope:`orders.read`
3.  In the Authorization policy, you configure:
    -   *Scope Key*: scp

    -   *Scope Value*: orders.read


4.  When a request reaches the API:
    1.  API Management extracts the JWT token from the request.
    2.  It looks for the claim defined as Scope Key \(`scp`\).
    3.  It checks whether the value of scp contains the required Scope Value \(`orders.read`\).
    4.  Since the token contains `orders.read`, the request is authorized and forwarded to the backend.

        If the token had only:

        > ### Sample Code:  
        > ```
        > 
        > "scp": "orders.write"
        > ```

        then the request would be rejected with an authorization error.





</td>
</tr>
<tr>
<td valign="top">

Trust Upstream MCP Authorization

</td>
<td valign="top">

Select this option to establish trust with the authorization policy of the upstream MCP server when the API acts as the source. When enabled, the authorization policy is executed only once at the MCP layer, and the API-level authorization policy is bypassed. By default this setting is disabled.

</td>
<td valign="top">

This option is available only in the Premium, Enhanced, Trial, and Free tier edition.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



</td>
</tr>
</table>



## Authorization Types


<table>
<tr>
<th valign="top">

Authorization Types

</th>
<th valign="top">

Description

</th>
<th valign="top">

Validation Performed

</th>
<th valign="top">

Endpoint Invocation Behavior

</th>
</tr>
<tr>
<td valign="top">

OAuth Scope

</td>
<td valign="top">

Access is controlled solely through OAuth scopes.

</td>
<td valign="top">

-   The JWT token signature and validity are verified.
-   The configured scope claim is extracted from the token.
-   The runtime checks whether the configured scope exists in the token.



</td>
<td valign="top">

A JWT token issued either by:

-   the Process Integration Runtime \(PIR\) instance, or
-   an external Identity Provider \(IdP\)

can successfully invoke the endpoint if the required scope is present.

Configured policy:


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Authorization Type

</td>
<td valign="top">

OAuth Scope

</td>
</tr>
<tr>
<td valign="top">

Scope Key

</td>
<td valign="top">

scp

</td>
</tr>
<tr>
<td valign="top">

Scope

</td>
<td valign="top">

orders.read

</td>
</tr>
</table>

**Example**

Incoming JWT token:

```
{
  "iss": "https://idp.example.com",
  "sub": "user123",
  "scp": "orders.read orders.write"
}
```

**Result**: Access is allowed because the token contains ***orders.read***.

If the token contains only: ***"scp": "orders.write"***then the request is rejected with an authorization error.

</td>
</tr>
<tr>
<td valign="top">

Developer Key

</td>
<td valign="top">

Access is granted only when the JWT token contains a valid developer key, which the API caller obtains using credentials available in the Developer Hub.

</td>
<td valign="top">

-   The scope present in the JWT token is not validated.
-   Only the developer key is validated and matched.



</td>
<td valign="top">

The request is authorized when:

-   the JWT token contains a valid developer key, and
-   the developer key matches the configured subscription or client key.

> ### Note:  
> Scopes contained in the JWT token are ignored for this authorization type.



</td>
</tr>
<tr>
<td valign="top">

OAuth Scope OR Developer Key

</td>
<td valign="top">

Access is granted when either the required OAuth scope or a valid developer key is present.

</td>
<td valign="top">

The request is authorized if either of the following conditions is satisfied:

-   The JWT token contains the required scope, OR
-   The JWT token contains a valid developer key



</td>
<td valign="top">

The endpoint can be invoked successfully when:

-   a valid JWT token from the PIR instance or external IdP contains the required scope, or
-   the JWT token contains a valid developer key.

**Example Scenarios**


<table>
<tr>
<th valign="top">

JWT Scope Present

</th>
<th valign="top">

Developer Key Present

</th>
<th valign="top">

Result

</th>
</tr>
<tr>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
<td valign="top">

Authorized

</td>
</tr>
<tr>
<td valign="top">

No

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Authorized

</td>
</tr>
<tr>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Authorized

</td>
</tr>
<tr>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
<td valign="top">

Rejected

</td>
</tr>
</table>



</td>
</tr>
<tr>
<td valign="top">

OAuth Scope AND Developer Key

</td>
<td valign="top">

Access is granted only when both the required OAuth scope and a valid developer key are present.

</td>
<td valign="top">

The request is authorized only when:

-   the JWT token contains the required authorization scope, AND
-   the JWT token contains the correct developer key



</td>
<td valign="top">

Both validations must succeed before the request is forwarded to the backend service.


<table>
<tr>
<th valign="top">

JWT Scope Present

</th>
<th valign="top">

Developer Key Present

</th>
<th valign="top">

Result

</th>
</tr>
<tr>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Authorized

</td>
</tr>
<tr>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
<td valign="top">

Rejected

</td>
</tr>
<tr>
<td valign="top">

No

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Rejected

</td>
</tr>
<tr>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
<td valign="top">

Rejected

</td>
</tr>
</table>



</td>
</tr>
</table>



## Error Codes


<table>
<tr>
<th valign="top">

HTTP Status Code

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

403

</td>
<td valign="top">

Forbidden. User doesn’t have the authorization to perform this operation. Please contact your administrator.

</td>
</tr>
<tr>
<td valign="top">

403

</td>
<td valign="top">

Not allowed. Request unauthenticated. User is not allowed to perform this operation. Please authenticate and ensure you have the necessary permissions.

</td>
</tr>
</table>

**Related Information**  


[Authentication](authentication-fa6eec4.md "Different APIs may have various authentication mechanisms. The Authentication policy supports both external OAuth-based identity providers (OIDC) and the SAP internal identity provider (IDP).")

[JSON Threat Protection](json-threat-protection-c4991a6.md "Minimizes the risk posed by content-level attacks by enabling specific limits on various JSON structures, such as arrays and strings.")

[XML Threat Protection](xml-threat-protection-2e04b93.md "An XML Threat Protection policy safeguards XML-based applications and APIs from malicious attacks. It enforces rules on XML data to prevent threats such as recursive payloads, excessive node depth, and oversized payloads.")

[API Validation](api-validation-02ff41b.md "The API validation policy enables you to validate incoming request messages against an OpenAPI 3.0 Specification.")

