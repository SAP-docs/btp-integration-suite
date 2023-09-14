<!-- loio778c7e7835ff46408aafe0d499720dc7 -->

# Setting Up Inbound HTTP Connections \(Integration Flow Processing\), Neo Environment

You can use various sender adapters \(for example, the SOAP adapters, the IDoc adapter, and the HTTP adapter\) to connect the tenant to a sender system so that the sender can send messages to Cloud Integration over the HTTP protocol.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.



The following figure illustrates the basic setup for HTTP inbound communication:

![](images/SAP_HCI_Onboarding_Intro_Inbound_Communication_923bac7.png)

To configure inbound HTTP connections, you need a specific setup in which a load balancer component is interconnected for inbound calls between the remote sender system and the Cloud Integration tenant.

The load balancer terminates each inbound TLS \(Transport Layer Security\) request and re-establishes a new one for the connection to the tenant where the message will be processed.

For inbound HTTP connections, you can define *Authorization* options for the communication user associated with the sender system to define how it accesses the Cloud Integration components. Depending on the chosen *Authorization* option, you can configure how the sender system should be **authenticated** against the Cloud Integration system \(as indicated in the table\).

For more information, see [Authentication and Authorization Options \(Inbound\)](authentication-and-authorization-options-inbound-983f2a5.md).

The following table lists the options for setting up secure connections for the different protocols. Consider the following table as a connection setup checklist. For a detailed description of the available properties for integration flow design, see the documentation of the individual adapters and integration flow steps.

> ### Note:  
> When setting up inbound HTTP connections, there are certain steps that depend on the environment in which you run Cloud Integration. Check out the specific, environment-specific topics to find out more.

> ### Note:  
> If an SAP system based on Application Server ABAP sends requests to Cloud Integration and there are 2 or more worker nodes enabled on Cloud Integration side, you can receive an `HTTP/1.1 403` authentication error. The root cause is that the SAP kernel encodes the cookies' value by default, which breaks the load-balancing feature. To solve the issue, set profile parameter `ict/disable_cookie_urlencoding` to `1` or `2` depending on kernel level. For more information, see SAP note [2681175](https://me.sap.com/notes/2681175).

****


<table>
<tr>
<th valign="top">

Authorization



</th>
<th valign="top">

Authentication



</th>
<th valign="top">

Description



</th>
<th valign="top">

How to configure \(checklist\) ...



</th>
</tr>
<tr>
<td valign="top">

User role



</td>
<td valign="top">

Client-Certificate with certificate-to-user mapping



</td>
<td valign="top">

Load balancer authenticates sender based on a client certificate and, if the check is successful, forwards the certificate's issuer and subject DNs to the tenant in the message header. Tenant evaluates if a certificate-to-user mapping is defined \(for the certificate\) and, if so, checks whether the user \(derived from the certificate-to-user mapping\) is authorized to process the integration flow on the tenant. This step is performed based on user-to-role assignments \(defined for the subaccount for the runtime node\) and by checking the user role specified in the sender adapter.

> ### Note:  
> We recommend using this option for HTTP inbound connections.
> 
> See also:

Supported by the following sender adapters: HTTPS, IDoc, SOAP \(SOAP RM, SOAP 1.x\), AS2, OData

More information: [Client Certificate Authentication and Certificate-to-User Mapping \(Inbound\), Neo Environment](client-certificate-authentication-and-certificate-to-user-mapping-inbound-neo-environment-4b5afdd.md)



</td>
<td valign="top">

Sender administrator: Configure sender keystore \(generate sender key pair; import CA root certificate supported by load balancer\).

Tenant administrator:

-   Define *Certificate-to-User Mappings* artifact \(to map sender client certificate to user\).

-   In the integration flow / sender adapter, choose the *User Role* authorization option and specify the role \(either keep the role `ESBmessaging.send` or enter a custom role defined for the runtime node\).

-   In SAP BTP cockpit, assign the `ESBMessaging.send` role to the user \(or define own role for runtime node and assign to user\).




</td>
</tr>
<tr>
<td valign="top">

Client certificate



</td>
<td valign="top">

Client-Certificate without certificate-to-user mapping



</td>
<td valign="top">

Load balancer authenticates sender based on a client certificate and, if the check is successful, forwards the certificate's issuer and subject DNs to the tenant in the message header. Tenant checks the permissions of the sender by evaluating the certificate's subject/issuer distinguished name \(DN\).

This is a secure option, but as the client certificate is defined for each integration flow, it has the disadvantage that each time you change \(and redeploy\) the integration flow, there is a brief downtime. Secondly, when the client certificate is renewed, you need to redeploy the integration flow.

