<!-- loiobb416c51c3d64d3fba03bce1b5d06846 -->

# Creating a Key Pair



## Context

OpenPGP provides the option of defining two kinds of keys: primary keys and subkeys. There is no general recommendation for when to use which type.

Usually, a primary key is created for certification and signing, and a subkey is created for encryption for each tenant that uses OpenPGP,but this is just a recommendation.



## Procedure

1.  Start the GPA tool \(by double-clicking `run_gpa.bat` in the tenant-specific directory\).

2.  In the main menu, select *Window* \> *Key Maintenance*.

3.  In the menu of the following window, select *New* \> *New Keys*.

4.  In the *Generate Key* dialog, keep the Algorithm and Key Size \(RSA, 2048\), and specify the following attributes.

    For *Name*, enter a string according to the following naming convention:

    `<speaking tenant name> <tenant alias>.hci.sap.com` 

    For `<speaking tenant name>`, you can use the name of the company, for example \(like `Citi`\).

    Leave the *Email* and *Comment* fields empty.

    Select *Expires* and chose a period of 2 years.

5.  Choose *OK*.

6.  Enter a password \(passphrase\).

    Note that all private keys in the secret keyring must have the same password.

    There's also the option to have multiple secret keys in a PGP secret keyring \(each with a passphrase\). When using PGP secret keys for Cloud Integration, all secret keys must have the same passphrase.

7.  The key is generated.

    If you select the key entry, more details are displayed.

    On the *Subkeys* tab, the usage of the related subkeys is displayed.


**Related Information**  


[Deploying a PGP Secret Keyring](../50-Development/deploying-a-pgp-secret-keyring-9d8e1a9.md "This artifact contains the PGP secret keys for the usage of Open Pretty Good Privacy (PGP). The private key enables the tenant to decrypt or sign messages.")

