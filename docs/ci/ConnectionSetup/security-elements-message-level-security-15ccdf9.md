<!-- loio15ccdf99016049ba85bcf75aab9ce6fa -->

# Security Elements \(Message-Level Security\)

The configuration of secure message exchange requires the exchange of public keys \(or other security-related information\) between the involved parties. Each message-level security option requires a specific set of keys to be exchanged.

The following tables provide a summary of how the required security elements \(in **bold letters**\) have to be distributed among the involved components \(tenant and sender/receiver systems\).

**Message-Level Security**


<table>
<tr>
<th valign="top">

Security Option/Standard



</th>
<th valign="top">

Direction



</th>
<th valign="top">

Protection Method on Tenant



</th>
<th valign="top">

Required by tenant administrator …



</th>
<th valign="top">

… to do the following



</th>
<th valign="top">

Required by sender/receiver administrator …



</th>
<th valign="top">

… to do the following



</th>
</tr>
<tr>
<td valign="top" rowspan="4">

PKCS\#7, WS-Security, XML Digital Signature \(uses X.509 certificates\)

XML Digital Signature: only sign/encrypt



</td>
<td valign="top" rowspan="2">

Inbound \(sender calls tenant\)



</td>
<td valign="top">

Decrypt



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

**Tenant public key certificate** \(to be provided by tenant administrator\)

Is used to encrypt the message from the sender \(that is to be encrypted by the tenant\).



</td>
<td valign="top">

Import into sender keystore



</td>
</tr>
<tr>
<td valign="top">

Verify



</td>
<td valign="top">

**Sender public key certificate** \(to be provided by sender administrator\)

Is used by the tenant to verify the signature of the message sent from the sender system.



</td>
<td valign="top">

Import into tenant keystore.



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Outbound \(tenant calls receiver\)



</td>
<td valign="top">

Encrypt



</td>
<td valign="top">

**Receiver public key certificate** \(to be provided by receiver administrator\)

Is used by the tenant to encrypt the message \(sent to the receiver\).



</td>
<td valign="top">

Import into tenant keystore.



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Sign



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

**Tenant public key certificate** \(to be provided by tenant administrator\)

Is used by the receiver to verify the message sent from the tenant.



</td>
<td valign="top">

Import into receiver keystore



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

OpenPGP \(uses PGP keys\)



</td>
<td valign="top" rowspan="2">

Inbound \(sender calls tenant\)



</td>
<td valign="top">

Decrypt



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

**Tenant public key** \(to be provided by tenant administrator\)

Is used to encrypt the message from the sender \(that is to be encrypted by the tenant\).

To make sure that the public key originates from the correct source and that it has not been changed on its way, consider the note below this table.



</td>
<td valign="top">

Import into sender PGP public keyring



</td>
</tr>
<tr>
<td valign="top">

Verify



</td>
<td valign="top">

**Sender public key** \(to be provided by sender administrator\)

Is used by the tenant to verify the signature of the message sent from the sender system.

To make sure that the public key originates from the correct source and that it has not been changed on its way, consider the note below this table.



</td>
<td valign="top">

Import into tenant PGP public keyring.



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Outbound \(tenant calls receiver\)



</td>
<td valign="top">

Encrypt



</td>
<td valign="top">

**Receiver public key** \(to be provided by receiver administrator\)

Is used by the tenant to encrypt the message \(sent to the receiver\).

To make sure that the public key originates from the correct source and that it has not been changed on its way, consider the note below this table.



</td>
<td valign="top">

Import into tenant PGP public keyring.



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Sign



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

**Tenant public key** \(to be provided by tenant administrator\)

Is used by the receiver to verify the message sent from the tenant.

To make sure that the public key originates from the correct source and that it has not been changed on its way, consider the note below this table.



</td>
<td valign="top">

Import into receiver PGP public keyring



</td>
</tr>
</table>

> ### Note:  
> Relevant for the SAP-managed operating model: When **exchanging public PGP keys**, note the following:
> 
> To ensure that the information originates from the correct source and that it has not been changed on its way, the key should be exchanged using a secure channel \(for example, encrypted e-mail\).
> 
> If a secure channel is not available, the person who receives the public key from the key owner has to **verify the fingerprint** of the public key. One option is to phone the owner of the public key and compare the fingerprint.

