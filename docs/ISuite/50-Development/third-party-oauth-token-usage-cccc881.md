<!-- loiocccc88169bc446539ee7dab7c9b6ccb3 -->

# Third-Party OAuth Token Usage

Import externally generated access tokens, refresh tokens, or auth codes into the API Management token store. You can use this technique if you would like to configure API Management to validate tokens that are generated outside of SAP Integration Suite.

> ### Note:  
> The size of third-party tokens must be 2 KB or smaller.

In typical scenarios, API Management generates and stores an OAuth token, which is then returned to the calling application. The calling app subsequently presents this token to API Management when requesting a service, and API Management via the OAuthV2 policy with `Operation = VerifyAccessToken`, verifies the token's validity. This topic explains how to configure API Management to store an OAuth token generated elsewhere, while maintaining the same token verification process as if the token were generated by API Management.

Let's say you already have an authorization system up and running. You want to use the token or code values produced by this system instead of the OAuth2 token or code values generated by API Management. You can then make secure API proxy requests using the substituted token or code. API Management validates them as though they're its own.



<a name="loiocccc88169bc446539ee7dab7c9b6ccb3__section_s53_sfc_pdc"/>

## Context

Typically, API Management generates a token by producing a random string of letters and numbers. It then links this token to other data. This data includes the time the token was issued, its expiration date, the list of API Products the token is valid for, and the scope. All of this information can be returned in a response automatically generated by the OAuthV2 policy configured with `Operation = GenerateAccessToken`. Here's what the response looks like:

> ### Sample Code:  
> ```
> {
>   "issued_at": "1469735625687",
>   "application_name": "06947a86-919e-4ca3-ac72-036723b18231",
>   "scope": "urn://example.com/read",
>   "status": "approved",
>   "api_product_list": "[implicit-test]",
>   "api_product_list_json": ["implicit-test"],
>   "expires_in": "1799", //--in seconds
>   "developer.email": "joe@weathersample.com",
>   "token_type": "BearerToken",
>   "client_id": "U9AC66e9YFyI1yqaXgUF8H6b9wUN1TLk",
>   "access_token": "zBC90HhCGmGlaMBWeZAai2s3za5j",
>   "organization_name": "wwitman",
>   "refresh_token_expires_in": "0", //--in seconds
>   "refresh_count": "0"
> }
> ```

The **`access_token`** attribute's value essentially serves as the lookup key for the response data. Suppose an app makes a request to an API proxy hosted in API Management, carrying the bearer token **zBC90HhCGmGlaMBWeZAai2s3za5j**. In that case, API Management uses the OAuthV2 policy with `Operation = VerifyAccessToken` to look up the token. It retrieves all the information and uses it to determine the token's validity for the requested API Proxy. This process is known as Token validation. The token comprises all the information mentioned above. The **`access_token`** value is simply the way to look up that information.

Alternatively, you can set up API Management to store a token by following these steps. This token's `access_token` value is generated by an external service. The rest of the metadata typically remains the same. For instance, let's say you have an external system to API Management that generates tokens in the format **TOKEN-<16 random numbers\>**. In this scenario, the complete token metadata stored by API Management might look like the below:

> ### Sample Code:  
> ```
> {
>   "issued_at": "1469735625687",
>   "application_name": "06947a86-919e-4ca3-ac72-036723b18231",
>   "scope": "urn://example.com/read",
>   "status": "approved",
>   "api_product_list": "[implicit-test]",
>   "api_product_list_json": ["implicit-test"],
>   "expires_in": "1799", //--in seconds
>   "developer.email": "joe@weathersample.com",
>   "token_type": "BearerToken",
>   "client_id": "U9AC66e9YFyI1yqaXgUF8H6b9wUN1TLk",
>   "access_token": "TOKEN-1092837373654221",
>   "organization_name": "wwitman",
>   "refresh_token_expires_in": "0", //--in seconds
>   "refresh_count": "0"
> }
> ```

