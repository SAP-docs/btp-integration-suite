<!-- loio68f0246b5016408284691dc5f72a9847 -->

# Designing OAuth v2.0 Policies

The table below illustrates the various elements and attributes used in the OAuth policies:


<table>
<tr>
<th valign="top">

**Name**

</th>
<th valign="top">

**Description**

</th>
<th valign="top">

**Valid Values**

</th>
<th valign="top">

**Related Operation and Grant Type**

**Combinations**

</th>
</tr>
<tr>
<td valign="top">

Operation

</td>
<td valign="top">

The OAuth 2.0 operation implemented by the policy

</td>
<td valign="top">

GenerateAccessToken

GenerateAccessTokenImplicitGrant

GenerateAuthorizationCode

RefreshAccessToken

VerifyAccessToken

</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top">

ExpiresIn\(optional\)

</td>
<td valign="top">

ExpiresIn enforces the expiry time of the authorization code in milliseconds. The expiry time of authorization code is system generated plusExpiresInvalue. IfExpiresInis -1, the system considers it as an infinite life time. If it is not specified, the system applies a default value configured at system level.

</td>
<td valign="top">

GenerateAccessToken

GenerateAccessTokenImplicitGrant

GenerateAuthorizationCode

RefreshAccessToken

VerifyAccessToken

</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top">

SupportedGrant Types

</td>
<td valign="top">

Specifies the GrantTypes supported by a token endpoint.

An endpoint may support multiple GrantTypes \(that is, a single endpoint can be configured to distribute access tokens for multiple GrantTypes.\)

</td>
<td valign="top">

client\_credentials

authorization\_code

implicit

</td>
<td valign="top">

All

</td>
</tr>
<tr>
<td valign="top">

Code

</td>
<td valign="top">

The expected location in the request message where the authorization code must be presented to the token endpoint

</td>
<td valign="top">

Any variable setting. For example request.queryparam.auth\_code indicates that the authorization code should be present as a query parameter, as, for example, ?auth\_code=AfGlvs9. To require the authorization code in an HTTP header, for example, set this value to request.header.auth\_code.

</td>
<td valign="top">

GenerateAccessToken with grant typeauthorization\_code

</td>
</tr>
<tr>
<td valign="top">

ClientId

</td>
<td valign="top">

The expected location in the request message where the client\_id \(the app's consumer key\) must be presented to the token endpoint

</td>
<td valign="top">

Any variable setting. For example request.queryparam.client\_id indicates that the client\_id should be present as a query parameter, as, for example, ?client\_id=AfGlvs9.

To require the ClientId in an HTTP header, for example, set this value

to request.header.client\_id.

</td>
<td valign="top">

GenerateAccessToken

Implicit: Optional

GenerateAuthorization

Code:Optional

</td>
</tr>
<tr>
<td valign="top">

RedirectUri

</td>
<td valign="top">

The expected location in the request message where the RedirectUri must be presented to the token endpoint.

</td>
<td valign="top">

Any variable setting. For example, request.queryparam.redirect\_uriindicates that the RedirectUri should be present as a query parameter, as, for example,?redirect\_uri=login.myapp.com. To require the RedirectUri in an HTTP header, for example, set this value to request.header.redirect\_uri.

</td>
<td valign="top">

GenerateAccessToken

Implicit: Optional

GenerateAuthorization

Code:Optional

</td>
</tr>
<tr>
<td valign="top">

Scope

</td>
<td valign="top">

The expected location in the request message where the scope must be presented to the token endpoint.

</td>
<td valign="top">

Any variable setting. For example, request.queryparam.scope indicates that the scope should be present as a query parameter, as, for example, ?scope=READ. To require the scope in an HTTP header, for example, set this value to request.header.scope.

</td>
<td valign="top">

All: Optional

</td>
</tr>
<tr>
<td valign="top">

State

</td>
<td valign="top">

The expected location in the request message where the state must be presented to the token endpoint.

</td>
<td valign="top">

Any variable setting. For example request.queryparam.state indicates that the state should be present as a query parameter, as, for example, ?state=HjoiuKJH32.

To require the state in an HTTP header, for example, set this value to request.header.state.

</td>
<td valign="top">

authorization\_code,

password

</td>
</tr>
<tr>
<td valign="top">

AppEndUser

</td>
<td valign="top">

The expected location in the request message where the state must be presented to the token endpoint.

</td>
<td valign="top">

Any variable setting. For example request.queryparam.app\_enduserindicates that the AppEndUser should be present as a query parameter, as, for example,?app\_enduser=ntesla@theramin.com. To require the AppEndUser in an HTTP header, for example, set this value torequest.header.app\_enduser.

</td>
<td valign="top">

All: Optional

</td>
</tr>
<tr>
<td valign="top">

UserName

</td>
<td valign="top">

The expected location in the request message where the UserName must be presented to the token endpoint.

</td>
<td valign="top">

Any variable setting. For example request.queryparam.username indicates that the username should be present as a query parameter, as, for example,?username=joe. To require the UserName in an HTTP header, for example, set this value to request.header.username.

</td>
<td valign="top">

All: Optional

</td>
</tr>
<tr>
<td valign="top">

Password

</td>
<td valign="top">

The expected location in the request message where the Password must be presented to the token endpoint.

</td>
<td valign="top">

Any variable setting. For example request.queryparam.password indicates that the Password should be present as a query parameter, as, for example,?password=changeit. To require the Password in an HTTP header, for example, set this value to request.header.password.

</td>
<td valign="top">

All: Optional

</td>
</tr>
<tr>
<td valign="top">

GenerateResp onse

</td>
<td valign="top">

An element used in token endpoints, authorization endpoints, and refresh endpoints to indicate that a response should be generated for requests, and that no further processing should take place. \(Indicates that the policy is an endpoint.\)

</td>
<td valign="top">

N/A

</td>
<td valign="top">

All: Optional

</td>
</tr>
</table>

