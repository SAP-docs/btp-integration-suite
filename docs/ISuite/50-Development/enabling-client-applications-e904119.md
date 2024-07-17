<!-- loioe904119a0910462baa8e2b58e9e48c57 -->

# Enabling Client Applications

Before a client application can access a Graph business data graph, the client application must know certain secrets, known as Graph service credentials \(Graph root URL, security service URL, client ID, and client secret\), as well as the business data graph identifier.

This is satisfied by creating a Graph service instance. This consists of two steps:

1.  Create the Graph instance, and explicitly list a redirect-URL for each trusted client application that intends to perform user authentication. These URLs must be provided by the developers of the client applications and are specified within a JSON structure as follows:

    ```
    {
        "oauth2-configuration": {
           "redirect-uris": [ https://my.client-application.net/callback ]  
        }
    }
    ```

    Each redirect URL must reference the callback handler in the corresponding client application that accepts the OAuth 2.0 authorization code when authenticating a user \("\*" wildcards are also supported\). If you do not specify any `redirect-uris`, SAP BTP automatically allows \(trusts\) the default URL of `localhost/*` \(that is, any sub-path for any application running on a developer's local machine\). You should only allow `localhost` in non-productive development landscapes. Client applications that only use client authentication do not need to be listed in the `oauth2-configuration`.

    > ### Note:  
    > The service instance must be updated in the future if the location of the user-authenticating client application, or just a callback path inside the application, has changed. In such a case, the same structure must be passed, but with the modified `redirect-uris` value.

2.  Create a binding to the Graph instance. This operation results in a service descriptor \(aka service key or application binding\) of service credentials \(client ID, client secret, authorization service endpoint, and Graph endpoint\). These credentials are then used by the authentication code of the client applications.

    For more information, see *Create and Download a Service Binding* in [Enable Client Applications](enable-client-applications-09d7783.md).

    > ### Note:  
    > The list of allowed `redirect-uris` may be changed at a later point in time by updating the Graph instance. For more information, see *Create a Graph Service Instance* in [Enable Client Applications](enable-client-applications-09d7783.md).


Sharing service bindings enables any client application to consume Graph APIs. From a security perspective, create a dedicated service instance per client application. This helps tracking, auditing, and if necessary, revoking the credentials of a client application, without affecting others.

