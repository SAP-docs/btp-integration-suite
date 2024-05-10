<!-- loio4a428fdc9498429b84e8000b9d240d47 -->

# Configuration Checklist for Inbound Authentication

The following tables provide a summary of the configuration settings for the available inbound authentication options.

> ### Note:  
> Most options are configured using SAP BTP service instances and service keys \(see [Creating Service Instance and Service Key for Inbound Authentication](creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md)\).
> 
> Those options based on users registered in an identity provider \(IdP\), don't require service instance/key configuration.

> ### Tip:  
> You can also use an application programming interface \(API\) to manage service instances and service keys. To learn more about how to use the API to retrieve information on the service instances and service keys configured for inbound communication, check out [Managing Service Instances and Service Keys Using an API](managing-service-instances-and-service-keys-using-an-api-6e5db60.md).

**Configuration Checklist \(Sender Calling Integration Flow Endpoint\)**


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

Authentication Option

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

Client certificate \(for senders calling integration flow\)

Using SAP certificate

See: [Client Certificate Authentication for Integration Flow Processing](client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

</td>
<td valign="top" rowspan="6">

*integration-flow* 

</td>
<td valign="top" rowspan="6">

Keep standard role `ESBMessaging.send` or use one or more custom roles.

</td>
<td valign="top" rowspan="6">

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

Client certificate \(for senders calling integration flow\)

Using own \(external\) certificate

See: [Client Certificate Authentication for Integration Flow Processing](client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

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
<tr>
<td valign="top">

OAuth client credentials grant \(for senders calling integration flow\)

Using clientId and clientsecret to authenticate against token server

See: [OAuth with Client Credentials Grant for Integration Flow Processing](oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

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

OAuth client credentials grant \(for senders calling integration flow\)

Using SAP certificate to authenticate against token server

See: [OAuth with Client Credentials Grant for Integration Flow Processing](oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

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

OAuth client credentials grant \(for senders calling integration flow\)

Using own certificate to authenticate against token server

See: [OAuth with Client Credentials Grant for Integration Flow Processing](oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)

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
<tr>
<td valign="top">

Basic authentication

With clientId and clientsecret

See: [Basic Authentication with clientId and clientsecret for Integration Flow Processing](basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)

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

Basic authentication

With IdP user

See: [Basic Authentication of IdP User for Integration Flow Processing](basic-authentication-of-idp-user-for-integration-flow-processing-5d46e56.md)

</td>
<td valign="top" colspan="7">

n.a.

</td>
</tr>
</table>

**Configuration Checklist \(API Client Calling OData API\)**


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

Authentication Option

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

Client certificate \(for API clients calling OData API\)

Using SAP certificate

See: [Client Certificate Authentication for API Clients](client-certificate-authentication-for-api-clients-d9ca0ac.md)

</td>
<td valign="top" rowspan="5">

*api* 

</td>
<td valign="top" rowspan="5">

Role as described at [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md) 

</td>
<td valign="top" rowspan="5">

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

Client certificate \(for API clients calling OData API\)

Using own \(external\) certificate

See: [Client Certificate Authentication for API Clients](client-certificate-authentication-for-api-clients-d9ca0ac.md)

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
<tr>
<td valign="top">

OAuth client credentials grant \(for API clients calling OData API\)

Using clientId and clientsecret to authenticate against token server

See: [OAuth with Client Credentials Grant for API Clients](oauth-with-client-credentials-grant-for-api-clients-20e26a8.md)

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

OAuth client credentials grant \(for API clients calling OData API\)

Using SAP certificate to authenticate against token server

See: [OAuth with Client Credentials Grant for API Clients](oauth-with-client-credentials-grant-for-api-clients-20e26a8.md)

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

OAuth client credentials grant \(for API clients calling OData API\)

Using own certificate to authenticate against token server

See: [OAuth with Client Credentials Grant for API Clients](oauth-with-client-credentials-grant-for-api-clients-20e26a8.md)

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
<tr>
<td valign="top">

Basic authentication \(for API clients calling OData API\)

With IdP user

See: [Basic Authentication of an IdP User for API Clients](basic-authentication-of-an-idp-user-for-api-clients-57f104d.md)

</td>
<td valign="top" colspan="7">

n.a.

</td>
</tr>
</table>

> ### Note:  
> **Note Related to Role Configuration**
> 
> Depending on the chosen inbound authorization option, you define permissions for sender systems to call integration flow endpoints in different ways:
> 
> ****
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Option
> 
> </th>
> <th valign="top">
> 
> Summary of Steps
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> Basic authentication of a user registered at an identity provider \(IdP\)
> 
> </td>
> <td valign="top">
> 
> Use SAP BTP cockpit to define a role collection that contains the predefined role template `MessagingSend` and assign the role collection to the IdP user \(under *Security* \> *Trust Configuration*\). The role template `MessagingSend` is provided by default in your subaccount to define permissions for sender systems to call integration flow endpoints for this use case.
> 
> See: [Basic Authentication of IdP User for Integration Flow Processing](basic-authentication-of-idp-user-for-integration-flow-processing-5d46e56.md)
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Authentication with an OAuth client \(service instance\)
> 
> </td>
> <td valign="top">
> 
> Use the Cloud Integration *Monitor* application and select the *User Roles* tile under *Manage Security*. When doing this, you can either use the predefined role `ESBMessaging.send` or create a custom role.
> 
> Create service instance and service key using SAP BTP cockpit. During this step, you need the role specified with the *User Roles* tile.
> 
> See:
> 
> -   [Client Certificate Authentication for Integration Flow Processing](client-certificate-authentication-for-integration-flow-processing-7f84d16.md)
> 
> -   [OAuth with Client Credentials Grant for Integration Flow Processing](oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)
> 
> -   [Basic Authentication with clientId and clientsecret for Integration Flow Processing](basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)
> 
> -   [Basic Authentication with clientId and clientsecret for Integration Flow Processing](basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)
> -   [Client Certificate Authentication for Integration Flow Processing](client-certificate-authentication-for-integration-flow-processing-7f84d16.md)
> -   [OAuth with Client Credentials Grant for Integration Flow Processing](oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)
> 
> 
> 
> </td>
> </tr>
> </table>

