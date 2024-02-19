<!-- loiocd478a7226304ad683c2df69cf6c2a48 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing PGP Keys

The PGP Keys monitor allows a tenant administrator to manage the public and private PGP keys.



<a name="loiocd478a7226304ad683c2df69cf6c2a48__section_ff5_dfq_5sb"/>

## Overview

> ### Caution:  
> This information is only relevant for Edge Integration Cell runtime.
> 
> All changes you make to a key will affect all runtimes associated with that key.

Select *Monitor* \> *Integrations*.

Under *Manage Security*, select *PGP Keys*.

A list of public and secret PGP keys is displayed in a table. For each artifact, the following attributes are displayed:

**Attributes of PGP Keyrings**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*User ID*

</td>
<td valign="top">

States the User ID of this PGP key.

</td>
</tr>
<tr>
<td valign="top">

*Type*

</td>
<td valign="top">

Indicates whether the entry is a public PGP Key or a secret PGP key.

</td>
</tr>
<tr>
<td valign="top">

*Key ID*

</td>
<td valign="top">

States the key ID.

</td>
</tr>
<tr>
<td valign="top">

*Validity State*

</td>
<td valign="top">

Indicates the validity state:

-   *Valid*: The PGP key is valid.

-   *Critical*: The PGP key will expire within the next 14 days.

-   *Expired*: The PGP key is no longer valid.




</td>
</tr>
<tr>
<td valign="top">

*Valid Until*

</td>
<td valign="top">

Indicates the expiration date.

</td>
</tr>
<tr>
<td valign="top">

*Modified On*

</td>
<td valign="top">

Indicates the date and time the entry was last modified.

</td>
</tr>
</table>

To sort and filter the content of the table, choose *Table Settings* \(:gear:\). On the subsequent screen, you can define how the table entries are to be sorted \(by specifying an attribute and whether the entries are to be sorted for that attribute in ascending or descending order\). You can also filter the table entries for certain attributes.



<a name="loiocd478a7226304ad683c2df69cf6c2a48__section_ytv_qfq_5sb"/>

## Actions

**Actions**


<table>
<tr>
<td valign="top">

Display key properties.

</td>
<td valign="top">

To display properties of a dedicated key, click the key.

See: [Displaying Properties of a PGP Key](displaying-properties-of-a-pgp-key-13b3dc9.md)

</td>
</tr>
<tr>
<td valign="top">

Add a keyring.

</td>
<td valign="top">

To add a public keyring, select *Add* \> *Public Keys*.

To add a secret keyring, select *Add* \> *Secret Keys*.

When adding a secret keyring, you need to specify the key passphrase.

See:

-   [Deploying a PGP Public Keyring](deploying-a-pgp-public-keyring-7f04458.md)

-   [Deploying a PGP Secret Keyring](deploying-a-pgp-secret-keyring-9d8e1a9.md)




</td>
</tr>
<tr>
<td valign="top">

Download a keyring.

</td>
<td valign="top">

To download public keys, select *Download* \> *Public Keys.*

To download secret keys, select *Download* \> *Secret Keys.*

When downloading secret keys, you need to specify the key passphrase twice.

> ### Note:  
> It is not recommended to download secret keys. If, for certain reasons, you nevertheless need to download secret keys, make sure to use of a sufficiently secure storage location for the downloaded PGP secret keyring file, for example, a password manager.
> 
> Why do you need to apply a passphrase again when downloading secret keys? During upload, all keys are decrypted with the passphrase specified by you. In a next step, behind the scenes, the system re-encrypts the keys with a system-generated passphrase that is not disclosed to the user. This step further increases the protection level of your keys. Due to these additional steps, it is necessary that you apply a passphrase also when downloading secret keys. This passphrase is used to encrypt all keys in the downloaded secret keyring file.



</td>
</tr>
<tr>
<td valign="top">

Download a single key as file.

</td>
<td valign="top">

To download a dedicated key as a file, click the download button \(<span class="SAP-icons-V5"></span>\) at the end of the row of the key.

When downloading a secret key, you need to specify the key passphrase twice.

</td>
</tr>
<tr>
<td valign="top">

Delete

</td>
<td valign="top">

To delete a dedicated key, click the delete button \(:wastebasket:\) at the end of the row of the key.

> ### Caution:  
> This information is only relevant for Edge Integration Cell runtime.
> 
> When you delete a key, it affects all the runtime nodes where that key has been assigned. This means that after deletion, the key is no longer present on any of these nodes.



</td>
</tr>
<tr>
<td valign="top">

Search

</td>
<td valign="top">

To search for a key, start typing the user id or key id of a dedicated key in the search field above the table.

</td>
</tr>
</table>

**Related Information**  


[Manage Security](manage-security-6e7c44c.md "The Manage Security section allows you to manage various kinds of security material (for example, user credentials, keystore entries), and to perform outbound connectivity tests.")

[Define PGP Encryptor](define-pgp-encryptor-7a07766.md "")

[Define PGP Decryptor](define-pgp-decryptor-d0dc511.md "")

