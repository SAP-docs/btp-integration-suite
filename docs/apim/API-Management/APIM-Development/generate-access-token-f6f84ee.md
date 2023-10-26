<!-- loiof6f84eeb5e3a455b9530d9a534b4d91b -->

# Generate Access Token

OAuth 2.0 policies are used both to generate and to validate OAuth 2.0-compliant tokens. To generate tokens on behalf of application end users, OAuth 2.0 policies that specify the GenerateAccessToken operation are attached to a token endpoint.

> ### Note:  
> Deploy a single API proxy to function as a token endpoint for all API proxies in an environment. A single API proxy configured as a token endpoint can support multiple grant types. By setting up a single token endpoint, you can publish a unified set of URIs that application developers can use to obtain tokens.

A token endpoint is simply a URI path that the system uses to identify requests for access tokens. On API Management, a token endpoint is a conditional flow to which an OAuthV2 policy is attached. The OAuthV2 policy specifies the GenerateAccessToken operation as an element. For example, to configure a token endpoint that generates tokens on requests to the URI path /accesstoken:

> ### Sample Code:  
> ```
> 
> <Flow name="TokenEndpoint">
> 	<Condition>proxy.pathsuffix MatchesPath "/accesstoken"</Condition>
> 	<Request>
> 	<Step><Name>GenerateAccessToken</Name></Step>
> 	</Request>
> </Flow> 
> ```

> ### Note:  
> An example payload for the policy is as follows.

> ### Code Syntax:  
> ```
> 
> <OAuthV2 async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
> <!-- this flag has to be set when you want to work with third-party access tokens -->
> <ExpiresIn ref="kvm.expiry.value">360000</ExpiresIn> <!-- in mili seconds -->
> <ExternalAuthorization>false</ExternalAuthorization>
> <GrantType>request.queryparam.grant_type</GrantType>
> <Operation>GenerateAccessToken</Operation>
> <PassWord>request.formparam.password</PassWord>
> <RedirectUri/>
> <RefreshToken/>
> <RefreshTokenExpiresIn ref="kvm.expiry.value">240000</RefreshTokenExpiresIn>
> <GenerateResponse enabled="true"/>
> <SupportedGrantTypes>
> <GrantType>client_credentials</GrantType>
> </SupportedGrantTypes>
> </OAuthV2>
> ```

These variables are set when the GenerateAccessToken policy operation executes successfully for the authorization code, password, and client credentials grant type flows. Note that refresh token variables do not apply to and are not set by the client credentials grant type flow.

**Access Token**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

oauthv2accesstoken.\{policy\_name\}.token\_type

</td>
<td valign="top">

Will be set to accesstoken.

</td>
</tr>
<tr>
<td valign="top">

oauthv2accesstoken.\{policy\_name\}.expires\_in

</td>
<td valign="top">

The expiry value for the token.

</td>
</tr>
<tr>
<td valign="top">

oauthv2accesstoken.\{policy\_name\}.refresh\_token

</td>
<td valign="top">

The refresh token generated when the policy executes.

</td>
</tr>
<tr>
<td valign="top">

oauthv2accesstoken.\{policy\_name\}.refresh\_token\_expires\_in

</td>
<td valign="top">

The lifespan of the refresh token, in seconds.

</td>
</tr>
<tr>
<td valign="top">

oauthv2accesstoken.\{policy\_name\}.refresh\_token\_issued\_at

</td>
<td valign="top">

This time value is the string representation of the corresponding 32-bit timestamp quantity.

</td>
</tr>
<tr>
<td valign="top">

oauthv2accesstoken.\{policy\_name\}.refresh\_token\_status

</td>
<td valign="top">

Set to approved or revoked.

</td>
</tr>
<tr>
<td valign="top">

oauthv2accesstoken.\{policy\_name\}.scope

</td>
<td valign="top">

List of available OAuth scopes.

</td>
</tr>
</table>

For information on the various `GrantType` supported, see [OAuth 2.0 Grant Types](oauth-2-0-grant-types-308a18a.md). For information on the various field descriptions \(supported elements and attributes\), see [Designing OAuth v2.0 Policies](designing-oauth-v2-0-policies-68f0246.md).

**Related Information**  


[Designing OAuth v2.0 Policies](designing-oauth-v2-0-policies-68f0246.md "")

[OAuth 2.0 Grant Types](oauth-2-0-grant-types-308a18a.md "")

