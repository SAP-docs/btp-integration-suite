<!-- loio744ce8a40bbb49a4aeca4d79244ddfa5 -->

# Verify Access Tokens

Once a token endpoint is set up for an API proxy, a corresponding OAuthV2 policy that specifies theVerifyAccessToken operation is attached to the Flow that exposes the protected resource.



## Example

To ensure that all requests to an API are authorized, the following policy enforces access token verification:

> ### Sample Code:  
> ```
> 
> <OAuthV2>
> 	<Operation>VerifyAccessToken</Operation>
> </OAuthV2>
> ```

The policy is attached to the API resource to be protected. To ensure that all requests to an API are verified, attach the policy to the proxy endpoint request PreFlow, as follows:

> ### Sample Code:  
> ```
> 
> <PreFlow>
> 	<Request>
> 	<Step><Name>VerifyOAuthAccessToken</Name></Step>
> 	</Request>
> </PreFlow>
> ```

The following optional elements can be used to override the default settings for the VerifyAccessToken operation


<table>
<tr>
<th valign="top">

**Name**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

Scope

</td>
<td valign="top">

A space separated list of scopes that must be present in the access token for verification to succeed. For example, the following policy will check the access token to ensure that it contains the scopes READ and WRITE:

> ### Sample Code:  
> ```
> 
> <OAuthV2>
> 	<Operation>VerifyAccessToken</Operation>
> 	<Scope>READ WRITE</Scope>
> </OAuthV2>
> ```



</td>
</tr>
<tr>
<td valign="top">

AccessToken

</td>
<td valign="top">

The variable where the access token is expected to be located. For example, request.queryparam.accesstoken. By default, the access token is expected to be presented by the application in the Authorization HTTP header, according to the OAuth 2.0 specification. Use this setting if the access token is expected to be presented in a nonstandard location. Such location may be a query parameter, or an HTTP header with a name other than Authorization.

</td>
</tr>
</table>

For information on the various field descriptions \(supported elements and attributes\), see [Designing OAuth v2.0 Policies](designing-oauth-v2-0-policies-68f0246.md).

