<!-- loio9d8e1a9504ed4da0bc9b4377e1f27c9b -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Deploying a PGP Secret Keyring

This artifact contains the PGP secret keys for the usage of Open Pretty Good Privacy \(PGP\). The private key enables the tenant to decrypt or sign messages.



<a name="loio9d8e1a9504ed4da0bc9b4377e1f27c9b__prereq_ghp_brd_2z"/>

## Prerequisites

You've created a PGP secret keyring and stored it on your computer.

More information: [Creating a Key Pair](../40-RemoteSystems/creating-a-key-pair-bb416c5.md)



## Procedure

1.  Select the tile *PGP Keys*.

2.  Go to *Add* and select the option *Secret Keys* to upload an artifact.

3.  Browse for the secret keyring file on your computer and enter the secret key passphrase.

    > ### Note:  
    > The selected keyring file can contain 1 or several PGP secret keys in one of the following formats:
    > 
    > -   Binary format \(typical file extension: `.gpg`\)
    > 
    > -   ASCII armored format \(typical file extension: `.asc`\)
    > 
    > 
    > To guarantee an adequate security level, SAP Integration Suite doesn’t allow you to upload unencrypted secret keys. Therefore, when uploading a PGP secret key, you need to provide a passphrase, Make sure to specify a secure passphrase that meets the common safety standards.
    > 
    > If you upload a file that contains multiple PGP keys, all of them have to be encrypted with the same passphrase. Import of the keyring file fails if this condition isn’t met. This situation can happen, for example, when you import secret keys from different sources.

    > ### Note:  
    > It is not recommended to download secret keys. If, for certain reasons, you nevertheless need to download secret keys, make sure to use of a sufficiently secure storage location for the downloaded PGP secret keyring file, for example, a password manager.
    > 
    > Why do you need to apply a passphrase again when downloading secret keys? During upload, all keys are decrypted with the passphrase specified by you. In a next step, behind the scenes, the system re-encrypts the keys with a system-generated passphrase that is not disclosed to the user. This step further increases the protection level of your keys. Due to these additional steps, it is necessary that you apply a passphrase also when downloading secret keys. This passphrase is used to encrypt all keys in the downloaded secret keyring file.

4.  For *Action*, select one of the following options:


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Add* 
    
    </td>
    <td valign="top">
    
    Adds the entries from the uploaded keyring. These are merged with the existing keys.

    When you select the option *Overwrite Existing Keys*, existing entries are overwritten by uploaded entries with the same `KeyId` value.

    > ### Note:  
    > A PGP key is considered *identical* to another one if the hexadecimal `KeyId` value of both keys matches. Note that there can be several distinct PGP keys with the same `UserId`.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Replace* 
    
    </td>
    <td valign="top">
    
    Replaces existing keyring including all keys with the uploaded one.

    Replaces the whole keyring with the uploaded one \(replaces only the keys that are already available\).

    You need to confirm the replacement of the existing keys.
    
    </td>
    </tr>
    </table>
    
5.  Confirm to replace existing keys \(only if the option *Overwrite Existing Keys* is selected in the previous step\).

6.  Click *Deploy* to deploy your artifact.

    > ### Note:  
    > After a successful upload, a dialog is displayed showing the summary of the added, removed, changed, and not imported keys, if there are any. If any keys were not uploaded, information is provided to explain why \(for example, the key with the same key id already exists\). The keys in the table refresh automatically. You can also manually refresh the list by clicking the refresh button \(<span class="SAP-icons-V5"></span>\).




<a name="loio9d8e1a9504ed4da0bc9b4377e1f27c9b__result_mmf_qmy_wwb"/>

## Results

If deployment isn't successful, the following errors are raised:

-   `The key type you try to upload is invalid.`

    Is displayed if you try to upload public keys instead of secret keys.

-   `Invalid passphrase.`

    Is displayed if you upload secret key with a wrong passphrase.

-   `File upload impossible due to invalid file format. Select one of the supported file formats.` 

    Is displayed if you try to upload a file with a wrong format \(not `.asc`and not `.gpg`\).


**Related Information**  


[Managing PGP Keys](managing-pgp-keys-cd478a7.md "The PGP Keys monitor allows a tenant administrator to manage the public and private PGP keys.")

