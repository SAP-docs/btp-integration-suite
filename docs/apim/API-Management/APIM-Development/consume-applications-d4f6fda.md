<!-- loiod4f6fda3ba314f2ebb4fd4a735a3384e -->

# Consume Applications

Once you create an Application, you can then consume the APIs based on your business requirements.

On subscribing to an application, the application developer receives an API key that the application must pass on every request to the API. API keys provide a simple mechanism for authenticating applications.

API Management generates API keys for applications, and enables you to add API key-based authentication to your APIs using policies. However, enforcement of the key is performed at the API proxy level, not by the API product itself. Therefore, you must ensure that all API proxies, and the corresponding resources defined by those API proxies, implement some form of key validation.

Before you use the API keys, ensure you are aware of the policies that support API keys and their functionality. There are two popular ways how APIKeys are provisioned. They are provided either as part of a Simple APIKey verification or as part of OAuth verification.



## VerifyAPIKey Validation

If you define an API proxy to perform key validation by using the VerifyAPIKey policy, provide the API Key details to gain access to the applications.



## OAuth 2.0 Validation

API Management supports standard OAuth flow. Currently SAP supports only Client credentials grant\_type in OAuth.

Before you start, make a note of the Application key and secret for the required application.

A request is made using the following:

-   URL: <URL of OAuth token\>
-   Method: POST
-   Custom Header: Authorization value: Basic <`Application key`\>:<`Application secret`\>\(base64 encoded\)
-   Payload: grant\_type=client\_credentials

This call returns a json payload with the OAuth validation response. On successful validation, it contains the access token. Note down the access token.

As default, the expiry time is configured to 3600 secs \(1 hr\). You can also configure the expiration time and the details that have to be displayed as part of the response.

You can now use this access token to fetch OAuth enabled services while making the actual business API call:

-   URL: http\[s\]://<host\>:<port\>/<service\_path\>
-   Custom Header: Authorization value: Bearer <access\_token\>

If the access token is valid, a valid service response is returned.

