<!-- loioaaeaa2f8747c4230a04357d46e121b54 -->

# Renewal of Keys for XML Digital Signature Signer - Outbound

This use case covers all situations where private keys \(used by the tenant to sign outbound messages based on XML Digital Signature\) are changed. The renewal process ensures that the related public verification key is changed at the receiver side that way that no downtime is required.

The signer \(when configured to use the XML Digital Signature standard\) uses a private key to sign a payload. The private key is provided in the outbound keystore of the tenant. To locate the private key in the keystore, an alias is specified in the corresponding integration flow signer step.

The renewal process depends on whether the receiver system can verify signed data with different public keys at one point in time.



## Receiver is able to Verify Payloads Signed by the old Key and Payloads Signed by the new Key at the Same Time

1.  Tenant administrator: Creates a new key pair/certificate.
2.  Tenant administrator: Provides the receiver administrator with the new certificate.
3.  Receiver administrator: Configures the receiver system so that the receiver system can verify payloads signed by the old key or payloads signed by the new key.
4.  Receiver administrator: Informs the tenant administrator that the receiver system can verify payloads signed by the old key or payloads signed by the new key.
5.  Tenant administrator: Exchanges the old key pair/certificate with the new key pair/certificate in the keystore, keeping the old alias.

    From now on, the message is signed with the new key.

6.  Tenant administrator: Informs the receiver administrator that certificate has been exchanged.
7.  Receiver administrator: Removes the old certificate that way that from now on the receiver system can only verify payloads signed by the new key.

> ### Note:  
> This is the same process as to be applied for the CMS/PKCS\#7 Signer.



## Receiver is only able to Verify Payloads Signed by the Same Key at one Point in Time

This process implies a downtime.

1.  Tenant administrator: Creates a new key pair/certificate.
2.  Tenant administrator: Provides the receiver administrator with the new certificate.
3.  Tenant administrator: Aggrees with the receiver administrator on a downtime.

    During certificate exchange no signed message is sent.

4.  Tenant administrator: Informs the integration developer that the integration flow which signs the payload shall be undeployed.
5.  Integration developer: Undeploys the integration flow.

    From now on, no further signed message is sent to the receiver system.

6.  Integration developer informs tenant administrator about the preceding step.
7.  Tenant administrator: Exchanges the old key pair/certificate with the new key pair/certificate, keeping the old alias in the keystore.

    From now on, the data are signed with the new key.

8.  Tenant administrator: Informs the receiver administrator that no signed messages are being sent.
9.  Receiver administrator: Exchanges the certificate in the receiver system.
10. Receiver administrator: Informs the tenant administrator that from now on the receiver system expects payloads signed by the new key.
11. Tenant administrator: Informs the integration developer that he can redeploy the integration flow.
12. Integration developer: Redeploys the integration flow.

**Related Information**  


[How XML Signature Works](how-xml-signature-works-9857d50.md "A digital signature ensures the authenticity of a message that way that it guarantees the identity of the signer and that the message was not altered after signing. You have the option to digitally sign and validate a message based on the XML Signature standard (issued by the W3C consortium). Applying this standard means that the digital signature of a document itself is stored as an XML element.")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

