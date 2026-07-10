<!-- loio39afbfa5feeb4a92be2ef0f45430d3a5 -->

# Renewal of Keys for CMS/PKCS\#7 Encryptor - Outbound

This use case covers all situations where a private key used for message decryption is changed by a receiver. The renewal process ensures that the related public encryption key is changed at the tenant side that way that no downtime is required.

The encryptor \(specified in the integration flow to use the CMS/PKCS\#7 standard\) uses one or serveral public keys to encrypt a payload. The resulting enveloped data then contains one or several recipient information elements corresponding to the public keys. These recipient information elements contain information about the certificates corresponding to the public keys \(issuer DN and serial number of the certificate\). The encryptor uses aliases configured in the integration flow step to loacte the certificates in the keystore.

The following figure illustrates the communication path that is relevant for this use case.

![](images/SAP_HCI_Security_Renewal_-_PKCS7_Outbound_Encrypt_3c254d6.png)



## Receiver is able to Decrypt Payloads Encrypted by the Old Key and Payloads Encrypted by the New Key at one Point in Time

1.  Receiver administrator: Creates a new key pair.
2.  Receiver administrator: Configures receiver system that way that it either can verify payloads encrytped with the old key or payloads encrypted with the new key.
3.  Receiver administrator: Prrovides the new public to the tenant administrator.
4.  Tenant administrator: Exchanges the public key \(certificate\) with the new public key, keeping the old alias.

    From now on, messages are being encrypted with the new key.

5.  Tenant administrator: Informs the receiver administrator that certificate has been exchanged.
6.  Receiver administrator: Removes the old key pair.



## Receiver is only able to Decrypt Payloads Encrypted by the Same Key at one Point in Time

> ### Note:  
> It is assumed that receiver system can manage CMS/PKCS7 enveloped data containing several encryption recipients.

1.  Receiver administrator: Creates a new key pair.
2.  Receiver administrator: Provides the public key to the tenant administrator.
3.  Tenant administrator: Adds the new public key to the keystore with a new alias.
4.  Tenant administrator: Informs the integration developer that new certificate with new alias has been added for encryption usage.
5.  Integration developer: Changes the integration flow.

    The integration developer adds the new alias to the *Receiver Public Key Alias* list of the CMS/PKCS7 *Encryptor* step.

    After this step has been performed, the tenant sends CMS/PKCS7 enveloped data containing two recipient information elements: from the old and from the new certificate.

6.  Tenant administrator: Informs the receiver administrator that the tenant sends CMS/PKCS7 enveloped data with two recipient information elements: from the old and new certificate.
7.  Receiver administrator: Exchanges the certificate that way tha the receiver system now uses the recipient information of the new certificate to decrypt the payload.
8.  Receiver administrator: Removes the old key pair.
9.  Receiver administrator: Informs the tenant administrator that the receiver now uses the recipient information of the new certificate to decrypt the payload.
10. Tenant administrator: Informs the integration developer that the old alias can be removed from the integration flow encryptor step.
11. Integration developer: Removes the old alias from the integration flow encryptor step.

    After this step has been performed, the sent CMS/PKCS7 enveloped data does only contain one recipient information of the new certificate.

12. Integration developer: Informs the tenant administrator that the alias has been removed.
13. Tenant administrator: Removes the old certificate from keystore.



## Receiver can only Decrypt Payloads Encrypted by the Same Key at one Point in Time and Accepts PKCS7/CMS-Enveloped Data Containing Symmetric Keys Encrypted by Several Asymmetric Keys

This procedure is supported as of release 1.7 of the Integration Designer.

This procedure is applicable for systems based on AS ABAB.

The following assumptions apply:

-   The receiver system can handle with CMS/PKCS7-enveloped data containing several encryption recipients. This should be the case because this is part of the specification.
-   The PKCS7/CMS encryptor step contains two aliases, one for the current public key and one for the new public key. If this is not the case, the integration developer has to be asked to add a second alias.

1.  Receiver administrator: Creates new key pair/certificate.
2.  Receiver administrator: Provides new certificate to the tenant administrator.
3.  Tenant administrator: Adds new certificate to the keystore taking into account that the alias is used which is specified in the PKCS7/CMS encryptor step for the new certificate.

    From now on the PKCS7/CMS enveloped data contains two encrpytions of the symmetric key.

4.  Tenant administrator: Informs the receiver administrator that PKCS7/CMS-enveloped data are sent with two encryptions for the symmetric key.
5.  Receiver administrator: Exchanges old key pair/certificate with the new one.
6.  Receiver administrator: Informs the tenant administrator that the certificate has been exchanged.
7.  Tenant administrator: Removes old certificate from the keystore.



## Receiver can Only Decrypt Payloads Encrypted by the Same Key at one Point in Time and Does not Accept PKCS7/CMS-Enveloped Data Containing Symmetric Keys Encrypted by Several Asymmetric Keys

This procedure implies a downtime.

1.  Receiver administrator: Creates new key pair/certificate.
2.  Receiver administrator and tenant administrator: Aggree on a downtime.
3.  Receiver administrator: Provides tenant administrator with certificate.
4.  During the downtime:
    1.  Receiver administrator: Exchanges the old key pair/certificate with the new one.
    2.  Tenant administrator: Exchanges the old certificate with the new one, keeping the old alias


**Related Information**  


[How PKCS\#7 Works](how-pkcs-7-works-21325d5.md "You have the option to sign and encrypt message payloads based on PKCS#7/CMS Enveloped Data and Signed Data (PKCS stands for Public Key Cryptography Standards).")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

