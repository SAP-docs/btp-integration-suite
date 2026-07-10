<!-- loio6c5846bbe10a4d258507443108f68301 -->

# Creating OpenPGP Keys

You use the tool gpg4win to create the required keys for the usage of OpenPGP.

This section covers the creation of OpenPGP keys for tenants managed by SAP.

This description does not apply to tenants managed by customers. Customers might have their own OpenPGP key management processes.

The OpenPGP keys are maintained on the Windows VM on which the keys of the X.509 certificates are also maintained.

The kind of keys required depends on the use case and the role of the tenant for which the keys are created.

The following table lists the possible use cases and the required kinds of keys.

> ### Note:  
> As soon as you start gpg4win, files are created for the PGP Public Keyring and PGP Secret Keyring.

**OpenPGP Keys for the Tenant**


<table>
<tr>
<th valign="top">

Role of Tenant

</th>
<th valign="top">

Chosen Kind of Message Protection

</th>
<th valign="top">

Required Keys

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

Sender

\(outbound communication\)

</td>
<td valign="top">

Encrypts outbound payload

</td>
<td valign="top">

**PGP Public Keyring** \(contains **receiver's** public key to encrypt payload\)

</td>
</tr>
<tr>
<td valign="top">

Encrypts and signs outbound payload

</td>
<td valign="top">

**PGP Public Keyring** \(contains **receiver's** public key to encrypt payload\)

**PGP Secret Keyring** \(contains **tenant's** secret key to sign payload\)

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Receiver

\(inbound communication\)

</td>
<td valign="top">

Decrypts inbound payload

</td>
<td valign="top">

**PGP Secret Keyring** \(contains **tenant's** secret key to decrypt payload\)

</td>
</tr>
<tr>
<td valign="top">

Decrypts and verifies inbound payload

</td>
<td valign="top">

**PGP Secret Keyring** \(contains **tenant's** secret key to decrypt payload\)

**PGP Public Keyring** \(contains the **sender's** public key to verify payload\) for verifying

</td>
</tr>
</table>

**Related Information**  


[How OpenPGP Works](how-openpgp-works-29bc188.md "You can use Open Pretty Good Privacy (Open PGP) to digitally sign and encrypt messages.")

[Creating PGP Keys for Encryption \(Tenant Is Sender\)](creating-pgp-keys-for-encryption-tenant-is-sender-b97e269.md "")

[Creating PGP Keys for Encryption and Signing \(Tenant Is Sender\)](creating-pgp-keys-for-encryption-and-signing-tenant-is-sender-a05a142.md "")

[Creating PGP Keys for Decryption \(Tenant Is Receiver\)](creating-pgp-keys-for-decryption-tenant-is-receiver-b69f6c6.md "")

[Creating PGP Keys for Decryption and Verifying \(Tenant Is Receiver\)](creating-pgp-keys-for-decryption-and-verifying-tenant-is-receiver-f80c999.md "")

[Securely Exchanging Key Material](securely-exchanging-key-material-908d93e.md "In many cases, communication partners need to exchange public keys in order to establish a secure connection.")

