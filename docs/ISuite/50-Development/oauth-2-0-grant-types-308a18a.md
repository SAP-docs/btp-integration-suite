<!-- loio308a18a3f6324db4815b35dcdfa6b789 -->

# OAuth 2.0 Grant Types

OAuth 2.0 policies such as generate access token and generate authorization code use the GrantType method element. The below table illustrates the three supported grant types:


<table>
<tr>
<th valign="top">

**Grant Type**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

Clientcredentials

</td>
<td valign="top">

"Two-legged" OAuth, usually implemented for trusted clients \(for example, applications developed by the API provider themselves\).

</td>
</tr>
<tr>
<td valign="top">

Authorizationcode

</td>
<td valign="top">

"Three-legged" OAuth, which enables the application end users to obtain an access token without exposing credentials to the application. The application requests an access token using an authorization code returned by the intermediary who authenticates the application end user. API Platform can act as both authorization server \(generating authorization codes\) and as a token endpoint \(issuing access tokens in return for valid authorization codes\).

</td>
</tr>
<tr>
<td valign="top">

Implicit

</td>
<td valign="top">

A variation on authorization code, usually enforced for browser-based applications that are implemented in scripting languages such as JavaScript

</td>
</tr>
</table>

