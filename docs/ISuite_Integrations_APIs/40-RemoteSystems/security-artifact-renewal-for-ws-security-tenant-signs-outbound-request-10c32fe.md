<!-- loio10c32fe6f7a64b7ba7327e3d57264667 -->

# Security Artifact Renewal for WS-Security \(Tenant Signs Outbound Request\)

This use case covers all situations where private keys \(used by the tenant to sign outbound messages based on WS-Security\) are changed. The renewal process ensures that the related public verification key is changed on the receiver side so that no or only a minimum downtime is required.

The signer \(if configured to use the WS-Security standard\) uses a private key to sign a payload. The private key is provided in the outbound keystore of the tenant. To locate the private key in the keystore, an alias is specified in the corresponding integration flow signer step.

The signed WS-Security data contains either the certificate of the public key corresponding to the private key or the issuer and serial version number of the certificate so that the receiver can easily determine the public key with which the signature must be verified.

The renewal process depends on whether the receiver system can verify signed data with different public keys at the same time.



## Receiver is Able to Verify Payloads Signed by the Old Key and Payloads Signed by the New Key at the Same Time

The same process applies as for the PKCS\#7/CMS Signer in the same case.



## Receiver is Only Able to Verify Payloads Signed by the Same Key at One Time

The same process applies as for the XML Digital Signer in the same case.

The participants have to make sure that old keys are kept for at least 90 days after they have been exchanged for new ones. This is to ensure that messages can still be decrypted with the old keys for a period of time.

**Related Information**  


[How WS-Security Works](how-ws-security-works-2f9a038.md "Messages can be protected according to the WS-Security standard.")

[Renewal of Keys for CMS/PKCS\#7 Signer - Outbound](renewal-of-keys-for-cms-pkcs-7-signer-outbound-fe4d37f.md "This use case covers all situations where private keys (used by the tenant to sign outbound messages) are changed. The renewal process ensures that the related public verification key is changed at the receiver side that way that no downtime is required.")

[Renewal of Keys for XML Digital Signature Signer - Outbound](renewal-of-keys-for-xml-digital-signature-signer-outbound-aaeaa2f.md "This use case covers all situations where private keys (used by the tenant to sign outbound messages based on XML Digital Signature) are changed. The renewal process ensures that the related public verification key is changed at the receiver side that way that no downtime is required.")

