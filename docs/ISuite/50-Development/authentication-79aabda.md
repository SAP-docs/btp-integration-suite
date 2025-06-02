<!-- loio79aabdaea22a4846a7238231f8fbad77 -->

# Authentication

To communicate with Graph, client applications must present an access token, which they obtain from a security service during authentication: the process of verifying an identity \(such as a username\) of the user and the client by checking additional credentials \(such as a password\).

Client applications are not concerned with connections to the actual data sources – this is managed entirely by Graph.

Client applications follow the OAuth 2.0 protocol to obtain an access token. Graph supports two different scenarios, depending on the type of authentication flow required:

1.  User Authentication \(`authorization_code grant`\)

2.  Client Authentication \(`client_credentials grant`\)




<a name="loio79aabdaea22a4846a7238231f8fbad77__section_h54_qby_xrb"/>

## User Authentication

User authentication is used by Task or Workflow applications, which are required to authenticate \(human\) enterprise users. A typical use case might be an app that lets employees use their own identity to check their vacation quota.

It requires two steps, involving browser redirects. The first step is to receive an authorization code via a callback, and the second step exchanges the received authorization code for the access token. Applications that use this authentication method must be approved \(added to an allowlist\) by the SAP BTP administrator. For more information, see [Enable Client Applications](enable-client-applications-e904119.md).

In the first step, a `GET` call is made to the *security-service*`/oauth/authorize` endpoint with the following query parameters:

```json
client_id: <application client ID>
redirect_uri: <application URL that accepts the authorization code>
response_type: code
```

To then obtain the access token, a `POST` call is made to the *security-service* `/oauth/token` endpoint with a body:

```json
grant_type: authorization_code
client_id: <application client ID>
client_secret: <application client secret>
redirect_uri: <application URL that accepts the authorization code>
code: <received authorization code>
```



<a name="loio79aabdaea22a4846a7238231f8fbad77__section_uyc_xby_xrb"/>

## Client Authentication

Client authentication is used by \(headless\) extension archetype applications, when there is no human user to authenticate, or by workflow applications that serve unidentified \(anonymous\) users, for instance in B2C or B2B2C use cases. For example, job applicants can check out a list of job openings, or a business' customers can look up product information\).

To retrieve an access token that authenticates the client itself is simpler, and involves only one step: the client application makes a `POST` call to the `<security service>/oauth/token` endpoint with the following body information that is encoded as `x-www-form-urlencoded` \(for example, `Content-Type: application/x-www-form-urlencoded`\) :

```json
grant_type: client_credentials
client_id: <application client ID>
client_secret: <application client secret>
```

Either way, the retrieved access token must be sent to Graph in every communication, by adding the following header to each `HTTP` call:

```json
"Authorization": "Bearer <access token>"
```

Your application code can cache the access token, so it doesn't need to retrieve it every time, but it must be prepared to refresh it, when it expires.



<a name="loio79aabdaea22a4846a7238231f8fbad77__section_uft_rpm_jwb"/>

## Acquire Graph Service Credentials

The authentication code of the client applications must use the following parameters to obtain an access token and to connect to Graph:

-   The URL of the authentication service
-   Authentication credentials: `client id` and `client secret`
-   The Graph API URL

To acquire these parameters, the *Process Integration Runtime* service instance and service binding must be created. For more information, see [Enable Client Applications](enable-client-applications-e904119.md).

