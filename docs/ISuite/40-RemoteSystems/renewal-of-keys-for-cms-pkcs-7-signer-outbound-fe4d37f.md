<!-- loiofe4d37f7b09c45818e8e818fc3fe73a9 -->

# Renewal of Keys for CMS/PKCS\#7 Signer - Outbound

This use case covers all situations where private keys \(used by the tenant to sign outbound messages\) are changed. The renewal process ensures that the related public verification key is changed at the receiver side that way that no downtime is required.

The signer \(when configured to use the CMS/PKCS\#7 standard\) uses one or more private keys to sign a single payload. These private keys are provided in the outbound keystore of the tenant. The resulting signed data object can contain several signatures from different private keys. To locate the different private keys in the keystore, aliases can be specified in the corresponding integration flow signer step.

The following figure illustrates the communication path that is relevant for this use case.

![](images/SAP_HCI_Security_Renewal_-_PKCS7_Outbound_Sign_26b58d0.png)

The renewal process depends on whether the receiver system can verify signed data with different public keys at one point in time.



## Receiver is able to Verify Payloads Signed by the old Key and Payloads Signed by the new Key at the Same Time

This renewal process implies the following sequence of steps.

1.  Tenant administrator: Creates a new key pair.
2.  Tenant administrator: Provides the new certificate to the receiver administrator.
3.  Receiver administrator: Configures the receiver system that way that it is able to verify payloads signed by the old key or payloads signed by the new key.
4.  Receiver administrator: Informs the tenant administrator that the receiver system is able to verify payloads signed by the old key or payloads signed by the new key.
5.  Tenant administrator: Exchanges the old key pair with the new key pair, keeping the old alias.

    From now on outbound messages are signed with the new key.

6.  Tenant administrator: Informs the receiver administrator that the key pair has been exchanged.
7.  Receiver administrator: Removes the old key pair.

    From now on, the receiver system can only verify payloads signed by the new key.




## Receiver is only able to Verify Payloads Signed by the Same Key at one Point in Time

This renewal process requires cooperation of tenant administrator, integration developer and receiver administrator.

> ### Note:  
> Is is assumed that the receiver system can manage CMS/PKCS\#7-signed data containing several signatures. This should be the case because the specification requires it.

1.  Tenant administrator: Creates a new key pair.
2.  Tenant administrator: Adds the new key pair to the keystore with a new alias.
3.  Tenant administrator: Informs the integration developer.
4.  Integration developer: Changes the integration flow.

    In particular, the integration developer adds the new alias to the Signer Parameters table of the CMS/PKCS7 Signer step. All other parameters like *Signature Algorithm*, *Include Certificates*, *Include Signing Time* have to be the same as specified for the entry with the old alias.

    From now on, the tenant sends signed data containing two signatures both from the old and the new key.

5.  Tenant administrator: Provides the new certificate to the receiver administrator and informs him that the tenant is sending from now on signed data containing two signatures, a signature of the old key and a signature of the new key.
6.  Receiver administrator: Exchanges the key pair that way that the receiver system verifies from now on the signature of the new key.
7.  Receiver administrator: Informs the tenant administrator that the receiver system verifies the signature of the new key.
8.  Tenant administrator: Informs the integration developer that he can remove the old alias from the integration flow signer step.
9.  Integration developer: Removes the old alias from the integration flow signer step.

    From now on, the tenant sends signed data with only one signature of the new key.

10. Integration developer: Informs the tenant administrator that the alias has been removed.
11. Tenant administrator: Removes the old key pair from the keystore.



## Receiver can only Verify Payloads Signed by the Same Key at one Point in Time but Accepts PKCS7/CMS Data with two Signatures

This use case is supported as of release 1.7 of the Integration Designer.

This procedure is not applicalbe for system based on AS ABAP.

The following assumptions apply:

-   The receiver system can handle CMS/PKCS7-signed data containing several signatures. Actually this should be the case because this is part of the specification. Note that systems based on AS ABAP do not support this.

-   The PKCS7/CMS signer step contains two aliases, one for the current private key and one for the new private key.

    If this is not the case, the integration developer has to be be asked to add a second alias.


1.  Tenant administrator: Creates a new key pair/certificate.
2.  Tenant administrator: Adds the new certificate to the keystore, taking into account that the alias is used which is specified in the PKCS7/CMS signer step for the new certificate.

    From now on the PKCS7/CMS data format contains two signatures.

3.  Tenant administrator: Provides the receiver administrator with the new certificate.
4.  Receiver administrator: Exchanges the old certificate with the new certificate and performs relevant configuration steps.
5.  Receiver administrator: Informs the tenant administrator that certificate has been exchanged.
6.  Tenant administrator: Removes the old certificate from the keystore.



## Receiver can only Verify Payloads Signed by the Same Key at one Point in Time and Accepts only PKCS/CMS Data with Exaclty one Signature

This procedure is applicaple for systems based on AS ABAP.

> ### Note:  
> This procedure implies a downtime.

1.  Tenant administrator: Creates new key pair/certificate.
2.  Tenant administrator and receiver administrator: Aggree on a downtime.
3.  Tenant administrator: Provides receiver admin with the certificate.
4.  During the downtime:
    1.  Tenant administrator: Exchanges key pair/certificate in keystore, keeping the old alias.
    2.  Receiver administrator: Exchanges the certificate in receiver system.


**Related Information**  


[How PKCS\#7 Works](how-pkcs-7-works-21325d5.md "You have the option to sign and encrypt message payloads based on PKCS#7/CMS Enveloped Data and Signed Data (PKCS stands for Public Key Cryptography Standards).")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