In this case, an app could make a request to an API proxy hosted in API Management, carrying the bearer token **TOKEN-1092837373654221**, and API Management - via the OAuthV2 policy with `Operation = VerifyAccessToken`- will be able to validate it. You can apply a similar import pattern to authorization codes and refresh tokens.



<a name="loiocccc88169bc446539ee7dab7c9b6ccb3__section_gpw_vlc_pdc"/>

## Validating Client Credentials

As a prerequisite, to generate a token, you first need to validate the requesting client. The OAuthV2 policy's [Generate Access Token](generate-access-token-f6f84ee.md) operation in API Management does this by default, checking the client credentials implicitly. Typically, in a request for an OAuthV2 token, the `client_id` and `client_secret` are passed in the Authorization header, encoded via HTTP Basic Authorization \(colon-concatenated, then base64-encoded\). The **OAuthV2/GenerateAccessToken** policy in API Management then decodes this header. It looks up the `client_id` and verifies if the provided `client_secret` is valid for that `client_id`.

In the event that the client credentials are not to be validated by API Management, it is necessary to design your API Proxy, before it generates a token, to explicitly validate the client through other methods. This is often accomplished through a ServiceCallout policy that connects to a remote endpoint in your network.

One way or the other, either implicitly or explicitly, you need to ensure that the API proxy that generates tokens, first validates the client credentials. Remember, validating the client is independent of generating the access token. You have the flexibility to configure API Management to perform both tasks, just one, or neither.

If you want the **OAuthV2/GenerateAccessToken** policy in API Management to validate the client credentials against the API Management store, set the **`<ExternalAuthorization>`** element to **`false`** inside the policy configuration, or omit it entirely. If you want to use an external authorization service to explicitly validate the client credentials, set **`<ExternalAuthorization>`** to **`true`**.

API Management might not validate client credentials, but it's still essential for it to know and manage the `client_id`. Every `access_token` in API Management, whether it's generated by API Management or by an external system and then imported, needs to be associated to a client application, indicated by the `client_id`. Even when the **OAuthV2/GenerateAccessToken** policy in API Management doesn't verify the match between the `client_id` and `client_secret`, it checks that the `client_id` is valid, present, and not revoked. Therefore, as a prerequisite setup step, you might need to import client\_ids using the API Management administrative API.



<a name="loiocccc88169bc446539ee7dab7c9b6ccb3__section_sck_qqc_pdc"/>

## Policy Flow for Third-party OAuth

To use tokens from third-party OAuth systems in API Management, the flow for generating access tokens should adhere to one of the following patterns:



### External Validation of Client Credentials

1.  Use the [Service Callout](service-callout-6b40873.md) policy to verify the inbound client credentials and acquire an external token.
2.  Use the [Extract Variables](extract-variables-dad6ef6.md) or [JavaScript](javascript-5b63ed7.md) policies to extract the externally-generated token from the response.
3.  Use the [Assign Message](assign-message-523efe6.md) policy to set the special well-known-variable called `oauth_external_authorization_status`. The value must be **`true`** to indicate the client credentials are valid.

4.  Use the [OAuthV2/Generate Access Token](generate-access-token-f6f84ee.md) policy with the `<ExternalAuthorization>` element set to `true`, and at least one of `<ExternalAccessToken>`, `<ExternalRefreshToken>`, or `<ExternalAuthorizationCode>`.



### Internal Validation of Client Credentials

1.  Use the [Service Callout](service-callout-6b40873.md) policy to acquire an external token.
2.  Use the [Extract Variables](extract-variables-dad6ef6.md) or [JavaScript](javascript-5b63ed7.md) policies to extract the externally-generated token from the response.
3.  Use the [OAuthV2/Generate Access Token](generate-access-token-f6f84ee.md) policy with the `<ExternalAuthorization>` element set to `false`, and at least one of `<ExternalAccessToken>`, `<ExternalRefreshToken>`, or `<ExternalAuthorizationCode>`.



