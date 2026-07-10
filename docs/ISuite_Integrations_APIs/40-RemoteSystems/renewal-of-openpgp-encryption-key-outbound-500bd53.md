<!-- loio500bd53681cb43b1b6c9c327850a6247 -->

# Renewal of OpenPGP Encryption Key - Outbound

In this use case, the tenant is the sender \(outbound communication\) and the receiver renews the encryption key.

The following figure illustrates the communication path that is relevant for this use case:

![](images/Renewal_PGP_Encrypt_Outbound_f9b9e4d.png)

The renewal process depends on the capabilities of the customer receiver system.



## Receiver Can Decrypt Payloads Encrypted by the Old Key and Payloads Encrypted by the New Key at One Point in Time

This use case requires a change of the integration flow if the user ID changes.

1.  Receiver administrator: Creates a new PGP key pair.
2.  Receiver administrator: Configures receiver system so that it can decrypt either payloads encrypted with the old key or payloads encrypted with the new key.
3.  Receiver administrator: Provides the tenant administrator with the new PGP public key through a secure channel and informs the tenant administrator that for a certain period of time the receiver system will accept PGP messages encrypted either with the old key or with the new key.
4.  Tenant administrator: Imports the new PGP public key into the PGP Public Keyring.

    If the public key has not been received through a secure channel, the tenant administrator checks that the new imported key has the correct fingerprint by comparing the fingerprint with a fingerprint provided via a trustworthy channel \(phone, signed e-mail\).

5.  Tenant administrator: Informs the integration developer that he has to exchange the old encryption user ID with the new encryption user ID in the PGP encryptor step \(only if the new key has a different user ID to the old key\).
6.  Integration developer adapts the integration flow \(only if the new key has a different user ID to the old key\).

    The integration developer adds the new user ID \(or a part of the user ID\) to the list of user IDs in the PGP encryptor step.

    The adapted integration flow has to be newly deployed. The old user ID must still be kept on the user ID list.

7.  Tenant administrator: Deletes the old public key from the PGP Public Keyring and deploys the changed PGP Public Keyring.

    From now on the payloads are encrypted with the new public key.

8.  After the agreed time period, the receiver administrator removes the old key pair and configures the receiver system so that from now on it can only receive payloads encrypted by the new key.



## Receiver Can Only Decrypt Payloads Encrypted with the Same Key at One Point in Time and Accepts PGP Messages Containing Symmetric Keys Encrypted with Several Asymmetric Keys

This use case requires a change of the integration flow if the user ID changes.

1.  Receiver administrator: Creates new PGP key pair.
2.  Receiver administrator: Provides tenant administrator with the new PGP public key and informs the tenant administrator that the receiver system will only be able to decrypt PGP messages that are encrypted with the new key as of a certain date.

    Note that the PGP message may still contain an additional package containing the symmetric key encrypted with the old key.

3.  Tenant administrator: Imports the new PGP public key into the PGP Public Keyring and checks that the new imported key has the correct fingerprint by comparing the fingerprint with a fingerprint provided via a trustworthy channel \(phone, signed e-mail\).

    This step is only necessary if the public key has not been received through a secure channel.

4.  Tenant administrator: Informs the integration developer that he has to exchange the old encryption user ID with the new encryption user ID in the PGP encryptor step \(only if the new key has a different user ID to the old key\).
5.  Integration developer adapts the integration flow \(only if the new key has a different user ID to the old key\).

    The integration developer adds the new user ID \(or a part of the user ID\) to the list of user IDs in the PGP encryptor step.

    The adapted integration flow has to be newly deployed. The old user ID must still be kept on the user ID list.

6.  Tenant administrator: Deploys the changed PGP Public Keyring. From now on the payload is encrypted with the old key and the new key.
7.  At the specified date the receiver administrator removes the old key from the receiver system.
8.  After the specified date the tenant administrator removes the old public key from the PGP Public Keyring and deploys the changed PGP Public Keyring.

    From now on the payload is only encrypted with the new key.




## Receiver Can Only Decrypt Payloads Encrypted with the Same Key at One Point in Time and Does Not Accept PGP Messages Containing Symmetric Keys Encrypted with Several Asymmetric Keys

This use case requires a downtime.

1.  Receiver administrator: Creates new PGP key pair.
2.  Receiver administrator and tenant administrator agree on a downtime.
3.  Receiver administrator: Provides tenant administrator with the new PGP public key.
4.  Tenant administrator: Imports the new public key into the PGP Public Keyring and checks that the fingerprint of the new PGP public key is correct by comparing the fingerprint with a fingerprint provided via a trustworthy channel \(phone, signed e-mail\). This step is only necessary if the public key was not received through a secure channel.
5.  During downtime, the following happens:
    1.  Tenant administrator: Informs the integration developer that he has to exchange the old encryption user ID with the new encryption user ID in the PGP encryptor step \(only if the new key has a different user ID to the old key\).
    2.  Integration developer adapts the integration flow \(only if the new key has a different user ID to the old key\).

        The integration developer adds the new user ID \(or a part of the user ID\) to the list of user IDs in the PGP encryptor step.

        The adapted integration flow has to be newly deployed.

    3.  Tenant administrator: Removes the old key from the PGP Public Keyring and deploys the PGP Public Keyring.
    4.  Receiver administrator: Exchanges the old key with the new key in the receiver system.


**Related Information**  


[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

