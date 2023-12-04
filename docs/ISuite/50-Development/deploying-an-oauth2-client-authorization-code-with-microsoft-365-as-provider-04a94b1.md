<!-- loio04a94b18dac143c8af64708252f26c04 -->

# Deploying an OAuth2 Client Authorization Code with Microsoft 365 as Provider



<a name="loio04a94b18dac143c8af64708252f26c04__context_axq_4s2_kmb"/>

## Context

You can edit and deploy an OAuth2 Authorization Code. See also: [OAuth 2.0](../40-RemoteSystems/oauth-2-0-3823134.md#loio382313443b8d4453b0fd536b82b9e15d) and for more information on OAuth: [https://tools.ietf.org/html/rfc6749](https://tools.ietf.org/html/rfc6749).

> ### Note:  
> Refer to [Deploying an OAuth2 Client Authorization Code with Generic Provider](deploying-an-oauth2-client-authorization-code-with-generic-provider-72c8fa7.md), if you want to use other providers than “Microsoft 365”.



<a name="loio04a94b18dac143c8af64708252f26c04__steps_cnq_ss2_kmb"/>

## Procedure

1.  Choose *Monitor* \> *Integrations and APIs*.

2.  Select the target runtime \(*Runtime* parameter\).

    This information is only relevant for Edge Integration Cell runtime.

    For more information on how to manage security artifacts for Edge Integration Cell, see [Manage Security for Edge Integration Cell](../manage-security-for-edge-integration-cell-1783cf8.md).

3.  Click the *Security Material* tile in the *Manage Security* section.

4.  Choose *Add*.

5.  As *Type*, select *OAuth2 Authorization Code*.

6.  Specify the following attributes:

    ****


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
    
    Name of the artifact that you want to deploy on the tenant.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Description of the artifact you are deploying on the tenant.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Provider
    
    </td>
    <td valign="top">
    
    Enter the name of the provider of the platform on which you created the OAuth2 client.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authorization URL
    
    </td>
    <td valign="top">
    
    Provide the Authorization URL for authorizing the OAuth client to access resources of a user.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    Provide the URL that generates the OAuth2 access and refresh token for the registered OAuth2 client and the provided user.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Refresh Token Expiry
    
    </td>
    <td valign="top">
    
    Provide an amount of time after which the refresh token expires.

    The maximum is set to 90 days and the minimum is set to 3 days. The SAP Cloud Integration system will update the refresh token before the expiration.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Redirect URL
    
    </td>
    <td valign="top">
    
    Displays the URL you need, when creating the OAuth Clients/App im OAuth Authorization Server/Token Server. For more information, see [OAuth2.0 Authorization Code Grant](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/oauth-2-0#loio508a70db7eac4addbb6ac69a06d46e79) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client ID
    
    </td>
    <td valign="top">
    
    ID of the client you want to connect to.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Secret
    
    </td>
    <td valign="top">
    
    Secret key of the client that you are connecting to.

    See: [OAuth 2.0](../40-RemoteSystems/oauth-2-0-3823134.md#loio382313443b8d4453b0fd536b82b9e15d).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Send As
    
    </td>
    <td valign="top">
    
    -   Body Parameter: Send the Client ID and Client Secret in the request body when calling the Authorization URL or Token Service URL.

    -   Basic Auth Header: Send the Client ID and Client Secret via Basic Authorization when calling the Authorization URL or Token Service URL.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User Name
    
    </td>
    <td valign="top">
    
    Name of the user whose resources the OAuth2 client gets access to.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Scope
    
    </td>
    <td valign="top">
    
    OAuth2 scopes protecting the access to the resources.

    > ### Note:  
    > *Configure Mail Sender and Receiver Adapter*:
    > 
    > -   The scope https://outlook.office.com/SMTP.Send is necessary for sending e-mails from Outlook 365.
    > 
    > -   The scope https://outlook.office.com/IMAP.AccessAsUser.All is necessary for reading e-mails from Outlook 365.
    > 
    > -   You can also request an [offline\_acccess scope](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent#offline_access). When a user approves the offline\_access scope, your app can receive refresh tokens from the Microsoft identity platform token endpoint.
    > 
    >     If the offline\_access scope is not provided, SAP Integration Suite is adding this scope automatically to the credential since needs the refresh token to create access tokens.
    > 
    > -   If you add more than one scope, you need to separate your scopes by a blank space.


    
    </td>
    </tr>
    </table>
    
7.  Choose *Deploy*.


**Related Information**  


[Managing Security Material](managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

[Deploying an OAuth2 Client Authorization Code with Generic Provider](deploying-an-oauth2-client-authorization-code-with-generic-provider-72c8fa7.md "Create an OAuth2 Client Authorization Code with the Generic Provider.")

[OAuth 2.0](../40-RemoteSystems/oauth-2-0-3823134.md#loio382313443b8d4453b0fd536b82b9e15d "OAuth 2.0 allows a user to grant a client access to a protected resource (hosted by a resource server). The user typically restricts the access of the client and doesn't allow full access.")

