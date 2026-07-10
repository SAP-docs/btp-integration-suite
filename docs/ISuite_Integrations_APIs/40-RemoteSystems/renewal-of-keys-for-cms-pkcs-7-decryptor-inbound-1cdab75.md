<!-- loio1cdab75a73f64c8ebdb1cd082fb00c14 -->

# Renewal of Keys for CMS/PKCS\#7 Decryptor - Inbound

This use case covers all situations where private keys used by the tenant to decrypt messages from a sender \(in our terminology: inbound messages\) are changed. The renewal process ensures that the related public encryption key is changed at sender side that way that no downtime is required.

The CMS/PKCS7 decryptor uses a private key to decrypt a PKCS7/CMS encrypted payload. This private key is provided in the tenant keystore together with a X509 certificate. The decryptor uses an alias configured in the corresponding integration flow step to locate the private key in the keystore.

The following figure illustrates the communication path that is relevant for this use case.

![](images/SAP_HCI_Security_Renewal_-_PKCS7_Inbound_Decrypt_f179f08.png)



## Sender is able to Encrypt Payload with the old Key and the new Key

1.  Tenant administrator: Creates a new key pair.
2.  Tenant administrator: Adds the new key pair and the corresponding certificate into the keystore.

    After this step has been performed, the decryptor accepts payloads encrypted by the old and the new public key.

3.  Tenant administrator: Hands over the new certificate to the sender administrator.
4.  Sender administrator: Exchanges the certificate.
5.  Sender administrator: Informs the tenant administrator.
6.  Tenant administrator: Removes the old key pair from the keystore after a time period \(which at least corresponds to the guaranteed delivery time\) so that he can be sure that no payload encrypted with the old pulic key has been sent.



## Sender is only able to Encrypt Payload with one Key

This process is applicable as of version 1.6 of the Integration Designer.

1.  Tenant administrator: Creates a new key pair/certificate.
2.  Tenant administrator: Adds the new key pair and the corresponding certificate into the keystore.

    From now on, the decryptor accepts payloads encrypted by the old and new public key.

3.  Tenant administrator: Hands over the new certificate to the sender administrator.
4.  Sender administrator: Exchanges the certificate.
5.  Sender administrator: Informs the tenant administrator about the preceding step.
6.  Tenant administrator: Removes the old key pair/certificate from the payload security keystore after a time period \(which at least corresponds to the guaranteed delivery time\) so that he can be sure that no payload encrypted with the old pulic key is being sent.

**Related Information**  


[How PKCS\#7 Works](how-pkcs-7-works-21325d5.md "You have the option to sign and encrypt message payloads based on PKCS#7/CMS Enveloped Data and Signed Data (PKCS stands for Public Key Cryptography Standards).")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

