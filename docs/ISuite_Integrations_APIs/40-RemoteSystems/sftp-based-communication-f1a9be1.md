<!-- loiof1a9be17b11c4014af1cfa496331710a -->

# SFTP-Based Communication

A tenant can connect **as SFTP client** to an SFTP server \(the latter either hosted at SAP or in the customer landscape\).

Depending on the direction of data flow \(whether the tenant reads data from the SFTP server or writes data to it\), either an SFTP sender adapter or SFTP receiver adapter is involved.

Files are stored on the SFTP server in specific directories referred to as *mailboxes*. For each mailbox, a user is specified in order to control access to the data.

In certain cases, you have the option to choose between the following authentication options for SFTP connectivity in the SFTP \(sender or receiver\) adapter:

-   User Name/Password

-   Public Key




<a name="loiof1a9be17b11c4014af1cfa496331710a__section_vgc_c15_4xb"/>

## User Name/Password Authentication

The tenant connects to the server with a user and authenticates itself against the SFTP server with a password.

The user credentials \(user name and password\) are stored in a User Credentials artifact which has been deployed on the tenant prior to connection set up.



<a name="loiof1a9be17b11c4014af1cfa496331710a__section_wgc_c15_4xb"/>

## Public Key Authentication

In order to set up secure connection between the SFTP client and SFTP server, a combination of symmetric and asymmetric keys is applied.

-   Symmetric \(session\) keys are used in order to encrypt and decrypt data within a data transfer session.
-   Asymmetric key pairs \(on client and server side\) are used in order to encrypt and decrypt the session keys.

Symmetric and asymmetric keys are used by a client and a server exchanging data via SFTP in the following way:

1.  The client connects to the server.
2.  The server sends his public key to the client.
3.  The client checks if the server is a trusted participant by evaluating a known\_hosts file at client's side: if the server's public key is listed there-in, the identity of the server is confirmed.
4.  The client generates a session key \(to be used for one data transfer session\).
5.  The client encrypts the session key with the public key of the server.
6.  The client sends the encrypted session key to the server. As public and private key of one party are mathematical correlated with each other, the server can decrypt the session key using its private key.
7.  The session can now be continued in an encrypted way.
8.  As part of the secure data transfer \(using the session key exchanged by the step before\), the client sends its public key to the server.
9.  The server checks if the public key of the client is known to him \(evaluating an authorized\_keys file on the server side\).
10. The server encrypts a random number with the client's public key and sends it to the client.
11. The client decrypts the random number with its private key and sends the unencrypted random number back to the server. That way, the client authenticates itself on server side.

**Related Information**  


[Inbound SFTP With Public Key Authentication](inbound-sftp-with-public-key-authentication-97e2baa.md "")

[Outbound SFTP With Public Key Authentication](outbound-sftp-with-public-key-authentication-d96b2d7.md "")

