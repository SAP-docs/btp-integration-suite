<!-- loiodb96a4cb780b4a3f8e65fdf17d75fa6e -->

# Renewal of OpenPGP Signer Key - Inbound

In this use case, the tenant is the receiver \(inbound communication\) and the sender renews the signer key.

The following figure illustrates the communication path that is relevant for this use case:

![](images/Renewal_PGP_Signer_Inbound_001b002.png)

1.  Sender administrator: Creates a new PGP key pair for signing.
2.  Sender administrator: Provides the tenant administrator with the new public key and informs the tenant administrator that as of a certain the payloads are signed with the new key.
3.  Tenant administrator: Imports the public key into the PGP Public Keyring of the tenant and checks that the fingerprint of the new PGP public key is correct by comparing the fingerprint with a fingerprint provided via a trustworthy channel \(phone, signed e-mail\).

    This step is only necessary if the public key has not been received through a secure channel.

4.  Tenant administrator: Informs the integration developer that he has to exchange the old encryption user ID with the new encryption user ID in the PGP decryptor step \(only if the new key has a different user ID to the old key\).
5.  Integration developer adapts the integration flow \(only if the new key has a different user ID to the old key\).

    The integration developer adds the new user ID \(or a part of the user ID\) to the list of user IDs in the PGP decryptor step \(so that the old and new user ID are contained in the list of signer user IDs\).

    The adapted integration flow has to be newly deployed. The old user ID must still be kept on the user ID list.

6.  Tenant administrator: Deploys changed PGP Public Keyring on the tenant.

    From now on, the tenant accepts payloads signed with the old key or with the new key.

7.  On the specified date, the sender administrator configures the sender system so that it sends payloads signed with the new key from now on. The sender administrator removes the old key pair.
8.  After the specified date, the tenant administrator removes the old public key from the PGP Public Keyring and deploys the changed PGP Public Keyring on the tenant.

    From now on the tenant only accepts payloads signed with the new key.


**Related Information**  


[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

