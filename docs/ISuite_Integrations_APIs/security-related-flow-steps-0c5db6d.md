<!-- loio0c5db6d1ae2c47f8962906d4a1c4fe45 -->

# Security-Related Flow Steps

Security steps enable you to protect the confidentiality, integrity, and authenticity of messages processed by an API artifact. You can add these steps to the policy model of your API artifact to encrypt, decrypt, sign, or verify message content exchanged with participants on the cloud.



## Use

You use security steps in an API artifact to:

-   Encrypt outgoing messages to protect them from unauthorized access.
-   Decrypt incoming messages received from participants on the cloud.
-   Sign messages to ensure authenticity and data integrity.
-   Verify signed messages to confirm the sender’s identity and message integrity.



## Security


<table>
<tr>
<th valign="top">

Policy

</th>
<th valign="top">

Sub Category

</th>
<th valign="top">

Policy Definition

</th>
<th valign="top">

Runtime Support

</th>
<th valign="top">

Important Notes/Links

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

Decryptor

</td>
<td valign="top">

PGP Decryptor

</td>
<td valign="top">

Decrypts a message using OpenPGP standards.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define PGP Decryptor](define-pgp-decryptor-d0dc511.md).

</td>
</tr>
<tr>
<td valign="top">

PKCS7 Decryptor

</td>
<td valign="top">

Decrypts messages from a participant on the cloud.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, [Define PKCS\#7/CMS Decryptor](define-pkcs-7-cms-decryptor-51d903b.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Encryptor

</td>
<td valign="top">

PGP Encryptor

</td>
<td valign="top">

Encrypts or sign and encrypt the payload using OpenPGP standard.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define PGP Encryptor](define-pgp-encryptor-7a07766.md).

</td>
</tr>
<tr>
<td valign="top">

PKCS7 Encryptor

</td>
<td valign="top">

Protects the message content from being altered while it is being sent to other participants on the cloud, by encrypting the content.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Encrypt and Sign the Message Content with PKCS\#7/CMS Encryptor](encrypt-and-sign-the-message-content-with-pkcs-7-cms-encryptor-21fd211.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Signer

</td>
<td valign="top">

PKCS7 Signer

</td>
<td valign="top">

Use this step to make your identity known to the participants and thus ensure the authenticity of the messages you're sending on the cloud. This task guarantees your identity by signing the messages with one or more private keys using a signature algorithm.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Sign the Message Content with PKCS\#7/CMS Signer](sign-the-message-content-with-pkcs-7-cms-signer-cc09e03.md).

</td>
</tr>
<tr>
<td valign="top">

Simple Signer

</td>
<td valign="top">

Use this step to sign messages to ensure authenticity and data integrity when sending a message to participants on the cloud.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Sign the Message Content with Simple Signer](sign-the-message-content-with-simple-signer-9879fc3.md).

</td>
</tr>
<tr>
<td valign="top">

XML Digital Signer

</td>
<td valign="top">

Use this step to sign a message with an XML digital signature to ensure authenticity and data integrity while sending an XML resource to the participants on the cloud.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Sign the Message Content with XML Digital Signature](sign-the-message-content-with-xml-digital-signature-9a013db.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Verifier

</td>
<td valign="top">

PKCS7 Signature Verifier

</td>
<td valign="top">

Ensures that the signed message received over the cloud is authentic.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Verify the PKCS\#7/CMS Signature](verify-the-pkcs-7-cms-signature-f095dc6.md).

</td>
</tr>
<tr>
<td valign="top">

XML Signature Verifier

</td>
<td valign="top">

Validates the XML signature contained in the incoming message body and returns the content which was signed in the outgoing message body.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Verify the XML Digital Signature](verify-the-xml-digital-signature-090b932.md).

</td>
</tr>
</table>

