<!-- loio0e3d3e77583f4cde8a80c31a3e584f0d -->

# Principal Propagation from the Same Cloud Foundry Subaccount

Transfer the principal \(user details\) within the same Cloud Foundry subaccount by exchanging tokens.

**Prerequisites**

-   You have created a *Service Key* by creating a service instance using the on-premise connectivity plan. For more details, see [Accessing On-Premise Systems through API Management](../accessing-on-premise-systems-through-api-management-2fc7a5b.md).

**Context**

When an application has to communicate with another application in the same subaccount on Cloud Foundry, exchange of token has to take place for secure passage of user details. To make this step easier, you can use the OAuth2UserTokenExchange authentication type, where the Destination service performs all these steps automatically and lets you simplify your application development. Therefore, the JWT user token in your application can be exchanged with the API Management token using the *Service Key* or client credentials by using OAuth2UserTokenExchange. For more details on OAuth2UserExchange destination, see [here](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e3c333f9de6245fca326993f2397c13a.html)

**Procedure**

1.  Create a Destination to the API Proxy that you want to call using principal propagation. Enter the following details while configuring a destination of type OAuth2UserTokenExchange. Also, if you have not generated the client credentials \(clientId, ClientSecret, tokenUrl and application url\) yet, see [Accessing On-Premise Systems through API Management](../accessing-on-premise-systems-through-api-management-2fc7a5b.md).

    > ### Sample Code:  
    > ```
    > Example:
    > 
    > Type=HTTP
    > clientId=Client id from the credentials
    > Authentication=OAuth2UserTokenExchange
    > Name= Name of the destination
    > tokenServiceURL= Token url from the credentials
    > ProxyType=Internet
    > URL=API Proxy URL for the proxy to be called
    > tokenServiceURLType=Dedicated
    > clientSecret=<Client Secret from the credentials>
    > ```

2.  Exchange the JWT user token in the application with the *API Management, API, portal* application via `OAuthUserTokenExchange` authentication type for HTTP destinations. For more detailed information, see [here](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/39d42654093e4f8db20398a06f7eab2b.html).

**Next Step**:

Use the token received from the `OAuthUserTokenExchange` to call an API Proxy and consume the above -created destination from your application.

