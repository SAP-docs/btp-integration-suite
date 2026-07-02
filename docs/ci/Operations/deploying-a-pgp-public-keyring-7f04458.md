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

3.  Browse for the public keyring file on your computer.

    > ### Note:  
    > The selected keyring file can contain 1 or several PGP secret keys in one of the following formats:
    > 
    > -   Binary format \(typical file extension: `.gpg`\)
    > 
    > -   ASCII armored format \(typical file extension: `.asc`\)

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

6.  Select *Deploy* to deploy your artifact.

    > ### Note:  
    > After a successful upload, a dialog is displayed showing the summary of the added, removed, changed, and not imported keys, if there are any. If any keys were not uploaded, information is provided to explain why \(for example, the key with the same key id already exists\). The keys in the table refresh automatically. You can also manually refresh the list by clicking the refresh button \(<span class="SAP-icons-V5"></span>\).




<a name="loio7f04458e2f3e4493a4337db1d45099a2__result_n4q_fmy_wwb"/>

## Results

If deployment isn't successful, the following errors are raised:

-   `The key type you try to upload is invalid.`

    Is displayed if you try to upload secret keys instead of public keys.

-   `File upload impossible due to invalid file format. Select one of the supported file formats.` 

    Is displayed if you try to upload a file with a wrong format \(not `.asc`and not `.gpg`\).


**Related Information**  


[Managing PGP Keys](managing-pgp-keys-cd478a7.md "The PGP Keys monitor allows a tenant administrator to manage the public and private PGP keys.")