<a name="loiocccc88169bc446539ee7dab7c9b6ccb3__section_k44_3v3_pdc"/>

## Few Points on the Flow and Policy Configuration

> ### Note:  
> The size of third-party tokens must be 2 KB or smaller.

-   If you want to use an external system to validate the client credentials, it is up to you to develop a policy flow that does the job. Usually, you use a [Service Callout](service-callout-6b40873.md) policy to send the externally recognized credentials to the external authentication service. This service would typically return a response. If the credentials are valid, it also provides an access token.

-   After the **Service Callout**, the API proxy is required to parse the response in order to extract the validity status. Additionally, it may also need to extract the externally generated `access_token` and possibly the `refresh_token`.

-   In the [OAuthV2/Generate Access Token](generate-access-token-f6f84ee.md) policy, set the `<StoreToken>` element to `true`, and set the `<ExternalAuthorization>` element to `true` or `false` as appropriate.

    When the **OAuthV2/GenerateAccessToken** policy executes, it reads the variable `oauth_external_authorization_status`. If the variable is set and the value is `true`, then API Management does not attempt to validate the client credentials. If the variable is not set or the value is not true, then API Management will attempt to validate client credentials.

-   There are three elements for the OAuthV2 policy that allow you to specify the external data to import: `<ExternalAccessToken>`, `<ExternalRefreshToken>`, and `<ExternalAuthorizationCode>`. Each of these elements accepts a flow variable. The API Management policy will read that variable to find the externally-generated access token, refresh token, or authorization code. It's up to you to implement policies and logic to place the external tokens or codes in the appropriate variables.

-   For example, the following configuration in the OAuthV2 policy tells API Management to look for the token in a context variable named `external_token`:

    > ### Sample Code:  
    > ```
    > <ExternalAccessToken>external_token</ExternalAccessToken>
    > ```

    Remember, you would also need a previous step that sets this variable.

-   In terms of setting the `oauth_external_authorization_status variable`, a frequently used method is to use an [Assign Message](assign-message-523efe6.md) policy with the `AssignVariable` element. Here is an example:

    > ### Sample Code:  
    > ```
    > <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
    > <AssignMessage async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
    > <AssignVariable>
    > <Name>oauth_external_authorization_status</Name>
    > <Value>true</Value>
    > </AssignVariable>
    > <IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
    > <AssignTo createNew="false" transport="http" type="request"></AssignTo>
    > </AssignMessage>
    > ```

    Remember, this policy must fall before the OAuthV2 policy with `Operation = GenerateAccessToken`.




<a name="loiocccc88169bc446539ee7dab7c9b6ccb3__section_gqb_tz3_pdc"/>

## Example: OAuthV2 Policy

The following OAuthV2 policy generates an API Management access token given that API Management finds a token value in the flow variable `external_access_token`:

> ### Sample Code:  
> ```
> <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
> <OAuthV2 async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
> <ExternalAccessToken>external_access_token</ExternalAccessToken>
> <ExternalAuthorization>true</ExternalAuthorization>
> <Operation>GenerateAccessToken</Operation>
> <GenerateResponse enabled="true"/>
> <StoreToken>true</StoreToken>
> <SupportedGrantTypes>
> <GrantType>client_credentials</GrantType>
> </SupportedGrantTypes>
> </OAuthV2>
> ```

> ### Note:  
> Normally, with the client credentials grant type, you need to provide a Basic Authentication header with the encoded Client ID and Client Secret. However, in this case, you do not need to provide that header. The policy still expects the `client_id` to be present in the request, and the policy will validate it. API Management expects the `client_id` to be sent as part of the request form data, for example, in **`request.formparam.client_id`**.

In theory, you could apply this pattern with any third-party OAuth2 authorization service.

