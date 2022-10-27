<!-- loio7f04458e2f3e4493a4337db1d45099a2 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Deploying a PGP Public Keyring

This artifact contains the public key that enables the tenant to encrypt or verify messages using the Pretty Good Privacy \(PGP\) standard.



<a name="loio7f04458e2f3e4493a4337db1d45099a2__prereq_kjm_bz2_2z"/>

## Prerequisites

You have created a PGP keyring file and stored it on your computer.



<a name="loio7f04458e2f3e4493a4337db1d45099a2__steps_d5l_5df_2z"/>

## Procedure

1.  Select the tile *PGP Keys*.

2.  Go to *Add* and select the option *Public Keys* to upload an artifact.

    > ### Note:  
    > If you upload a new PGP keyring, this newly uploaded key will replace all keys uploaded before.

3.  Browse for the public keyring file on your computer.

4.  Click on *Deploy* to deploy your artifact.

    > ### Note:  
    > After a successful upload, the list will refresh automatically. You can also manually refresh the list by clicking the refresh button \(<span class="SAP-icons"></span>\).

    You can download the PGP Public Keyring artifact. Go to *Monitor* \> *PGP Keys* and select *Download* \> ** \> *Public Keys*.

    To undeploy a Public Keyring artifact, go to *Monitor* \> *Security Material*. Select the artifact from the list and click *Undeploy* \(:wastebasket:\). The system displays a warning and requires you to confirm the task. The undeployed artifact is removed from the list. See also: [Managing Security Material](managing-security-material-b8ccb53.md).


**Related Information**  


[Managing Security Material](managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

[Managing PGP Keys](managing-pgp-keys-cd478a7.md "The PGP Keys monitor allows a tenant administrator to manage the public and private PGP keys.")

[Deploying a PGP Secret Keyring](deploying-a-pgp-secret-keyring-9d8e1a9.md "This artifact contains the PGP Secret Keys for the usage of Open Pretty Good Privacy (PGP). The private key enables the tenant to decrypt or sign messages.")

