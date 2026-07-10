<!-- loio6224cf2497684bb5829333726192a029 -->

# Security Specification for API Artifact

When an API artifact is created and published, it includes built-in authentication mechanisms that enable application developers to securely access and test the APIs. These authentication details are defined in the API specification, ensuring API consumers know how to authorize themselves with the required credentials.

By default, an OpenAPI Specification is generated during the creation of an API artifact, along with an automatically added authentication policy in the policy modeler. This configuration is reflected in the API specification—under the `securitySchemes` section for OpenAPI 3.0, and under `securityDefinitions` for version 2.0.

The API artifact supports three types of authentication mechanisms:

-   OAuth: The tenant authenticates itself using a client ID and client secret.

-   Client Certificate: The tenant authenticates itself against the using a client certificate.

-   Basic: The tenant authenticates itself using user credentials \(user name and password\).


Among these, *OAuth* and *Client Certificate* are selected by default in the authentication policy.

> ### Note:  
> For the OAuth 2.0 authentication type:
> 
> -   Changes made to the description field in the `securitySchemes` are preserved during deployment.
> -   However, if you modify the defined grant types—such as `authorizationCode, clientCredentials, password, x-refresh_token, x-saml2-bearer, x-jwt-bearer`—these will be overwritten and reset to the default configuration.
> 
> Additionally, scopes defined in the authorization policy, if added, will not be appended to the `securitySchemes` or `securityDefinitions` section of the OpenAPI specification 3.0 or 2.0.

Here’s a sample of how the security section is defined in an OpenAPI 3.0 specification:

> ### Sample Code:  
> ```
> openapi: 3.0.1
> info:
>   title: skbdqv
>   description: <p>This is skbdqv API.</p>
>   x-apiProvider: PO_T28_ESR
>   x-relativeUrl: /bcdwkj
>   version: '1'
> servers:
>   - url: 'https://null/jhdw'
> paths: {}
> components:
>   securitySchemes:
>     OAuth2:
>       type: oauth2
>       description: Testing OAUTH2
>       flows:
>         password:
>           tokenUrl: 'https://local_tenant.example.com/oauth/token'
>           scopes: {}
>         clientCredentials:
>           tokenUrl: 'https://local_tenant.example.com/oauth/token'
>           scopes: {}
>         authorizationCode:
>           authorizationUrl: 'https://local_tenant.example.com/oauth/authorize'
>           tokenUrl: 'https://local_tenant.example.com/oauth/token'
>           scopes: {}
>         x-refresh_token                           # Extension flows
>           tokenUrl: 'https://local_tenant.example.com/oauth/token'
>           refreshUrl: 'https://local_tenant.example.com/oauth/token'
>         x-saml2-bearer:
>           tokenUrl: 'https://local_tenant.example.com/oauth/token'
>         x-jwt-bearer:
>           tokenUrl: 'https://local_tenant.example.com/oauth/token'
>     clientCertAuth:
>       type: http
>       description: Client certificate support via mutualTLS.
>       scheme: mutualTLS
> security:
>   - clientCertAuth: []
>   - OAuth2: []
> ```

Here’s a sample of how the security section is defined in an OpenAPI 2.0 specification:

> ### Sample Code:  
> ```
> swagger: '2.0'
> info:
>   title: Demo
>   description: |
>     <p>This is Demo API.</p>
>   version: '1'
> host: undefined
> basePath: /bdsan
> schemes:
>   - https
> paths: {}
> securityDefinitions:
>   authorizationCode:
>     type: oauth2
>     flow: accessCode
>     authorizationUrl: https://local_tenant.test.com/oauth/authorize
>     tokenUrl: https://local_tenant.test.com/oauth/token
>    clientCredentials:
>     type: oauth2
>     flow: application
>     tokenUrl: https://local_tenant.test.com/oauth/token
>   password:
>     type: oauth2
>     flow: password
>     tokenUrl: https://local_tenant.test.com/oauth/token
>   x-refresh-token:
>     type: oauth2
>     flow: application
>     tokenUrl: https://local_tenant.test.com/oauth/token
>     description: wew
>   x-saml2-bearer:
>     type: oauth2
>     flow: application
>     tokenUrl: https://local_tenant.test.com/oauth/token
>     description: wew
>   x-jwt-bearer:
>     type: oauth2
>     flow: application
>     tokenUrl: https://local_tenant.test.com/oauth/token
>     description: wew
>   clientCertAuth:
>     type: apiKey
>     in: header
>     name: mutualTLS
>     description: >
>       Simulates client certificate (mutual TLS) authentication.
>       Swagger 2.0 doesn't support mutual TLS directly.
>       Use this definition to document that a client certificate is required,
>       even though actual enforcement is at the transport layer.
>   basicAuth:
>     type: basic
>     description: >
>       Basic Authentication using username and password via Authorization header.
> security:
>   - clientCertAuth: []
>   - basicAuth: []
>   - authorizationCode: []
>    clientCredentials: []
>    password: []
>    x-refresh-token: []
>    x-saml2-bearer: []
>    x-jwt-bearer: []
> 
> ```

