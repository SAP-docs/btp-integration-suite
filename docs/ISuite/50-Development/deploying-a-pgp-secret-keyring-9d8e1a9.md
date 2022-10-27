<!-- loio9d8e1a9504ed4da0bc9b4377e1f27c9b -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Deploying a PGP Secret Keyring

This artifact contains the PGP Secret Keys for the usage of Open Pretty Good Privacy \(PGP\). The private key enables the tenant to decrypt or sign messages.



<a name="loio9d8e1a9504ed4da0bc9b4377e1f27c9b__prereq_ghp_brd_2z"/>

## Prerequisites

You've created a PGP secret keyring and stored it on your computer.

More information: [Creating a Key Pair](../40-RemoteSystems/creating-a-key-pair-bb416c5.md)



## Procedure

1.  Select the tile *PGP Keys.*.

2.  Go to *Add* and select the option *Secret Keys* to upload an artifact.

    > ### Note:  
    > If you upload a new PGP keyring, this newly uploaded key will replace all keys uploaded before.

3.  Browse for the secret keyring file on your computer and enter the secret key passphrase.

    > ### Note:  
    > When adding a new secret key, you specify a password. There's also the option to have multiple secret keys in a PGP secret keyring \(each with a passphrase\). When using PGP secret keys for Cloud Integration, all secret keys must have the same passphrase \(see also [Creating a Key Pair](../40-RemoteSystems/creating-a-key-pair-bb416c5.md)\).
    > 
    > It's this secret key passphrase that you enter at this step. If the entered password doesn't match the original one, you can't deploy the artifact and get an error message.

4.  Click *Deploy* to deploy your artifact.

    > ### Note:  
    > After an successful upload, the list will refresh automatically. You can also manually refresh the list by clicking the refresh button \(<span class="SAP-icons"></span>\).

    You can downloadthe PGP Secret Keyring artifact. Go to *Monitor* \> *PGP Keys* and select *Download* \> *Secret Keys*.

    To undeploy a Secret Keyring artifact, go to *Monitor* \> *Security Material*. Select the artifact from the list and click *Undeploy* \(:wastebasket:\). The system displays a warning and requires you to confirm the task. The undeployed artifact is removed from the list. See also: [Managing Security Material](managing-security-material-b8ccb53.md).


**Related Information**  


[Managing Security Material](managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

[Managing PGP Keys](managing-pgp-keys-cd478a7.md "The PGP Keys monitor allows a tenant administrator to manage the public and private PGP keys.")

[Deploying a PGP Public Keyring](deploying-a-pgp-public-keyring-7f04458.md "This artifact contains the public key that enables the tenant to encrypt or verify messages using the Pretty Good Privacy (PGP) standard.")

