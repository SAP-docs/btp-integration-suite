<!-- loiocd478a7226304ad683c2df69cf6c2a48 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing PGP Keys

The PGP Keys monitor allows a tenant administrator to manage the public and private PGP keys.



<a name="loiocd478a7226304ad683c2df69cf6c2a48__section_ff5_dfq_5sb"/>

## Overview

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

-   Valid: The PGP key is valid.

-   Critical: The PGP key will expire within the next 14 days.

-   Expired: The PGP key is no longer valid.




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

*Add Public Key or Secret Keys*



</td>
<td valign="top">

To upload a secret or public keyring and replace the existing prior secret or public keyring, choose *Add*.



</td>
</tr>
<tr>
<td valign="top">

*Download*



</td>
<td valign="top">

To download an artifact, select the artifact in the table and choose *Download Public Keys or Secret Keys*.



</td>
</tr>
<tr>
<td valign="top">

*Delete*



</td>
<td valign="top">

To delete an artifact, go to *Monitor* \> *Managing Security Material* and choose *Delete* after the selecting the secret or public keyring in the table. See also: [Managing Security Material](managing-security-material-b8ccb53.md) 



</td>
</tr>
</table>

**Related Information**  


[Deploying a PGP Public Keyring](deploying-a-pgp-public-keyring-7f04458.md "This artifact contains the public key that enables the tenant to encrypt or verify messages using the Pretty Good Privacy (PGP) standard.")

[Deploying a PGP Secret Keyring](deploying-a-pgp-secret-keyring-9d8e1a9.md "This artifact contains the PGP Secret Keys for the usage of Open Pretty Good Privacy (PGP). The private key enables the tenant to decrypt or sign messages.")

[Managing Security](managing-security-6e7c44c.md "The Manage Security section allows you to manage various kinds of security material (for example, user credentials, keystore entries), and to perform outbound connectivity tests.")

[Define PGP Encryptor](define-pgp-encryptor-7a07766.md "")

[Define PGP Decryptor](define-pgp-decryptor-d0dc511.md "")

