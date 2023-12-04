<!-- loio2e507ea5a8894836bba0877251840e4e -->

# OAuth v2.0 GET

API Management generates and manages a set of OAuth resources for apps.

Depending on the OAuth configuration for an organization, API Management will generate and manage access tokens, authorization codes, and refresh tokens. For each OAuth resource that it generates, API Management also creates and stores a profile.

The GetOauthV2Info policy type enables you to get attributes of type tokens and authorization codes and to make them available to policies and code executing in an API proxy. This policy type can be useful when you need to configure dynamic, conditional behavior based on a value in an access token.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An access token has the following JSON representation on API Management:

> ### Code Syntax:  
> ```
> 
> {
> "issued_at" : "1847470170943",
> "application_name" : "efd1903j-b667-4431-cf82-bbb3abf9t586",
> "scope": "READ",
> "status" : "approved",
> "api_product_list" : "[FreeProduct]",
> "expires_in" : "2450",
> "developer.email" : "adam@sap.com",
> "organization_id" : "0",
> "refresh_token" : "64XMXgDyRFpFyXOaApj1N7AGIPnN2IZe",
> "client_id" : "ceGYedE0Y9Z0T35PEMaAXYphBJCGdrND",
> "access_token" : "shTUmeI1geSKin0TODcGLXBNe9vp",
> "organization_name" : "apifactory",
> "refresh_count" : "0"
> }
> ```

The properties of an access token profile are set as variables whenever a token is generated or validated. Sometimes, however, you will need to access these properties when no token generation or validation occurs. To do so, you can explicitly populate the access token profile by using the GetOAuthV2Info policy.

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <GetOAuthV2Info async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
>     <AccessToken ref="request.access_token"></AccessToken>
>     <ClientId ref="request.header.client_id"></ClientId>
> </GetOAuthV2Info
>  
> ```

OAuth v2.0 GET policy defines the following elements:


<table>
<tr>
<th valign="top">

**Field Name**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

AccessToken \(Optional\)

</td>
<td valign="top">

Use this element to retrieve the profile for an OAuth 2.0 access token.

</td>
</tr>
<tr>
<td valign="top">

AuthorizationCode \(Optional\)

</td>
<td valign="top">

Use this element to retrieve the profile for an OAuth

2.0 authorization code.

</td>
</tr>
<tr>
<td valign="top">

ClientId

</td>
<td valign="top">

Use this element to retrieve information about ClientId.

</td>
</tr>
<tr>
<td valign="top">

RefreshToken \(Optional\)

</td>
<td valign="top">

Use this element to retrieve the profile for an OAuth

2.0 refresh token.

</td>
</tr>
</table>

OAuth v2.0 GET policy defines the following errors:


<table>
<tr>
<th valign="top">

Error Name

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

invalid\_access\_token

</td>
<td valign="top">

The access token sent to the policy is invalid.

</td>
</tr>
<tr>
<td valign="top">

expired\_access\_token

</td>
<td valign="top">

The access token sent to the policy is expired.

</td>
</tr>
<tr>
<td valign="top">

invalid\_refresh\_token

</td>
<td valign="top">

The refresh token sent to the policy is invalid.

</td>
</tr>
<tr>
<td valign="top">

refresh\_token\_expired

</td>
<td valign="top">

The refresh token sent to the policy is expired.

</td>
</tr>
<tr>
<td valign="top">

invalid\_client-invalid\_client\_id

</td>
<td valign="top">

The client ID sent to the policy is invalid.

</td>
</tr>
<tr>
<td valign="top">

invalid\_request-authorization\_code\_invalid

</td>
<td valign="top">

The authorization code sent to the policy is invalid.

</td>
</tr>
<tr>
<td valign="top">

authorization\_code\_expired

</td>
<td valign="top">

The authorization code sent to the policy is expired.

</td>
</tr>
</table>

Following flow variables are populated and is used in cases where you need the profile data:

**Flow Variables**


<table>
<tr>
<th valign="top">

Variable Type

</th>
<th valign="top">

When

</th>
<th valign="top">

Variables list

</th>
</tr>
<tr>
<td valign="top">

Client ID variables

</td>
<td valign="top">

These variables are populated when the <ClientId\> operation executes

</td>
<td valign="top">

oauthv2client.\{policy\_name\}.client\_id

oauthv2client.\{policy\_name\}.client\_secret

oauthv2client.\{policy\_name\}.redirection\_uris

oauthv2client.\{policy\_name\}.developer.email

oauthv2client.\{policy\_name\}.developer.app.name

oauthv2client.\{policy\_name\}.developer.id

oauthv2client.\{policy\_name\}.\{developer\_app\_custom\_attribute\_name\}

</td>
</tr>
<tr>
<td valign="top">

Access token variables

</td>
<td valign="top">

These variables are populated when the <AccessToken\> operation executes

</td>
<td valign="top">

oauthv2accesstoken.\{policy\_name\}.access\_token

oauthv2accesstoken.\{policy\_name\}.scope

oauthv2accesstoken.\{policy\_name\}.refresh\_token

oauthv2accesstoken.\{policy\_name\}.accesstoken.\{custom\_attribute\_name\}

oauthv2accesstoken.\{policy\_name\}.developer.id

oauthv2accesstoken.\{policy\_name\}.developer.app.name

oauthv2accesstoken.\{policy\_name\}.expires\_in

oauthv2accesstoken.\{policy\_name\}.status

</td>
</tr>
<tr>
<td valign="top">

Authorization code variables

</td>
<td valign="top">

These variables are populated when the <AuthorizationCode\> operation executes

</td>
<td valign="top">

oauthv2authcode.\{policy\_name\}.client\_id

oauthv2authcode.\{policy\_name\}.organization\_id

oauthv2authcode.\{policy\_name\}.issued\_at

oauthv2authcode.\{policy\_name\}.expires\_in

oauthv2authcode.\{policy\_name\}.redirect\_uri

oauthv2authcode.\{policy\_name\}.status

oauthv2authcode.\{policy\_name\}.state

oauthv2authcode.\{policy\_name\}.scope

oauthv2authcode.\{policy\_name\}.id

oauthv2authcode.\{policy\_name\}.\{auth\_code\_custom\_attribute\_name\}

</td>
</tr>
<tr>
<td valign="top">

Refresh token variables

</td>
<td valign="top">

These variables are populated when the <RefreshToken\> operation executes

</td>
<td valign="top">

oauthv2refreshtoken.\{policy\_name\}.access\_token

oauthv2refreshtoken.\{policy\_name\}.refresh\_token

oauthv2refreshtoken.\{policy\_name\}.client\_id

oauthv2refreshtoken.\{policy\_name\}.refresh\_count

oauthv2refreshtoken.\{policy\_name\}.organization\_name

oauthv2refreshtoken.\{policy\_name\}.refresh\_token\_expires\_in

oauthv2refreshtoken.\{policy\_name\}.refresh\_token\_issued\_at

oauthv2refreshtoken.\{policy\_name\}.refresh\_token\_status

oauthv2refreshtoken.\{policy\_name\}.developer.email

oauthv2refreshtoken.\{policy\_name\}.developer.id

oauthv2refreshtoken.\{policy\_name\}.developer.app.name

oauthv2refreshtoken.\{policy\_name\}.developer.app.id

oauthv2refreshtoken.\{policy\_name\}.accesstoken.\{custom\_attribute\_name\}

</td>
</tr>
</table>

