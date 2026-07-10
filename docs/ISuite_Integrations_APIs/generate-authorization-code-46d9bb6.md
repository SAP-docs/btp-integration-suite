<!-- loio46d9bb6a604d4056b8815d2daf6e0d8e -->

# Generate Authorization Code

Similarly, you can configure authorization endpoints to issue authorization codes.

For example:

> ### Sample Code:  
> ```
> 
> <Flow name="AuthorizationEndpoint">
> 	<Condition>proxy.pathsuffix == "/authorize"</Condition>
> 	<Request>
> 	<Step><Name>GenerateAuthCode</Name></Step>
> 	</Request>
> </Flow>
> ```

This policy needs to be attached to the response to generate the authorization code.

> ### Note:  
> An example payload for the policy is as follows.

> ### Code Syntax:  
> ```
> 
> <OAuthV2 async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <ClientId>request.queryparam.client_id</ClientId> 
>     <Operation>GenerateAuthorizationCode</Operation>
>     <RedirectUri>request.queryparam.redirect_uri</RedirectUri> 
>     <GenerateResponse enabled="true"/>
>     <ResponseType>request.queryparam.response_type</ResponseType> 
>     <Scope>request.queryparam.scope</Scope>
>    <Tokens/>
> </OAuthV2>
> 
> 
> <!-- sample API call to get the auth code -->
> 
> https://<auth -endpoint>?redirect_uri=https://<your-app-redirect-url> &response_type=code&scope=read&state=1&client_id=<a_valid_app_key>
> 
> Here the response will be HTTP 302 and the code will be sent to app-redirect-url as an query parameter e.g.
> 
> HTTP 302 https://<your-app-redirect-url>?code=<the_genreate_code> &state=1&scope=read
> 
> ```

These variables are set when the GenerateAuthorizationCode policy operation executes successfully:

**Authorization Code**


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

oauthv2authcode.\{policy\_name\}.code

</td>
<td valign="top">

The authorization code generated when the policy executes.

</td>
</tr>
<tr>
<td valign="top">

oauthv2authcode.\{policy\_name\}.redirect\_uri

</td>
<td valign="top">

The redirect URI associated with the registered client app.

</td>
</tr>
<tr>
<td valign="top">

oauthv2authcode.\{policy\_name\}.scope

</td>
<td valign="top">

The optional OAuth scope passed in the client request.

</td>
</tr>
<tr>
<td valign="top">

oauthv2authcode.\{policy\_name\}.client\_id

</td>
<td valign="top">

The client ID passed in the client request.

</td>
</tr>
</table>

For information on the various `GrantType` supported, see [OAuth 2.0 Grant Types](oauth-2-0-grant-types-308a18a.md). For information on the various field descriptions \(supported elements and attributes\), see [Designing OAuth v2.0 Policies](designing-oauth-v2-0-policies-68f0246.md).

