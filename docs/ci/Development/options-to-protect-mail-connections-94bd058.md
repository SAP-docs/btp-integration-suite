<!-- loio94bd058f8ada42cf9d4e955031292fbe -->

# Options to Protect Mail Connections

With mail sender and receiver adapter, you have several options to protect the communication.

-   *SMTPS* \(receiver adapter\), *IMAPS* \(sender adapter\) or *POP3S* \(sender adapter\)

    Using one of these options, an encryption is already initiated when establishing the connection. The connection in that case is protected using Transport Layer Security \(TLS\). The mail server needs to offer a dedicated port in that case.

-   *STARTTLS*

    Using this option, an existing, unencrypted connection can be changed to an encryptiod one. This works that way that, after the connection has been established, the client request from the server which enhanced operations are supported by the latter. In case it is STARTTLS, the connection is upgraded to an encrypted one.

    The *Protection* parameter in the mail adapter provides two variants of using STARTTLS:

    -   *STARTTTLS Mandatory* 

        If the server supports STARTTLS, the client initiates encryption using TLS \(otherwise, the connection stops with an error\).

    -   *STARTTTLS Optional* 

        If the server supports STARTTLS, the client initiates encryption using TLS \(otherwise, client and server remain connected but communicate without encryption\).