Supported by the following sender adapters: HTTPS, IDoc, SOAP \(SOAP RM, SOAP 1.x\), AS2, OData

More information: [Client Certificate Authentication \(Inbound\), Neo Environment](client-certificate-authentication-inbound-neo-environment-c1eeeab.md)



</td>
<td valign="top">

Sender administrator: Configure sender keystore \(generate sender key pair; import CA root certificate supported by load balancer\).

Tenant administrator: In integration flow / sender adapter, choose *Client Certificate* authorization and specify the certificate.



</td>
</tr>
<tr>
<td valign="top">

User role



</td>
<td valign="top">

Basic



</td>
<td valign="top">

Sender sends user credentials \(user name and password\) in the message header.

This option is not recommended for productive usage.

Supported by the following adapters: HTTPS, IDoc, SOAP \(SOAP RM, SOAP 1.x\), AS2, OData

More information: [Basic Authentication](basic-authentication-2c4c2d9.md)



</td>
<td valign="top">

Sender administrator: Enable sender to provide user credentials with the request.

Tenant administrator:

-   In integration flow / sender adapter, choose the *User Role* authorization option and specify the role \(either keep the role `ESBmessaging.send` or enter a custom role defined for the runtime node\).

-   In BTP cockpit, assign the `ESBMessaging.send` role to the user \(or define own role for runtime node and assign to user\).




</td>
</tr>
<tr>
<td valign="top">

User role



</td>
<td valign="top">

OAuth Client Credentials Grant



</td>
<td valign="top">

Grants access to resources of SAP Cloud Integration without the need to share passwords with the client.

Supported by the following sender adapters: SOAP \(SOAP 1.x\), SOAP \(SAP RM\), HTTPS

> ### Note:  
> Usage of JSON Web Token \(JWT\) is also supported for authentication. The advantage of using JWT is that at runtime no additional steps are required to have an identity provider validate the token.
> 
> Therefore, this feature results in a better performance under high load when a token is used for multiple calls within the limit of its validity period.



</td>
<td valign="top">

More information:

[OAuth Client Credentials Grant](oauth-client-credentials-grant-cf611ec.md)



</td>
</tr>
<tr>
<td valign="top">

User role



</td>
<td valign="top">

OAuth SAML Bearer Destination



</td>
<td valign="top">

Grants access to resources of SAP Cloud Integration without the need to share passwords with the client.

You need to set up principal propagation to forward the identity of the user associated with the sender from the sender account to the receiver account.

An SAML 2.0 Bearer Assertion is used to authenticate the sender as well as to request the OAuth 2.0 access token from an OAuth 2.0 authorization server \(hosted in the SAP cloud\).

Supported by the following sender adapters: SOAP \(SOAP 1.x\), SOAP \(SAP RM\), HTTPS



</td>
<td valign="top">

More information:

[OAuth SAML Bearer Destination](oauth-saml-bearer-destination-f931226.md)



</td>
</tr>
</table>

**Related Information**  


[https://blogs.sap.com/2017/06/05/cloud-integration-how-to-setup-secure-http-inbound-connection-with-client-certificates/](https://blogs.sap.com/2017/06/05/cloud-integration-how-to-setup-secure-http-inbound-connection-with-client-certificates/)

[Authentication and Authorization Options \(Inbound\)](authentication-and-authorization-options-inbound-983f2a5.md "When a client calls a server using a secure communication channel, two different kinds of checks are performed subsequently.")



[Setting Up Inbound HTTP Connections \(with Certificate-to-User Mapping\), Neo Environment](setting-up-inbound-http-connections-with-certificate-to-user-mapping-neo-environment-9949c61.md "Using this option, authentication of a sender is performed based on a client certificate. With a certificate-to-user mapping, the certificate is mapped to a user, whose authorizations are checked on the tenant.")

[Setting Up Inbound HTTP Connections \(with Client Certificate Authentication\), Neo Environment](setting-up-inbound-http-connections-with-client-certificate-authentication-neo-environmen-057f4a7.md "Using this option, authentication of a sender is performed based on a client certificate (which is specified in the sender channel of the integration flow).")

[Setting Up Inbound HTTP Connections \(with Basic Authentication\), Neo Environment](setting-up-inbound-http-connections-with-basic-authentication-neo-environment-391c45c.md "")

[Setting Up Inbound HTTP Connections \(with OAuth\), Neo Environment](setting-up-inbound-http-connections-with-oauth-neo-environment-e5cb7ea.md "")

