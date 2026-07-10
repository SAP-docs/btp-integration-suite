<!-- loioa6ccceda81e54ef2977079e419df2bc8 -->

# Security Artifact Renewal for WS-Security \(Tenant Signs Inbound Response\)

This use case covers all situations where private keys \(used by the tenant to sign inbound response messages based on WS-Security\) are changed. The renewal process ensures that the related public verification key is changed on the sender side \(that receives the response message\) so that no or only a minimum downtime is required.

The signer \(if configured to use the WS-Security standard\) uses a private key to sign a payload. The private key is provided in the tenant keystore. To locate the private key in the keystore, an alias is specified in the corresponding integration flow signer step.

The signed WS-Security data contains either the certificate of the public key corresponding to the private key or the issuer and serial version number of the certificate so that the receiver can easily determine the public key with which the signature must be verified.

The renewal process depends on whether the sender system \(that sends the request message and receives the response message\) can verify signed data with different public keys at the same time.

The following figure illustrates the communication path for this use case.

![](images/SAP_HCI_Security_Renewal_-_WS_Security_Inbound_Response_Sign_2e4cd81.png)



## Sender is Able to Verify Payloads Signed by the Old Key and Payloads Signed by the New Key at the Same Time

1.  Tenant administrator: Creates a new key pair.
2.  Tenant administrator: Provides the new certificate to the sender administrator.
3.  Sender administrator: Configures the sender system so that it is able to verify payloads signed by the old key and payloads signed by the new key.
4.  Sender administrator: Informs the tenant administrator that the sender system is able to verify payloads signed by the old key and payloads signed by the new key.
5.  Tenant administrator: Exchanges the old key pair with the new key pair, keeping the old alias.

    From now on, outbound messages are signed with the new key.

6.  Tenant administrator: Informs the sender administrator that the key pair has been exchanged.
7.  Sender administrator: Removes the old key pair.

    From now on, the sender system can only verify payloads signed by the new key.


> ### Note:  
> The process is similar to the WS-Security Signer Outbound Request case, however, the role of the receiver administrator is replaced by the role of the sender administrator, and the receiver system is replaced by the sender system.



## Sender is Only Able to Verify Payloads Signed by the Same Key at One Time

1.  Tenant administrator: Creates a new key pair/certificate.
2.  Tenant administrator: Provides the new certificate to the sender administrator.
3.  Tenant administrator: Agrees a downtime with the sender administrator so that no signed messages are sent during the certificate exchange.
4.  Sender administrator: Stops sending signed messages at the start of the agreed downtime.
5.  Sender administrator: Exchanges the old certificate with the new certificate.
6.  Sender administrator: Informs the tenant administrator that message sending has been stopped and that the certificate has been exchanged.
7.  Tenant administrator: Ensures that there are no messages signed with the old key in the system.
8.  Tenant administrator: Exchanges the old key pair/certificate with the new key pair/certificate, keeping the old alias in the keystore.

    From now on, data is signed with the new key.

9.  Tenant administrator: Informs the sender administrator that the key pair/certificate has been exchanged.
10. Sender administrator: Starts sending messages.

The participants have to make sure that old keys are kept for at least 90 days after they have been exchanged for new ones. This is to ensure that messages can still be decrypted with the old keys for a period of time.

**Related Information**  


[How WS-Security Works](how-ws-security-works-2f9a038.md "Messages can be protected according to the WS-Security standard.")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

