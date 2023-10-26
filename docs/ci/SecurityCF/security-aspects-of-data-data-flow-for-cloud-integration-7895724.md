<!-- loio78957243ced5427abf130ce3f90d3234 -->

# Security Aspects of Data, Data Flow for Cloud Integration

All data in transit, either exchanged with remote components or internal, can be protected by methods such as encryption.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Cloud Foundry environment.

> ### Note:  
> Mutual TLS \(mTLS\) is equivalent to client certificate authentication. While setting up the TLS connection, client and server exchange certificates. With mTLS, not only server certificates, but also client certificates are validated based on the signatures provided by certification authorities. For more information, see [Client Certificate Authentication \(Outbound\)](../ConnectionSetup/client-certificate-authentication-outbound-c4e4a15.md) and [Keystore](../ConnectionSetup/keystore-b163513.md).

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

SFTP \(Secure Shell File Transfer Protocol\)

</td>
<td valign="top">

This protocol is supported by the SFTP sender and receiver adapter.

Secure Shell \(SSH\) is used to securely transfer files in an open network.

SSH uses a symmetric key length with at least 128 bits to protect FTP communication. Default length of asymetric keys provided by SAP is 2048 bits..

Supported authentication methods:

-   User name/password authentication \(where the SFTP server authenticates the calling component based on the user name and password\)

-   Public key authentication \(where the SFTP server authenticates the calling component based on a public key\)


Secure data transfer with SFTP is based on a combination of symmetric and asymmetric keys. Symmetric \(session\) keys are used to encrypt and decrypt data within a session. Asymmetric key pairs are used to encrypt and decrypt the session keys.

When asymmetric key pairs are used, SFTP also ensures that only authorized public keys are used by the involved participants.

Supported versions:

-   SSH version 2 \(as specified at http://tools.ietf.org/html/rfc4251\)
-   SSH File Transfer Protocol \(SFTP\) version 3 or higher



</td>
</tr>
<tr>
<td valign="top">

HTTP\(S\) \(Hypertext Transfer Protocol Secure\)

</td>
<td valign="top">

This protocol is supported by all adapters that allow communication over HTTPS \(for example, the IDoc adapter, the SOAP adapters, and the HTTP adapter\).

You can protect communication using Transport Layer Security \(TLS\). In this case, a symmetric key length of at least 128 bits is used \(which is technically enforced\). Default length of asymetric keys provided by SAP is 2048 bits.

> ### Note:  
> SAP Cloud Integration supports:
> 
> -   For inbound communication: TLS 1.2
> 
> -   For outbound communication: TLS 1.1, 1.2 and 1.3

> ### Note:  
> The HTTP receiver adapter also allows you to use HTTP URLs. However, we do not recommend using this option when transferring confidential data \(including the password for basic authentication\).
> 
> Also, if the network is not entirely trusted, there is no way to verify whether the result of an HTTP request originates from a trustworthy source. Therefore, we do not recommend using this option for productive scenarios over the Internet.

Receiver adapters also support principal propagation via SAP Cloud Connector.

Various authentication options \(basic authentication using user credentials, client certificates, or OAuth\) are supported depending on the selected sender or receiver adapter.

> ### Caution:  
> Consider that we do **not** recommend to use basic authentication in productive scenarios because of the following security aspects:
> 
> Basic authentication has the risk that authentication credentials, for example, passwords, are sent in clear text. Using TLS \(transport-layer security, also referred to as Secure Sockets Layer\) as transport-level encryption method \(when using HTTPS as protocol\) makes sure that this information is nevertheless encrypted on the transport path. However, the authentication credentials might become visible to SAP-internal administrators at points in the network where the TLS connection is terminated, for example, load balancers. If logging is not done properly at such devices, the authentication credentials might become part of log files. Also network monitoring tools used at such devices might expose the authentication information to administrators. Furthermore, the person to whom the authentication credentials belong \(in the example above, the password owner\) needs to maintain the password in a secure place.



</td>
</tr>
<tr>
<td valign="top">

SMTP \(Simple Mail Transfer Protocol\)

</td>
<td valign="top" rowspan="3">

These protocols are supported for the exchange of e-mails \(in combination with the Mail adapter\).

Transport encryption is supported via the STARTTLS extended operation.

To authenticate against the e-mail server, you can send user name and password in plain text or encrypted \(the latter only in case the e-mail server supports this option\).

> ### Note:  
> The \(optional\) password-based authentication only applies to communication between the Cloud Integration system and the mail server. Communication between mail servers is usually not authenticated. Therefore, you must not assume that data received by mail comes from a trustworthy source, unless other security measures \(such as digital signatures at message level\) are applied.



</td>
</tr>
<tr>
<td valign="top">

POP3 \(Post Office Protocol \)

</td>
</tr>
<tr>
<td valign="top">

IMAP \(Internet Message Access Protocol \)

</td>
</tr>
</table>



<a name="loio78957243ced5427abf130ce3f90d3234__section_uqg_nvw_vgb"/>

## Message-Level Security

On top of the *transport-level security* options, you can also secure the communication at *message level*, where the content of the exchanged messages can also be protected by means of digital encryption and signatures. Various security standards are available to do this, as summarized in the table below.

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


[Connectivity \(Adapters\)](../WhatIsCloudIntegration/connectivity-adapters-55325f2.md "You have the option to specify which technical protocols should be used to connect a sender or a receiver to the tenant.")

[Authentication and Authorization Options \(Inbound\)](../ConnectionSetup/authentication-and-authorization-options-inbound-983f2a5.md "When a client calls a server using a secure communication channel, two different kinds of checks are performed subsequently.")

[Authentication Options \(Outbound\)](../ConnectionSetup/authentication-options-outbound-58a7537.md "For outbound communication through HTTPS (when the tenant sends a message to a receiver), the following authentication options are supported.")

[Certificate Management](../ConnectionSetup/certificate-management-feb9c2f.md "")

[Message-Level Security](../ConnectionSetup/message-level-security-463a908.md "Several standards are supported to protect the message content (message-level security).")

