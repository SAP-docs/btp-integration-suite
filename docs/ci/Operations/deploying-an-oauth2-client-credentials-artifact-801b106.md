<!-- loio801b106885b14d2788223956ce9786e5 -->

# Deploying an OAuth2 Client Credentials Artifact

Many web servers use OAuth 2.0 for authorization purposes. If you want to connect to a system that uses OAuth 2.0 authentication, you need to deploy an OAuth2 Credentials artifact using the following procedure.



## Context

You can edit and deploy an OAuth2 Client Credentials artifact.

> ### Note:  
> -   The adapter using the OAuth 2 Client Credentials accesses the OAuth token and caches it against the name of the credential. The adapter uses the same token until it expires. Also, if you use the same credential in another adapter simultaneously, the token is reused.
> 
> -   Every time you edit an OAuth2 Client Credentials artifact, you must re-enter the Client Secret.

More information on OAuth: [https://tools.ietf.org/html/rfc6749](https://tools.ietf.org/html/rfc6749)



## Procedure

1.  Choose *Monitor*.

2.  Choose the tile *Security Material*.

3.  Choose *Create* \> *OAuth2 Client Credentials*.

4.  Specify the following attributes:


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Name for the credentials. This name is also called as "alias" when using in an adapter.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Grant Type
    
    </td>
    <td valign="top">
    
    The relevant type of grant for authorizing the client to interact with the server. By default, the value is *Client Credentials* which you can't change.

    > ### Note:  
    > Read [SAP Cloud Integration – Principal Propagation with SuccessFactors OData V2](https://blogs.sap.com/2018/07/30/sap-cloud-platform-integration-principal-propagation-with-successfactors-odata-v2/), to design and deploy an integration flow that talks to SuccessFactors OData V2 endpoint with OAuth2 authentication.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Description for the credentials.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    URL of the OAuth2 authorization server that issues the access token.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client ID
    
    </td>
    <td valign="top">
    
    ID of the client that you're connecting to.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Secret
    
    </td>
    <td valign="top">
    
    Secret key of the client that you're connecting to.

    OAuth2 uses a multiple step authentication pattern: Client credentials \(*Client ID* and *Client Secret*, as specified in the artifact\) are used by the client application to initially request an access token. The access token is then used to authorize the client \(for as long as the token is valid\) to access the server’s resources \(for example, the resources that are used in the associated integration flow\). In many OAuth2 scenarios, the access token is issued \(or generated\) by an authorization server.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Authentication
    
    </td>
    <td valign="top">
    
    Allows you to access an application using *Client ID* and *Client Secret*.

    By default the *Send as Body Parameter* is selected, this option sends the *Client ID* and *Client Secret* as a JSON content to the authentication server in the request body.

    If you select the *Send as Request Header* option, then the *Client ID* and *Client Secret* are encoded, and send to the server as an *Authorization* header.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Scope
    
    </td>
    <td valign="top">
    
    Provide the OAuth2 scope information to be included in the request body.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Content Type
    
    </td>
    <td valign="top">
    
    Request content type to indicate the media type.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Resource
    
    </td>
    <td valign="top">
    
    Enter the identifier of the application or service that shares the same client secret. The identifier varies depending on the service that you want to connect with.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Audience
    
    </td>
    <td valign="top">
    
    Enter the identifier of the application or service that shares the same client secret. The identifier varies depending on the service that you want to connect with.
    
    </td>
    </tr>
    </table>
    
5.  Choose *Deploy*.


**Related Information**  


[Managing Security Material](managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

