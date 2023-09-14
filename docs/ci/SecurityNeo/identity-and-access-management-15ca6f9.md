<!-- loio15ca6f9403cb41da87aa7f165a4502f5 -->

# Identity and Access Management

Identity and access management features are used during the lifecycle of an integration scenario.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.



## Access Management

Dialog users who access the platform are authenticated against an identity provider. SAP Identity Service \(ID Service\) is used by default. SAP ID Service is the central service for the process of managing identities and their lifecycles.

The authentication of inbound calls to the platform depends on the chosen authentication mode. If the client sends a client certificate, the authentication is done by the load balancer. The load balancer terminates the TLS connection; therefore, it checks the client certificate of the calling component against a list of trusted certification authorities \(CAs\). This certificate is mapped to a user. If basic authentication is configured, the calling entity is checked by the connected identity provider. Besides client certificate authentication, the platform supports basic authentication, OAuth, and Security Assertion Markup Language \(SAML\).



## User Management and Authorizations

Access to dedicated functions of the platform is controlled and protected by authorization checks. A number of authorization groups are available to manage the authorizations of dialog users. An authorization group is based on a persona and defines a set of dedicated permissions relating to the tasks that come into play during the lifecycle of an integration project.

> ### Note:  
> Example:
> 
> If the logged-in user has to perform tasks such as designing and deploying integration flows, the user must be assigned the authorization group `AuthGroup.IntegrationDeveloper`.



<a name="loio15ca6f9403cb41da87aa7f165a4502f5__section_rcc_sww_vgb"/>

## Authorization for the Integration Developer

The tasks of persons with integration developer permissions \(short: integration developers\) constitute a key part of the SAP Cloud Integration lifecycle. Permissions for the integration developer \(who is in charge of modeling integration flows\) are contained in the authorization group `AuthGroup.IntegrationDeveloper`.

Note that the roles contained in this authorization group give an integration developer full control over message processing during runtime.

More information: [Persona](persona-2937e5c.md)

During integration flow modeling, the integration developer defines how messages are mapped, which credentials are used, and to which recipients messages are sent. The set of roles provides very powerful permissions and in some cases allows the integration developer to access sensitive data.

> ### Note:  
> The integration developer can control which credentials are to be used in connections with basic authentication by deploying the associated *User Credentials* artifacts on the tenant. These artifacts contain user names and passwords. Note that, however, a password specified in a *User Credentials* is never displayed. Furthermore, passwords cannot be downloaded \(by either using the user interface or the application programming interface\). The integration developer, although having full control over the integration flow, does not have access to credentials of another tenant of the same customer.

Therefore, apply the following measures when designing integration flows for security-sensitive areas:

-   Don't give the integration developer access to productive systems.

-   Consider applying a four-eyes principle and implement a review process before deploying integration flows to production.

-   An integration developer has the option to develop integration flows on a separate development or test tenant. These integration flows can then be transported to the productive tenant by another person.

-   Consider using client certificate-based authentication rather than basic authentication. When using client certificates, the private key remains in the sender system and no secret password is transmitted through the network.

-   Don’t share the same secret credentials between tenants with different security levels \(for example, between test tenant and productive tenant\).

-   If you suspect a security violation, check the audit log to find out which user deployed the integration flow in question.

-   If read-only access is required to analyze issues in the productive system, use the authorization group `AuthGroup.ReadOnly`.


> ### Tip:  
> Hint: Instead of using the predefined authorization groups, you can tailor the permissions to your own requirements by applying elementary roles that are defined for individual tasks.



## Authentication and Authorization Options for Inbound Calls

When a sender system calls the integration platform using HTTPS-based \(inbound\) requests, there are different ways for the calling sender to authenticate itself against the integration platform. The options are client certificate authentication, basic authentication, OAuth, and SAML.

Detailed access to the resources of the integration platform is controlled by certain authorization options. In sender channels that are based on transport protocol HTTP, the authorization options are *User Role* and *Client Certificate*,

