<!-- loio37c919d8d0174822b6ff046732ad4367 -->

# Deploying an OAuth2 Password Credentials

Deploy an OAuth2 Password Credentials to securely connect to systems that use OAuth 2.0 password grant authentication. The deployed credentials can then be referenced by integration adapters to obtain and reuse access tokens.



## Context

You can edit and deploy an OAuth2 Password Credentials artifact.

> ### Note:  
> Set the token expiry to at least 10 minutes. Otherwise, since the token is refreshed 5 minutes before its expiry, it can create a continuous refresh loop and trigger rate limits from the token server.

> ### Note:  
> -   The adapter using the OAuth 2 Password Credentials accesses the OAuth token and caches it against the name of the credential. The adapter uses the same token until it expires. Also, if you use the same credential in another adapter simultaneously, the token is reused.
> 
> -   Every time you edit an OAuth2 Password Credentials artifact, you must re-enter the *Client Secret*. This option is available when *Enable Client Authentication* checkbox is selected.

> ### Note:  
> Read [SAP Cloud Integration – Principal Propagation with SuccessFactors OData V2](https://blogs.sap.com/2018/07/30/sap-cloud-platform-integration-principal-propagation-with-successfactors-odata-v2/), to design and deploy an integration flow that talks to SuccessFactors OData V2 endpoint with OAuth2 authentication.

For more information about OAuth, see [https://tools.ietf.org/html/rfc6749](https://tools.ietf.org/html/rfc6749)



### **How OAuth2 Authentication Works**

When an integration flow runs, Cloud Integration sends the Client ID and Client Secret to the authorization server of the target system. Once validated, an access token is issued from this server. Cloud Integration then uses this token to access the target system's resources for the duration of the token's validity.

> ### Note:  
> The Client ID and Secret is issued by the target system's authorization server when Cloud Integration is registered as a client application.



## Procedure

1.  Choose *Monitor* \> *Integrations and APIs*.

2.  Select the target runtime \(*Runtime* parameter\).

    > ### Note:  
    > This information is only relevant for Edge Integration Cell runtime.
    > 
    > For more information on how to manage security artifacts for Edge Integration Cell, see [Manage Security for Edge Integration Cell](https://help.sap.com/viewer/caeaa5e76f8c486ebea167938fa1f40b/CLOUD/en-US/1783cf87caa2449e96082f0cf754449d.html "The manage security section allows you to manage various kinds of security-related artifacts according to the runtime deployment possibilities.") :arrow_upper_right:.

3.  Click the *Security Material* tile in the *Manage Security* section.

4.  Choose *Create* \> *OAuth2 Password Credentials*.

5.  Specify the following attributes:


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
    
    Grant Type
    
    </td>
    <td valign="top">
    
    Allows you to use grant type as one of the following.

    -   *Send as part of URL*: This includes grant type as part of the URL and is set by default for credentials that are already deployed or existing.

    -   *Send as part of body*: This includes grant type in the request body sent to the token authentication server.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Username
    
    </td>
    <td valign="top">
    
    Enter the username required to authenticate with the authorization server.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Password
    
    </td>
    <td valign="top">
    
    Enter the password required to authenticate with the authorization server.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Client Authentication
    
    </td>
    <td valign="top">
    
    Select this checkbox to enable client authentication. When selected, you can specify the client ID, client secret and client authentication method.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client ID

    \(Available only if *Enable Client Authentication* checkbox is selected\)
    
    </td>
    <td valign="top">
    
    Unique identifier assigned to the application \(Cloud Integration\) by the target system's authorization server. It identifies Cloud Integration as the registered client application and must always be used together with the Client Secret for authentication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Secret

    \(Available only if *Enable Client Authentication* checkbox is selected\)
    
    </td>
    <td valign="top">
    
    Confidential credential assigned to your application \(Cloud Integration\) by the target system's authorization server. It is used together with the Client ID to authenticate Cloud Integration before an access token is issued from the server.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Authentication

    \(Available only if *Enable Client Authentication* checkbox is selected\)
    
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
    
    **Custom Parameter**

    Add or delete additional parameters in the custom parameter table, which includes three columns: *Key*, *Value*, and *Send as Part of*.

    Each custom parameter can be sent in the request body, request header, or request URL, depending on specific requirements.

    > ### Note:  
    > -   Duplicate combinations of *Key*, *Value*, and *Send as Part of* fields are not allowed.
    > 
    > -   The *Key* cannot be "client\_id," "client\_secret," or "grant\_type".
    > 
    > -   Fields cannot be empty or consist only of whitespace.
    > 
    > -   The maximum length of the fields can be 1024 characters.
    > 
    > -   You can add a maximum of 20 key-value pairs.

6.  Choose *Deploy*.


