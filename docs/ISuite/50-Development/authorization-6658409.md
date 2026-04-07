<!-- loio6658409a114a4c038572276335bea8b9 -->

# Authorization

This policy evaluates whether a user should be permitted to access a protected API.

> ### Note:  
> This feature and the information is relevant only if you have activated Edge Integration Cell in your SAP Integration Suite tenant. Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

Different iFlow sender channels may have different authorizations and roles. For API artifact, different resources may have different authorization and roles configured.

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

Scope Key

</td>
<td valign="top">

The name of the JWT claim where the scope information is present.

</td>
<td valign="top" rowspan="2">

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

    > ### Note:  
    > The scopes are not in the standard scope claim. They are present in a custom claim called scp.

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

Scope

</td>
<td valign="top">

The specific scope\(s\) that must be present in the token for the request to be authorized.

Please make sure that the user attempting to invoke the API endpoint is assigned at least one of the roles defined in the scope field.

> ### Note:  
> Either the role entered in the scope field should be preconfigured in the *User Roles* section of the *Monitor* view under the *Manage Security* section or you must add the role you've entered in the scope field in *User Roles*. To learn how to configure the role, see [Managing User Roles](https://help.sap.com/docs/integration-suite/sap-integration-suite/managing-user-roles?q=Defining%20Permissions%20for%20Senders%20to%20Process%20Messages%20on%20a%20Runtime%20Node).

For example, if you’ve configured a role called `APIArtifactUser` in *User Roles*, you must enter the role exactly as it is \(including case sensitivity\) in the scope field or vice versa.

Once the `APIArtifactUser` role is configured in *User Roles*, it is automatically added to the *Roles* in SAP BTP Cockpit.

To execute an API with the Authorization policy successfully on the runtime node, the `APIArtifactUser` role should be associated to the *Process Integration Runtime* instance. For step-by-step instruction on how to create a *Process Integration Runtime* instance, see [Invoke an API Artifact by Obtaining API Credentials through Process Integration Runtime](invoke-an-api-artifact-by-obtaining-api-credentials-through-process-integration-runtime-b63baa2.md).

</td>
</tr>
</table>

**Related Information**  


[Authentication](authentication-fa6eec4.md "Different APIs may have various authentication mechanisms. The Authentication policy supports both external OAuth-based identity providers (OIDC) and the SAP internal identity provider (IDP).")

[JSON Threat Protection](json-threat-protection-c4991a6.md "Minimizes the risk posed by content-level attacks by enabling specific limits on various JSON structures, such as arrays and strings.")

[XML Threat Protection](xml-threat-protection-2e04b93.md "An XML Threat Protection policy safeguards XML-based applications and APIs from malicious attacks. It enforces rules on XML data to prevent threats such as recursive payloads, excessive node depth, and oversized payloads.")

[API Validation](api-validation-02ff41b.md "The API validation policy enables you to validate incoming request messages against an OpenAPI 3.0 Specification.")

