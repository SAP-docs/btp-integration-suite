<!-- loio040d8110293d44b1bfaa75674530d395 -->

# Setting Up OAuth Inbound Authentication with Client Credentials Grant for API Clients

The API is protected by basic authentication and OAuth.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.



:

1.  Register the client application as the OAuth client in the consumer account using the SAP Cloud Integration SAP BTP cockpit \(in the *Security*** \> *OAuth* section, go to the *Clients* tab\).

    Also specify a subscription in order to restrict the authorizations associated with the access token on the particular runtime node.

    Perform this step as described under [Register an OAuth Client](https://help.sap.com/docs/btp/sap-btp-neo-environment/register-oauth-client).

    To enable this security setting for the above-mentioned scenario \(client application sending messages to the cloud-based integration platform\), specify the following information when registering the OAuth client:

    -   As *Subscription*, select the application of the tenant management node \(that ends with the node type `….tmn`\).

        You can only register applications for node type `tmn`.

    -   Enter a client ID.

        You can either get a client ID from the client or you can choose one \(you then have to forward this ID to the client\).

    -   As *Authorization Grant*, choose *Client Credentials*.

    -   Enter a secret \(as assigned to the client application\).

    -   Specify a *Token Lifetime* to increase the security level.


2.  Assign the user with name `oauth_client_<client ID>` to the respective role in the subscription of the consumer account \(for the `tmn` node\).

    To do this, select the *Security Authorizations* section.

    Perform this step as described under [Defining Authorizations for Integration Team Members](../Operations/defining-authorizations-for-integration-team-members-3ec7679.md).

3.  On the client side, perform the following steps:

    1.  Perform a POST HTTPS call to`https://oauthasservices-<consumer-account>.<landscape host name>/oauth2/api/v1/token?grant_type=client_credentials`.

        For the URL part `https://oauthasservices-<consumer-account>.<landscape host name>/oauth2/api/v1/token`, you can find the value that you need to enter in the receiver account, SAP BTP cockpit, under *Security* \> *OAuth*. On the *Branding* tab in section *OAuth URLs*, the URL is displayed under *Token Endpoint*.

        Use basic authentication where the client ID is the user and the secret is the password. This call returns the access token.

        Example: **Fetch OAuth-token request**:

        > ### Sample Code:  
        > ```
        > POST /oauth2/api/v1/token?grant_type=client_credentials HTTP/1.1 
        > Host: oauthasservices-<consumer account>.<landscape host name>
        > Authorization: Basic xxxxxxxxxxxx 
        > Accept: */* 
        > 
        > ```

        **Response**:

        > ### Sample Code:  
        > ```
        > { 
        > "access_token": "8271a067126f0aa93b46c2fe07c6880", 
        > "token_type": "Bearer", 
        > "expires_in": 0, 
        > "scopes": [] 
        > }
        > ```

    2.  **GET request for MPL OData API**\(use the token from above\):

        > ### Sample Code:  
        > ```
        > GET /api/v1/MessageProcessingLogs HTTP/1.1
        > Host: <subaccount>-tmn.<landscape host name>
        > Authorization: Bearer 8271a067126f0aa93b46c2fe07c6880
        > Accept: text/xml
        > 
        > ```

        Perform an HTTPS call to the endpoint URI with the HTTP header with name `“Authorization”` and value `“Bearer <access token>”`.

        > ### Note:  
        > For modifying calls in the Neo environment, a CSRF-Token is required in the same way as for basic authentication.

        See: [HTTP Calls and URI Components](../Development/http-calls-and-uri-components-ca75e12.md)



