<!-- loio5495ee0775004999a73ce72a074d6fc7 -->

# Authentication Options \(Inbound\)

For inbound communication, different ways are supported how the sender can authenticate itself against Cloud Integration.

We use **inbound** to refer to the communication direction when a sender system sends a message to the integration platform.

-   **Basic authentication**

    The calling entity is authenticated based on credentials \(user name and password\)

-   **Client-certificate authentication and certificate-to-user mapping**

    The calling entity is authenticated based on a certificate, and the certificate is mapped to a user \(for which the authorization check is executed in a subsequent step\).

-   **Client-certificate authentication** 

-   OAuth 2.0

    OAuth allows you to set up authentication scenarios without the need to share credentials.

    See:

    [Protecting Applications with OAuth 2.0](https://help.hana.ondemand.com/help/frameset.htm?b7b589334d444293a2a91e0ef4234136.html)

    [OAuth 2.0 Specification](https://oauth.net/2/) 


**Related Information**  


[Basic Authentication](basic-authentication-2c4c2d9.md "Basic authentication allows a client to authenticate itself against the server based on user credentials.")

[Client Certificate Authentication and Certificate-to-User Mapping \(Inbound\), Neo Environment](client-certificate-authentication-and-certificate-to-user-mapping-inbound-neo-environment-4b5afdd.md "This option includes an authentication step based on a digital client certificate and the mapping of the certificate to a user.")

[Client Certificate Authentication \(Inbound\), Neo Environment](client-certificate-authentication-inbound-neo-environment-c1eeeab.md "This option includes an authentication step based on a digital client certificate.")

[Setting Up Inbound HTTP Connections \(with OAuth\), Neo Environment](setting-up-inbound-http-connections-with-oauth-neo-environment-e5cb7ea.md "")

