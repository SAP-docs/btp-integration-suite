<!-- loiobf35cba2d5fb4ac7951f7ac41465af54 -->

# Connection Setup for Inbound Communication - Integration Flow Endpoints

When configuring secure inbound HTTP connections, different authentication options can be used for the sender authenticate itself against Cloud Integration.



<a name="loiobf35cba2d5fb4ac7951f7ac41465af54__section_zpj_1cf_fpb"/>

## Cloud Foundry Environment

The following table provides an overview of the available authentication options and a summary of the configuration steps in the Cloud Foundry environment \(for the connection to integration flow endpoints\). The table provides a brief summary to indicate the key aspects. Note that the most secure/recommended options are listed on top in the table.

Note that the following description doesn’t contain aspects that are common in both environments such like the role of the load balancer and the required security settings with regard to this component.


<table>
<tr>
<th valign="top">

Authentication Option



</th>
<th valign="top">

Configuration \(Summary\)



</th>
<th valign="top">

How it Works



</th>
</tr>
<tr>
<td valign="top">

Client certificate authentication



</td>
<td valign="top">

Go to SAP BTP cockpit and define a service key for the *Process Integration* service and *integration-flow* plan. When defining the service instance, specify the role that is to be used to grant access to the integration flow endpoint \(you can either use the predefined role `ESBMessaging.send` or a custom role\). When defining a service key for the service instance, enter the client certificate \(public key\) used by the sender to authenticate itself against Cloud Integration.

See:

-   [Client Certificate Authentication for Integration Flow Processing](../ConnectionSetup/client-certificate-authentication-for-integration-flow-processing-7f84d16.md)

-   [Cloud Integration on CF – How to Setup Secure HTTP Inbound Connection with Client Certificates](https://blogs.sap.com/2019/08/14/cloud-integration-on-cf-how-to-setup-secure-http-inbound-connection-with-client-certificates/)




</td>
<td valign="top">

System checks if a service key is available that contains the client certificate provided by the sender. If a service key is available, the system then checks if the associated service instance has a role specified that grants permissions to call the integration flow endpoint.



</td>
</tr>
<tr>
<td valign="top">

OAuth



</td>
<td valign="top">

Go to SAP BTP cockpit and define a service key for the *Process Integration* service and *integration-flow* plan. Specify the role that is to be used to grant access to the integration flow endpoint. The generated service key contains the following properties: `clientid`, `clientsecret`, and `tokenurl`.

See: [OAuth with Client Credentials Grant for Integration Flow Processing](../ConnectionSetup/oauth-with-client-credentials-grant-for-integration-flow-processing-6c052ce.md)



</td>
<td valign="top">

For the client credentials grant variant of OAuth, authentication at runtime comprises two HTTP requests:

1.  In a first request \(addressed to the token service addressed by the `tokenurl`\), the sender provides `clientid` and `clientsecret` and gets back from the token service an access token.

2.  In a second request \(addressed to the integration flow endpoint\), the sender provides the access token and gets access to the integration flow.


Other grant types can be configured as well using the service key information\).



</td>
</tr>
<tr>
<td valign="top">

Basic authentication \(associated with an OAuth client\)



</td>
<td valign="top">

Perform the same steps as for OAuth.

See: [Basic Authentication with clientId and clientsecret for Integration Flow Processing](../ConnectionSetup/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)



</td>
<td valign="top">

In just one request, the sender uses `clientid` and `clientsecret` as user credentials to directly access the integration flow endpoint without the need to request an access token first.



</td>
</tr>
<tr>
<td valign="top">

