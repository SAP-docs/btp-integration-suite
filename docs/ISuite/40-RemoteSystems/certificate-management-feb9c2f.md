<!-- loiofeb9c2f0213d4f20af8a23475dc4f37b -->

# Certificate Management

Depending on the applied transport- and message-level security option, different types of security artifacts need to be managed and deployed on the tenant.

-   X.509 certificates

    Used for transport-level security TLS and for message-level security using PKCS\#7, WS-Security, and XML Digital Signature.

    They are stored in a Java keystore.

-   PGP keys

    Used for message-level security using Open PGP.

-   Known hosts files

    Required for transport-level security SFTP.

    SFTP keys are also stored in a Java keystore.




**Related Information**  


[X.509 Certificates](x-509-certificates-8d38a83.md "X.509 certificates (that comply with the X.509 standard) are used for transport-level security TLS and for message-level security using PKCS#7, WS-Security, and XML Digital Signature.")

[PGP Keys](pgp-keys-9e7e8f9.md "")

[Known Hosts File](known-hosts-file-5d7e2e7.md "")