> ### Note:  
> *Client Certificate* is now deprecated. Instead of this, a certificate-to-user mapping should be maintained. When using this option, within user management a role has to be assigned to the user to grant access to the resource.

> ### Note:  
> -   Authentication
> 
>     Verifies the identity of the calling entity.
> 
> -   Authorization
> 
>     Checks what a user or other entity is authorized to do \(for example, as defined by roles assigned to it\). In other words, the authorization check evaluates the access rights of a user or other entity.



<a name="loio15ca6f9403cb41da87aa7f165a4502f5__section_pj4_rbw_1cb"/>

## Combinations of Authentication and Authorization \(Inbound\)

For inbound communication based on HTTPS, the authentication and authorization options can be combined in a specific way.

**Combination of Authentication/Authorization Options**


<table>
<tr>
<th valign="top">

Authentication Option ...



</th>
<th valign="top">

Can Be Used with the Following Authorization Option ...



</th>
</tr>
<tr>
<td valign="top">

Basic authentication

The sender \(client\) authenticates itself against the server based on user credentials \(user name and password\). The HTTP header of the inbound message \(from the sender\) contains the user name and password.



</td>
<td valign="top">

Role-based authorization

For this user, the authorizations are checked based on user-to-role assignments defined on the tenant.

> ### Note:  
> When you use Cloud Integration in the Cloud Foundry environment, as user credentials you can also use clientid and clientsecret from a Process Integration service instance with plan *integration-flow* and *client\_credentials* grant type.



</td>
</tr>
<tr>
<td valign="top">

Client-certificate authentication and certificate-to-user mapping \(only in the Neo environment\)

The sender \(client\) authenticates itself against the server based on a digital client certificate. Furthermore, this certificate is mapped to a user \(based on the information contained in a *Certificate-to-User Mapping* artifact deployed on the tenant\).

> ### Note:  
> You can map multiple certificates to the same user \(n:1 certificate-to-user mappings possible\).



</td>
<td valign="top">

Role-based authorization

For the user derived from the certificate-to-user mapping, the authorizations are checked based on user-to-role assignments defined on the tenant.



</td>
</tr>
<tr>
<td valign="top">

Client-certificate authentication

\(without certificate-to-user mapping\)

The sender \(client\) authenticates itself against the server based on a digital client certificate.



</td>
<td valign="top">

Subject/Issuer DN authorization check of a certificate

In a subsequent authorization check, the permissions of the sender are checked on the tenant by evaluating the distinguished name \(DN\) of the client certificate of the sender.



</td>
</tr>
<tr>
<td valign="top">

OAuth

Grants access to resources of SAP Cloud Integration without the need to share passwords with the client.

> ### Note:  
> This option is supported for the following sender adapter types: SOAP \(SOAP 1.x\), SOAP \(SAP RM\), HTTPS, and OData.



</td>
<td valign="top">

Role-based authorization



</td>
</tr>
</table>

**Related Information**  


[User Management for SAP BTP, Neo Environment](../Operations/user-management-for-sap-btp-neo-environment-f319277.md "Users management tasks are required for different activities associated with the setup and operation of the cluster.")

[Managing Users and Role Assignments, Neo Environment](../Operations/managing-users-and-role-assignments-neo-environment-1d470b0.md "You specify the members of the account and assign roles to them.")

[Load Balancer Root Certificates Supported by SAP](../ConnectionSetup/load-balancer-root-certificates-supported-by-sap-4509f60.md "The load balancer supports a certain list of root certificates.")

[Authentication and Authorization Options \(Inbound\)](../ConnectionSetup/authentication-and-authorization-options-inbound-983f2a5.md "When a client calls a server using a secure communication channel, two different kinds of checks are performed subsequently.")

[Persona](persona-2937e5c.md "When you perform user management tasks using SAP BTP SAP BTP cockpit, you find a set of predefined roles that you can assign to users of the account. According to the main tasks associated with integration projects, these roles are associated to certain persona relevant for an integration project.")

