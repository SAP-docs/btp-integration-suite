<!-- loio78957243ced5427abf130ce3f90d3234 -->

# Security Aspects of Data, Data Flow for Cloud Integration

All data in transit, either exchanged with remote components or internal, can be protected by methods such as encryption.

> ### Note:  
> Mutual TLS \(mTLS\) is equivalent to client certificate authentication. While setting up the TLS connection, client and server exchange certificates. With mTLS, not only server certificates, but also client certificates are validated based on the signatures provided by certification authorities. For more information, see [Client Certificate Authentication \(Outbound\)](../40-RemoteSystems/client-certificate-authentication-outbound-c4e4a15.md) and [Keystore](../40-RemoteSystems/keystore-b163513.md).

During a scenario, the connected remote systems exchange data with each other based on the configured transport protocol. These protocols support different options to protect the exchanged data against unauthorized access. In addition to security at the transport level, the content of the exchanged messages can also be protected by means of digital encryption and signature.



<a name="loio78957243ced5427abf130ce3f90d3234__section_jln_mvw_vgb"/>

## Transport-Level Security

Each adapter allows you to set up a specific security level based on the underlying transport protocol.

**Transport-Level Security Options**


<table>
<tr>
<th valign="top">

Transport Protocol

</th>
<th valign="top">

Transport-Level Security

</th>
</tr>
<tr>
<td valign="top">

HTTP\(S\) \(Hypertext Transfer Protocol Secure\)

</td>
<td valign="top">

Hyper Text Transfer Protocol \(HTTP\) over Transport Layer Security \(TLS\) \(HTTPS\)

TLS is a protocol for secure communication over a computer network that is widely used on the Internet. As TLS is the enhancement of SSL, these terms are often used synonymously.

You can protect communication using Transport Layer Security \(TLS\). In this case, a symmetric key length of at least 128 bits is used \(which is technically enforced\). Default length of asymetric keys provided by SAP is 2048 bits.

> ### Note:  
> The following versions are supported:
> 
> -   For inbound communication: TLS 1.2 and 1.3
> 
> -   For outbound communication: TLS 1.1, 1.2, and 1.3

> ### Note:  
> The HTTP receiver adapter also allows you to use HTTP URLs. However, we do not recommend using this option when transferring confidential data \(including the password for basic authentication\).
> 
> Also, if the network is not entirely trusted, there is no way to verify whether the result of an HTTP request originates from a trustworthy source. Therefore, we do not recommend using this option for productive scenarios over the Internet.

Receiver adapters also support principal propagation via SAP Cloud Connector.

Various authentication options \(basic authentication using user credentials, client certificates, or OAuth\) are supported depending on the selected sender or receiver adapter.

> ### Caution:  
> Consider that we do **not** recommend to use basic authentication in productive scenarios because of the following security aspects:
> 
> Basic authentication has the risk that authentication credentials, for example, passwords, are sent in clear text. Using TLS \(transport-layer security, also referred to as Secure Sockets Layer\) as transport-level encryption method \(when using HTTPS as protocol\) makes sure that this information is nevertheless encrypted on the transport path. However, the authentication credentials might become visible to SAP-internal administrators at points in the network where the TLS connection is terminated, for example, load balancers. If logging is not done properly at such devices, the authentication credentials might become part of log files. Also network monitoring tools used at such devices might expose the authentication information to administrators. Furthermore, the person to whom the authentication credentials belong \(in the previous example, the password owner\) needs to maintain the password in a secure place.

This protocol is supported by all adapter types that allow communication over HTTPS, for example: Ariba, AS2, AS4, ELSTER, Facebook, HTTP, SOAP, IDoc, OData, ODC, OpenConnectors, SAP SuccessFactors, Twitter, XI.

</td>
</tr>
<tr>
<td valign="top">

SFTP \(Secure Shell File Transfer Protocol\)

</td>
<td valign="top">

Secure Shell \(SSH\) is used to securely transfer files in an open network. SSH is a network protocol that allows you to set up a secure connection to a remote computer, namely an SFTP server.

SSH uses a symmetric key length with at least 128 bits to protect FTP communication. Default length of asymmetric keys provided by SAP is 2048 bits.

Supported authentication methods:

-   User name/password authentication \(where the SFTP server authenticates the calling component based on the user name and password\)

-   Public key authentication \(where the SFTP server authenticates the calling component based on a public key\)


Secure data transfer with SFTP is based on a combination of symmetric and asymmetric keys. Symmetric \(session\) keys are used to encrypt and decrypt data within a session. Asymmetric key pairs are used to encrypt and decrypt the session keys.

When asymmetric key pairs are used, SFTP also ensures that only authorized public keys are used by the involved participants.

Supported versions:

