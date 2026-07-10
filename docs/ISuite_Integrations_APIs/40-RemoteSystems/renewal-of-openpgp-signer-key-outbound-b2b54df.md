<!-- loiob2b54dfac8074091b0393bf2132c9283 -->

# Renewal of OpenPGP Signer Key - Outbound

In this use case, the tenant is the sender \(outbound communication\) and renews the signer key.

The following figure illustrates the communication path that is relevant for this use case:

![](images/Renewal_PGP_Sign_Outbound_e142dde.png)

The renewal process depends on the capabilities of the customer receiver system.



## Receiver Can Verify Payloads Signed with the Old Key and Payloads Signed with the New Key at One Point in Time

1.  Tenant administrator: Creates a new PGP key pair in the tenant's PGP Secret Keyring with the same user ID as the old key \(without deploying the changed PGP Secret Keyring yet\).
2.  Tenant administrator: Exports the new PGP public key and provides receiver administrator with the new PGP public key via a secure channel. The tenant administrator informs the receiver administrator that as of a certain date the tenant will send payloads signed with the new key.
3.  Receiver administrator: Configures the receiver system so that it can verify payloads signed with the old key or payloads signed with the new key.
4.  On the specified date, the tenant administrator removes the old key from the PGP Secret Keyring and deploys the changed PGP Secret Keyring on the tenant.

    From now on the payloads are signed with the new key.

5.  After the specified date, the receiver administrator removes the old key so that from now on the receiver system can only verify payloads signed by the new key.



## Receiver Can Only Verify Payloads Signed with the Same Key at One Point in Time but Accepts PGP Messages with Two Signatures

1.  Tenant administrator: Creates a new PGP key pair in the tenant's PGP Secret Keyring with the same user ID as the old key.
2.  Tenant administrator: Deploys the changed PGP Secret Keyring on the tenant.

    From now on, the signed PGP message will contain two signatures, one from the old key and one from the new key.

3.  Tenant administrator: Exports the new PGP public key and provides the receiver administrator with the new public key and informs the receiver administrator about the following:
    -   For a certain period of time, PGP messages with two signatures will be sent.
    -   After this period, PGP messages with one signature made by the new key will be sent

4.  Before the specified period ends, the receiver administrator exchanges the old key with the new key and configures the receiver system so that it now verifies the signature with the new key.
5.  After the specified period the tenant administrator removes the old key from the PGP Secret Keyring and deploys the changed PGP Secret Keyring on the tenant.

    From now on, PGP messages signed by the new key are sent.




## Receiver Can Only Verify Payloads Signed with the Same Key at One Point in Time and Accepts Only PGP Messages with Exactly One Signature

This use case requires a downtime.

1.  Tenant administrator: Creates a new PGP key pair in the tenant's PGP Secret Keyring with the same user ID as the old key.
2.  Tenant administrator and receiver administrator agree on a downtime.
3.  Tenant administrator: Exports the new public key from the PGP Secret Keyring and provides the receiver administrator with the exported public key.
4.  During downtime, the following happens:
    1.  Tenant administrator: Removes the old key from the PGP Secret Keyring and deploys the changed PGP Secret Keyring on the tenant.
    2.  Receiver administrator: Exchanges the old key with the new key in the receiver system.


**Related Information**  


[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

