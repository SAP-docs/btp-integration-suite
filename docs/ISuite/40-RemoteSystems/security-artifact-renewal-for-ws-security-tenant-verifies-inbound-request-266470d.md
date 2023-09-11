<!-- loio266470d1245c437e9a215e081464f233 -->

# Security Artifact Renewal for WS-Security \(Tenant Verifies Inbound Request\)

This use case covers all situations where private keys used by a sender to sign messages sent to the tenant \(in our terminology: inbound messages\) are changed. The renewal process ensures that the related public verification key is changed on the tenant side so that no downtime is required.

The verifier \(specified in the integration flow as using the WS-Security standard\) uses a public key to verify a request payload signed by the sender. This public key has been imported into the tenant keystore as an X.509 certificate. The verifier uses the information provided in the WS-Security payload to determine the public key in the keystore.

The following figure illustrates the communication path for this use case.

![](images/SAP_HCI_Security_Renewal_-_WS_Security_Inbound_Request_Verify_999b032.png)

1.  Sender administrator: Creates new key pair/certificate.
2.  Sender administrator: Provides the tenant administrator with the new certificate.
3.  Tenant administrator: Adds the new certificate to the tenant keystore.
4.  Tenant administrator: Informs the sender administrator that payloads signed with the new key can be sent.
5.  Sender administrator: Configures sender system to send payloads signed with the new private key from now on.
6.  Sender administrator: Removes the old key pair/certificate.
7.  Sender administrator: Informs the tenant administrator that the sender system sends payloads signed with the new key.
8.  Tenant administrator: Removes the old certificate from the keystore after a certain time period \(which must be at least the guaranteed delivery time\).

    This time period is necessary to make sure that payloads signed with the old key are no longer in the system.


The participants have to make sure that old keys are kept for at least 90 days after they have been exchanged for new ones. This is to ensure that messages can still be decrypted with the old keys for a period of time.

**Related Information**  


[How WS-Security Works](how-ws-security-works-2f9a038.md "Messages can be protected according to the WS-Security standard.")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

