<!-- loiobcff8523ff08469396674e51f4a688e2 -->

# Import/Back up a Keystore

Import/back up a keystore.



Perform the following call:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

POST

</td>
<td valign="top">

`/KeystoreResources` 

</td>
</tr>
</table>

In the request body, provide the following properties:

**Properties**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Possible Values

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

system

</td>
<td valign="top">

Key field name of the keystore

Currently, only `system` is allowed \(SAP supports only one keystore\).

</td>
</tr>
<tr>
<td valign="top">

Resource

</td>
<td valign="top">

<base64-encoded JKS or JCEKS keystore\>

</td>
<td valign="top">

Keystore in JKS or JCEKS format

</td>
</tr>
<tr>
<td valign="top">

password

</td>
<td valign="top">

password

</td>
<td valign="top">

Keystore password and password of all private keys in the keystore

> ### Caution:  
> All private keys must have the same password.



</td>
</tr>
</table>

> ### Note:  
> If the imported keystore contains entries that don't represent an X.509 certificate entry or a key-pair entry with a certificate chain of X.509 certificates, these entries are ignored during the import. The returned keystore entries don't contain an entry for these ignored original entries.

> ### Note:  
> Only if the custom query option `returnKeystoreEntries` was `true`, the response contains the `KeystoreEntry` instances of the merged keystore, as well as the nonimported and removed entries \(HTTP response code 200\). A returned `KeystoreEntry` instance contains information about whether the instance was newly created, updated, unchanged, not imported, or removed in the property status. If the entry wasn't imported, information on the reason for this behavior is also provided in the status property.

