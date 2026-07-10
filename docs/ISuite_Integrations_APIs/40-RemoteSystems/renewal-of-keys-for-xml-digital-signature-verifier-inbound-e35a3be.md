<!-- loioe35a3bea37514edbaea091ab20412d7f -->

# Renewal of Keys for XML Digital Signature Verifier - Inbound

This use case covers all situations where private keys used by a sender to sign messages sent to the tenant \(in our terminology: inbound messages\) based on XML Digital Signature are changed. The renewal process ensures that the related public verification key is changed at the tenant side that way that no or minimum downtime is required.

The verifier \(specified in the integration flow to use the XML Digital Signature standard\) uses a public key to verifiy a payload signed by the sender. This public key has been imported into the tenant keystore as X509 certificate. The verifier uses an alias configured in the corresponding integration flow step to locate the public key in the keystore.



To apply the following process, the following prerequisites are met:

-   The Integration Designer as of version 1.7 is used.
-   The sender sends in the XML Signature information about the signer certificate \(certificate, whole certificate chain, issuer DN and serial number of certificate, or combinations\).
-   The XML Signature Verifier step \(in the integration flow\) contains two aliases, one for the current certificate and one for the new certificate.

    If the alias for the new certificate does not yet exist in the XML Signature step then the integration developer has to add such an alias prior to the renewal process.


1.  Sender administrator: Creates new key air/certificate.
2.  Sender administrator: Provides the tenant administrator with the new certificate.
3.  Tenant administrator: Adds the new certificate to the keystore taking care that for the alias the alias is used which already has been specified in the XML Signature Verifier step \(of the related integration flow\).
4.  Tenant administrator: Informs the sender administrator that payloads signed with the new key can be sent.
5.  Sender administrator: Configures sender system that way that from now on payloads signed with the new private key are being sent.
6.  Sender administrator: Removes the old key pair/certificate.
7.  Sender administrator: Informs the tenant administrator that the sender systems sends payloads signed with the new key.
8.  Tenant administrator: Removes the old certificate from the payload security keystore after a certain time period \(which at least corresponds to the guaranteed delivery time\).

    The time period is necessary to make sure that payloads signed with the old key are no longer in the SAP cloud system.


**Related Information**  


[How XML Signature Works](how-xml-signature-works-9857d50.md "A digital signature ensures the authenticity of a message that way that it guarantees the identity of the signer and that the message was not altered after signing. You have the option to digitally sign and validate a message based on the XML Signature standard (issued by the W3C consortium). Applying this standard means that the digital signature of a document itself is stored as an XML element.")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

