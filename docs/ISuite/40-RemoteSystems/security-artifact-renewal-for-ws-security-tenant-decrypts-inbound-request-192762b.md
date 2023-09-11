<!-- loio192762b074da4dacbfa09034790c91a6 -->

# Security Artifact Renewal for WS-Security \(Tenant Decrypts Inbound Request\)

This use case covers all situations where private keys used by the tenant to decrypt request messages from a sender \(in our terminology: inbound messages\) are changed. The renewal process ensures that the related public encryption key is changed on the sender side so that no downtime is required.

The following figure illustrates the communication path for this use case.

![](images/SAP_HCI_Security_Renewal_-_WS_Security_Inbound_Request_Decrypt_e520af0.png)

1.  Tenant administrator: Creates new key pair/certificate.
2.  Tenant administrator: Adds the new certificate to the keystore.
3.  Tenant administrator: Provides the sender administrator with the new certificate and informs the sender administrator that payloads encrypted with the new key can be sent.
4.  Sender administrator: Configures sender system to send payloads encrypted with the new public key/certificate from now on.
5.  Sender administrator: Removes the old public key/certificate.
6.  Sender administrator: Informs the tenant administrator that the sender system sends payloads encrypted with the new key.
7.  Tenant administrator: Removes the old key pair/certificate from the keystore after a certain time period \(which must be at least the guaranteed delivery time\).

    This time period is necessary to make sure that payloads encrypted with the old key are no longer in the system.


The participants have to make sure that old keys are kept for at least 90 days after they have been exchanged for new ones. This is to ensure that messages can still be decrypted with the old keys for a period of time.

**Related Information**  


[How WS-Security Works](how-ws-security-works-2f9a038.md "Messages can be protected according to the WS-Security standard.")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

