<!-- loio0c58bdc685fc45cda71bf4db328c7d2d -->

# Features that Support Message Level Security

With the following features you can configure security on message level. Note that applying these features depends strongly on your scenario.



<a name="loio0c58bdc685fc45cda71bf4db328c7d2d__section_dwp_vw2_ndc"/>

## Integration Flow Steps

**Protecting Messages**


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Encryptor

</td>
<td valign="top">

Encrypts the content of a message.

Supported standards:

-   PGP

    See: [Define PGP Encryptor](../define-pgp-encryptor-7a07766.md)

-   PKCS\#7/CMS Enveloped Data and Signed Data

    See: [Encrypt and Sign the Message Content with PKCS\#7/CMS Encryptor](../encrypt-and-sign-the-message-content-with-pkcs-7-cms-encryptor-21fd211.md)




</td>
</tr>
<tr>
<td valign="top">

Decryptor

</td>
<td valign="top">

Decrypts the content of a message.

Supported standards:

-   PGP

    See: [Define PGP Decryptor](../define-pgp-decryptor-d0dc511.md)

-   PKCS\#7/CMS Enveloped Data and Signed Data

    See: [Define PKCS\#7/CMS Decryptor](../define-pkcs-7-cms-decryptor-51d903b.md)




</td>
</tr>
<tr>
<td valign="top">

Signer

</td>
<td valign="top">

Signs a message.

Supported standards:

-   PKCS\#7/CMS Enveloped Data and Signed Data

    See: [Sign the Message Content with PKCS\#7/CMS Signer](../sign-the-message-content-with-pkcs-7-cms-signer-cc09e03.md)

-   XML Digital Signature

    See: [Sign the Message Content with XML Digital Signature](../sign-the-message-content-with-xml-digital-signature-9a013db.md)




</td>
</tr>
<tr>
<td valign="top">

Verifier

</td>
<td valign="top">

Verifies a message.

Supported standards:

-   PKCS\#7/CMS Enveloped Data and Signed Data

    See: [Verify the PKCS\#7/CMS Signature](../verify-the-pkcs-7-cms-signature-f095dc6.md)

-   XML Digital Signature

    See: [Verify the XML Digital Signature](../verify-the-xml-digital-signature-090b932.md)




</td>
</tr>
</table>



<a name="loio0c58bdc685fc45cda71bf4db328c7d2d__section_r5d_xw2_ndc"/>

## Additional Features

**Protecting Messages**


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

SOAP 1.x sender adapter

</td>
<td valign="top">

Verifying and decrypting a payload \(received from a sender\)

Supported standards:

PKCS\#7/CMS Enveloped Data and Signed Data

See: [WS-Security Configuration for the Sender SOAP 1.x Adapter](../ws-security-configuration-for-the-sender-soap-1-x-adapter-e53bb5c.md)

</td>
</tr>
<tr>
<td valign="top">

SOAP 1.x receiver adapter

</td>
<td valign="top">

Signing and encrypting a payload \(sent to a receiver\)

Supported standards:

PKCS\#7/CMS Enveloped Data and Signed Data

See: [WS-Security Configuration for the Receiver SOAP 1.x Adapter](../ws-security-configuration-for-the-receiver-soap-1-x-adapter-e9f42bf.md)

</td>
</tr>
</table>

