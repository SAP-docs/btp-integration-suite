<!-- loio983f2a5f994146ab8daff1f97d6db3dd -->

# Authentication and Authorization Options \(Inbound\)

When a client calls a server using a secure communication channel, two different kinds of checks are performed subsequently.

-   Authentication

    Verifies the identity of the calling entity.

-   Authorization

    Checks what a user or other entity is authorized to do \(for example, as defined by roles assigned to it\). In other words, the authorization check evaluates the access rights of a user or other entity.


When a client calls a server, it is first authenticated and, in a subsequent step, the authorization check is performed.

We use **inbound** to refer to the communication direction when a sender system sends a message to the integration platform.



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

Client-certificate authentication

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



More information: [OAuth 2.0 Specification](https://oauth.net/2/)

**Related Information**  


[Protecting Applications with OAuth 2.0](https://help.hana.ondemand.com/help/frameset.htm?b7b589334d444293a2a91e0ef4234136.html)

[Authentication Options \(Inbound\)](authentication-options-inbound-5495ee0.md "For inbound communication, different ways are supported how the sender can authenticate itself against Cloud Integration.")

[Authorization Options \(Inbound\)](authorization-options-inbound-c98c87e.md "For inbound HTTPS requests, two different ways to check the authorization of the caller can be configured.")

