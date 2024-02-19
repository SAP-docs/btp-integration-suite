<!-- loio20e26a837a8449c4b8b934b07f71cb76 -->

# OAuth with Client Credentials Grant for API Clients

The API is protected by OAuth and role-based authorization.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Cloud Foundry environment.



> ### Note:  
> This option is a recommended and secure way to set up HTTP inbound connections.

Simply spoken, this authentication is established using the following sequent steps:

1.  The API client authenticates itself at token server.

    There are 2 options to authenticate against the token server:

    -   Using clientId and clientsecret from the service key

    -   Using a client certificate from the service key

        If you use a client certificate, you can either use an own \("external"\) certificate or one generated by SAP.


2.  Token server issues access token.

3.  API client authenticates itself with access token when calling the OData API.


For more information, check out: [OAuth Authentication with Client Credentials Grant \(Inbound\), Cloud Foundry Environment](oauth-authentication-with-client-credentials-grant-inbound-cloud-foundry-environment-b9df724.md) \(explains the concepts and how this authentication option works\).

To set up this authorization option, perform the following steps.



1.  Look up the role to be used to authorize the API client to access the related Cloud Integration resource using the API.

    See: [Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md)

2.  In SAP BTP cockpit, select the subaccount that hosts your SAP Cloud Integration virtual environment and create a service instance and service key.

    Proceed as described under [Creating Service Instance and Service Key for Inbound Authentication](creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md).

    For this use case, specify the service instance and service key parameters as follows:

    ****


    <table>
    <tr>
    <th valign="top">

     
    
    </th>
    <th valign="top" colspan="3">

    Service Instance
    
    </th>
    <th valign="top" colspan="4">

    Service Key
    
    </th>
    </tr>
    <tr>
    <th valign="top">

    Option \(Authentication At Token Server\)
    
    </th>
    <th valign="top">

    Plan
    
    </th>
    <th valign="top">

    Roles
    
    </th>
    <th valign="top">

    Grant-types
    
    </th>
    <th valign="top">

    Key Type
    
    </th>
    <th valign="top">

    External Certificate
    
    </th>
    <th valign="top">

    Validity
    
    </th>
    <th valign="top">

    Key Size
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    ClientId and clientsecret
    
    </td>
    <td valign="top">
    
    *api* 
    
    </td>
    <td valign="top">
    
    Select role according to the API resource to access.

    See: [Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md)
    
    </td>
    <td valign="top">
    
    *Client Credentials* 
    
    </td>
    <td valign="top">
    
    *ClientId/Secret* 
    
    </td>
    <td valign="top">
    
    n.a.
    
    </td>
    <td valign="top">
    
    n.a.
    
    </td>
    <td valign="top">
    
    n.a.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP certificate
    
    </td>
    <td valign="top">
    
    *api* 
    
    </td>
    <td valign="top">
    
    Select role according to the API resource to access.

    See: [Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md)
    
    </td>
    <td valign="top">
    
    *Client Credentials* 
    
    </td>
    <td valign="top">
    
    *Certificate* 
    
    </td>
    <td valign="top">
    
    n.a.
    
    </td>
    <td valign="top">
    
    Specify validity in days.
    
    </td>
    <td valign="top">
    
    Specify key size.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    External certificate
    
    </td>
    <td valign="top">
    
    *api* 
    
    </td>
    <td valign="top">
    
    Select role according to the API resource to access.

    See: [Tasks and Permissions](../SecurityNeo/tasks-and-permissions-556d557.md)
    
    </td>
    <td valign="top">
    
    *Client Credentials* 
    
    </td>
    <td valign="top">
    
    *External Certificate* 
    
    </td>
    <td valign="top">
    
    Add PEM-encoded X.509 certificate.
    
    </td>
    <td valign="top">
    
    n.a.
    
    </td>
    <td valign="top">
    
    n.a.
    
    </td>
    </tr>
    </table>
    

When you've accomplished the configuration steps, you've generated a service key that contains the following information:

-   When using clientId and clientsecret to call token server:

    Service key contains OAuth client credentials \(`clientid` and `clientsecret`\) and the URL of the OAuth authorization service \(`tokenurl`\).

-   When using a client certificate to call token server:

    Service key contains a client certificate \(PEM-encoded\) and the URL of the OAuth authorization service \(`tokenurl`\).


To set up a sequence of requests for an OAuth workflow with the client credentials grant, you need to do the following.

> ### Note:  
> For the following instructions, we assume that you're using an HTTP client \(for example, Postman\) to call the integration flow endpoint.
> 
> 1.  Call the authorization service to get the access token for the integration flow endpoint:
> 
>     In your HTTP client \(calling the integration flow\), set up a POST request with the following parameters:
> 
>     As server address, use the following URL:
> 
>     `<tokenurl from service key>?grant_type=client_credentials`
> 
>     -   When using clientId and clientsecret to call token server:
> 
>         Choose the appropriate authentication option and make sure to pass on with the request the values of `clientid` and `clientsecret` \(from the service key\).
> 
>     -   When using a client certificate to call token server:
> 
>         Choose the appropriate authentication option and make sure to pass on with the request the client certificate.
> 
>         With the request, the API client has to pass on a certificate chain that contains a root certificate supported by the load balancer \(see [Load Balancer Root Certificates Supported by SAP](load-balancer-root-certificates-supported-by-sap-4509f60.md)\). Otherwise, the load balancer doesn't pass on the client certificate to SAP Cloud Integration.
> 
>         -   When you use an SAP-generated client certificate \(with *Key Type* set to *Certificate*\), the service key contains a certificate chain and a private key \(see [Creating Service Instance and Service Key for Inbound Authentication](creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md)\). The certificate chain contains already a root certificate supported by the load balancer.
> 
>             You can use these values to configure the request.
> 
>             > ### Note:  
>             > To enable the related HTTP client to support this authentication option, you need to format the certificate \(including the certificate chain\) and the key accordingly. In particular, make sure to replace all `\n` in the SAP-generated certificate or key by line breaks.
>             > 
>             > A suitable certificate, for example, would then look like:
>             > 
>             > ```
>             > -----BEGIN CERTIFICATE-----
>             > MIIFtDCCA5ygAwIBAgIQCUFIj6cfjiSfZi/ZvVU6IDANBgkqhkiG9w0BAQsFADB5
>             > ................................................................
>             > ................................................................
>             > ................................................................+
>             > LvHPhNDM3rMsLu06agF4JTbO8ANYtWQTx0PVrZKJu+8fcIaUp7MVBIVZ
>             > -----END CERTIFICATE-----
>             > ```
> 
>         -   When you use an external certificate \(with *Key Type* set to *External Certificate*\), the service key displays only the public key certificate provided by you \(see [Creating Service Instance and Service Key for Inbound Authentication](creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md)\). To configure the request, use the key pair exported from the application used to generate the client certificate.
> 
> 
> 
>     The response contains the access token.
> 
> 2.  Call the OData API:
> 
>     For the address of the call, enter the address of the OData API resource and the query options \(see [HTTP Calls and URI Components](../Development/http-calls-and-uri-components-ca75e12.md)\).
> 
>     See: [OData API](../Development/odata-api-a617d6f.md)
> 
>     Choose the appropriate authentication option and make sure to pass on with the request the access token that you retrieved as a response from the first HTTP call.