Basic authentication of a user registered at an identity provider \(IdP\) \(this option isn't considered to be secure enough for productive scenarios\)



</td>
<td valign="top">

Register a user at an identity provider \(for example, SAP's default identity provider SAP ID Service\). Using SAP BTP cockpit, you assign to the user a role that grants permission to call integration flow endpoints.

See: [Basic Authentication of IdP User for Integration Flow Processing](../ConnectionSetup/basic-authentication-of-idp-user-for-integration-flow-processing-5d46e56.md)



</td>
<td valign="top">

With username and password \(known to the identity provider\), the sender can call the integration flow endpoint.



</td>
</tr>
</table>

When defining a service key, the required role needs to be added in JSON representation. You can get the JSON representation of the role from the Cloud Integration *Monitor* section \(under *Manage Security* in the *User Roles* tile\).



<a name="loiobf35cba2d5fb4ac7951f7ac41465af54__section_lhs_hcf_fpb"/>

## Neo Environment

The following table provides an overview of the available authentication options and a summary of the configuration steps in the Neo environment \(for the connection to integration flow endpoints\). The table provides a brief summary to indicate the key aspects. Note that the most secure/recommended options are listed on top in the table.

Note that the following description doesn’t contain aspects that are common in both environments such like the role of the load balancer and the required security settings with regard to this component.


<table>
<tr>
<th valign="top">

Authentication Option



</th>
<th valign="top">

Configuration \(Summary\)



</th>
<th valign="top">

How it Works



</th>
</tr>
<tr>
<td valign="top">

Client certificate authentication with certificate-to-user mapping



</td>
<td valign="top">

Create and deploy a *Certificate-to-User Mapping* artifact on the Cloud Integration tenant. This artifact relates a user with a client certificate \(used by the sender to authenticate itself against Cloud Integration when calling an integration flow\). When defining the integration flow \(sender adapter\), for *Authorization* select *User Role* and specify role to be used to grant access to the integration flow endpoint.

Go to SAP BTP cockpit and assign to the user this role.

See:

-   [Setting Up Inbound HTTP Connections \(with Certificate-to-User Mapping\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-with-certificate-to-user-mapping-neo-environment-9949c61.md)

-   [Cloud Integration – How to Setup Secure HTTP Inbound Connection with Client Certificates](https://blogs.sap.com/2017/06/05/cloud-integration-how-to-setup-secure-http-inbound-connection-with-client-certificates/)




</td>
<td valign="top">

System checks if a *Certificate-to-User Mapping* artifact exists that fits to the client certificate provided by the sender. It checks if the associated user has the required permission to call the integration flow.



</td>
</tr>
<tr>
<td valign="top">

Client certificate authentication \(no certificate-to-user mapping\)

This option is secure but, compared to the usage of certificate-to-user mapping, not recommended. The reason: As the certificate is specified as part of the integration flow, each certificate change requires a redeployment of the integration flow. A downtime of the integration flow is the consequence.



</td>
<td valign="top">

When defining the integration flow \(sender adapter\), for *Authorization* select *Client Certificate* and provide the client certificate that is to be used by the sender when calling the integration flow endpoint.

See:

-   [Setting Up Inbound HTTP Connections \(with Client Certificate Authentication\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-with-client-certificate-authentication-neo-environmen-057f4a7.md)

-   [Cloud Integration – How to Setup Secure HTTP Inbound Connection with Client Certificates](https://blogs.sap.com/2017/06/05/cloud-integration-how-to-setup-secure-http-inbound-connection-with-client-certificates/)




</td>
<td valign="top">

System checks if client certificate provided by the sender is associated with integration flow endpoint.

Furthermore, system checks the permissions of the sender by evaluating the certificate's subject/issuer distinguished name.



</td>
</tr>
<tr>
<td valign="top">

OAuth



</td>
<td valign="top">

Go to SAP BTP cockpit and define an OAuth client. For *Authorization Grant*, select the option *Client Credentials*. On saving, a client ID and secret is generated. It's recommended to use the option to get a JSON Web Token \(JWT\) as access token.

Assign to user `oauth_client_<client ID>` a role that grants access to the integration flow \(`ESBMessaging.send` or a custom role\).

See:

-   [Setting Up Inbound HTTP Connections \(with OAuth\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-with-oauth-neo-environment-e5cb7ea.md)

-   [Cloud Integration – Inbound HTTP Connections using OAuth Client Credentials Grant](https://blogs.sap.com/2019/02/14/cloud-integration-inbound-http-connections-using-oauth-client-credentials-grant/)




</td>
<td valign="top">

For the client credentials grant variant of OAuth, authentication at runtime comprises two HTTP requests:

1.  In a first request \(addressed to the token service\), the sender provides ID and Secret from the OAuth client and gets back from the token service an access token. The URL of the token service can be found in the *Branding* tab of the OAuth client.

2.  In a second request \(addressed to the integration flow endpoint\), the sender provides the access token and gets access to the integration flow.


Other grant types can be configured as well.



</td>
</tr>
<tr>
<td valign="top">

Basic authentication of a user registered at an identity provider \(IdP\) \(this option isn't considered to be secure enough for productive scenarios\)



</td>
<td valign="top">

Register a user at an identity provider \(for example, SAP's default identity provider SAP ID Service\). Using SAP BTP cockpit, you assign to the user a role template that grants permission to call integration flow endpoints.

See: [Setting Up Inbound HTTP Connections \(with Basic Authentication\), Neo Environment](../ConnectionSetup/setting-up-inbound-http-connections-with-basic-authentication-neo-environment-391c45c.md)



</td>
<td valign="top">

With username and password \(known to the identity provider\), the sender can call the integration flow endpoint.



</td>
</tr>
</table>