-   SSH version 2 \(as specified at [The Secure Shell \(SSH\) Protocol Architecture](http://tools.ietf.org/html/rfc4251)\)
-   SSH File Transfer Protocol \(SFTP\) version 3 or higher

This protocol is supported by the SFTP sender and receiver adapter.

</td>
</tr>
<tr>
<td valign="top">

FTPS \(Secure File Transfer Protocol\)

</td>
<td valign="top">

This protocol is used to transfer files from and to file servers. This is an extension of the File Transfer Protocol \(FTP\).

This protocol is supported by the FTP sender and receiver adapter.

</td>
</tr>
<tr>
<td valign="top">

JMS \(Java Message Service\)

</td>
<td valign="top">

JMS is an API that supports reliable asynchronous communication based on a JMS Message Broker.

This protocol is supported by the JMS sender and receiver adapter.

</td>
</tr>
<tr>
<td valign="top">

JDBC \(Java Database Connectivity\)

</td>
<td valign="top">

Java Database Connectivity \(JDBC\) is a protocol or API that defines how a client accesses a database.

This protocol is supported by the JDBC receiver adapter.

</td>
</tr>
<tr>
<td valign="top">

RFC \(Remote Function Call\)

</td>
<td valign="top">

Remote Function Call \(RFC\) is an SAP-proprietary protocol that is used as standard for the communication of SAP systems.

This protocol is supported by the RFC receiver adapter.

</td>
</tr>
<tr>
<td valign="top">

TCP \(Transmission Control Protocol\)

</td>
<td valign="top">

TCP is one of the main communication protocols used on the Internet. TLS, previously mentioned, often \(but not always\) runs on top of TCP.

This protocol is supported by the AMQP \(TCP\) and the LDAP adapter.

</td>
</tr>
<tr>
<td valign="top">

WebSocket

</td>
<td valign="top">

WebSocket is a protocol that supports simultaneous communication in both directions \(full-duplex\). This protocol is used for setting up connections with a messaging systems.

This protocol is supported by the AMQP \(WebSocket\) adapter.

</td>
</tr>
<tr>
<td valign="top">

SMTPS \(Simple Mail Transfer Protocol Secure\)

</td>
<td valign="top">

This protocol enables a computer to exchange emails with a mail server. With SMTPS, SMTP connections can be secured by SSL or TLS.

Transport encryption is supported via the STARTTLS extended operation.

To authenticate against the e-mail server, you can send user name and password in plain text or encrypted \(the latter only in case the e-mail server supports this option\).

> ### Note:  
> The \(optional\) password-based authentication only applies to communication between the Cloud Integration system and the mail server. Communication between mail servers is usually not authenticated. Therefore, you must not assume that data received by mail comes from a trustworthy source, unless other security measures \(such as digital signatures at message level\) are applied.

This protocol is used by the Mail receiver adapter.

</td>
</tr>
<tr>
<td valign="top">

POP3S \(Post Office Protocol version 3 over TLS/SSL\)

</td>
<td valign="top">

This option enables email clients to retrieve emails from an email server using the Internet Protocol \(IP\).

Transport encryption is supported via the STARTTLS extended operation.

To authenticate against the e-mail server, you can send user name and password in plain text or encrypted \(the latter only in case the e-mail server supports this option\).

> ### Note:  
> The \(optional\) password-based authentication only applies to communication between the Cloud Integration system and the mail server. Communication between mail servers is usually not authenticated. Therefore, you must not assume that data received by mail comes from a trustworthy source, unless other security measures \(such as digital signatures at message level\) are applied.

This protocol can be used by the Mail sender adapter.

</td>
</tr>
<tr>
<td valign="top">

IMAPS \(Internet Message Access Protocol over TLS/SSL\)

</td>
<td valign="top">

Internet Message Access Protocol over TLS/SSL \(IMAPS\).

This option enables email clients to retrieve emails from an email server using a TCP/IP connection.

Transport encryption is supported via the STARTTLS extended operation.

To authenticate against the e-mail server, you can send user name and password in plain text or encrypted \(the latter only in case the e-mail server supports this option\).

> ### Note:  
> The \(optional\) password-based authentication only applies to communication between the Cloud Integration system and the mail server. Communication between mail servers is usually not authenticated. Therefore, you must not assume that data received by mail comes from a trustworthy source, unless other security measures \(such as digital signatures at message level\) are applied.

This protocol can be used by the Mail sender adapter.

</td>
</tr>
</table>



<a name="loio78957243ced5427abf130ce3f90d3234__section_uqg_nvw_vgb"/>

## Message-Level Security

On top of the *transport-level security* options, you can also secure the communication at *message level*, where the content of the exchanged messages can also be protected by means of digital encryption and signatures. Various security standards are available to do this, as summarized in the following table.

To configure message-level security options, you use dedicated integration flow steps \(for example, the *Encryptor* and *Signer* step types\).

The following standards and algorithms are supported:

**Message-Level Security Standards and Algorithms**


<table>
<tr>
<th valign="top">

Standard

</th>
<th valign="top">

Security Feature

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

PKCS\#7/CMS Enveloped Data and Signed Data

</td>
<td valign="top">

Encryption/decryption of message content

</td>
</tr>
<tr>
<td valign="top">

Signing/verification of payload

</td>
</tr>
<tr>
<td valign="top">

PKCS\#7/CMS Enveloped and Signed Data

</td>
<td valign="top">

Encryption/decryption and signing/verification of payload

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Open Pretty Good Privacy \(PGP\)

</td>
<td valign="top">

Encryption/decryption of message content

</td>
</tr>
<tr>
<td valign="top">

Encryption/decryption and signing/verification of message

</td>
</tr>
<tr>
<td valign="top">

XML Signature

</td>
<td valign="top">

Signing/verification of payload

</td>
</tr>
<tr>
<td valign="top">

WS-Security

</td>
<td valign="top">

Signing/verification of SOAP body

</td>
</tr>
</table>

**Related Information**  


[Connectivity (Adapters)](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/55325f2a722c4f67bb7752b369b09ff8.html "You have the option to specify which technical protocols should be used to connect a sender or a receiver to the tenant.") :arrow_upper_right:

[Authentication and Authorization Options \(Inbound\)](../40-RemoteSystems/authentication-and-authorization-options-inbound-983f2a5.md "When a client calls a server using a secure communication channel, two different kinds of checks are performed subsequently.")

[Authentication Options \(Outbound\)](../40-RemoteSystems/authentication-options-outbound-58a7537.md "For outbound communication through HTTPS (when the tenant sends a message to a receiver), the following authentication options are supported.")

[Certificate Management](../40-RemoteSystems/certificate-management-feb9c2f.md "")

[Message-Level Security](../40-RemoteSystems/message-level-security-463a908.md "Several standards are supported to protect the message content (message-level security).")

