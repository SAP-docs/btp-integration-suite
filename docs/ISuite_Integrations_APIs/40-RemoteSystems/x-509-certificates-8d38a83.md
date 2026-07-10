<!-- loio8d38a831d13144dda2096a09cc0a833b -->

# X.509 Certificates

X.509 certificates \(that comply with the X.509 standard\) are used for transport-level security TLS and for message-level security using PKCS\#7, WS-Security, and XML Digital Signature.



<a name="loio8d38a831d13144dda2096a09cc0a833b__section_pkj_wr1_yz"/>

## Elements of X.509 Certificates

This topic does not explain the standard in detail, but points out the following important elements of an X.509 certificate.

A digital certificate provides a public key that is signed by a certification authority \(CA\).

**Elements of X.509 Certificates**


<table>
<tr>
<th valign="top">

Element

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Issuer

</td>
<td valign="top">

Specifies the CA \(that issued and signed the certificate\).

</td>
</tr>
<tr>
<td valign="top">

Subject

</td>
<td valign="top">

Specifies the entity associated with the public key of the certificate.

</td>
</tr>
<tr>
<td valign="top">

Distinguished Name \(DN\)

</td>
<td valign="top">

Comprises the issuer, the subject, and other attributes.

A DN is a unique identifier of the certificate.

</td>
</tr>
</table>

When you specify a certificate, you have to define additional attributes such as a company name, a country or region identification, and so on.

**Related Information**  


[Keystore](keystore-b163513.md "Certificates and key pairs are stored in one keystore per tenant, referred to also as tenant keystore.")

[Requirements for Keystore Passwords](requirements-for-keystore-passwords-33469d3.md "To protect a keystore, you have to specify a password when creating the keystore.")

[Certificate Chains](certificate-chains-77a6094.md "The trust relationship between a client and a server using TLS authentication is usually based on chain certificates.")

