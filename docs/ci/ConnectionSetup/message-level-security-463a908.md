<!-- loio463a9085156d4672bc4ee9095277e453 -->

# Message-Level Security

Several standards are supported to protect the message content \(message-level security\).

Message-level security features allow you to digitally encrypt/decrypt or sign/verify a message \(or both\). The following standards and algorithms are supported.

**Message-Level Security Options**


<table>
<tr>
<th valign="top">

Security Standard

</th>
<th valign="top">

Security Feature

</th>
<th valign="top">

Supported Algorithms

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

PKCS\#7/CMS Enveloped Data and Signed Data

PKCS\#7/CMS provides a syntax for data that has cryptography applied to it, such as digital signatures or digital encryption.

The CMS specification can be found at: [http://tools.ietf.org/html/rfc5652](http://tools.ietf.org/html/rfc5652)

Digitally signing a message is based on the CMS type Signed Data.

Digitally encrypting or decrypting the content of a message is based on the CMS type Enveloped Data.

</td>
<td valign="top">

Encryption/decryption of message content

</td>
<td valign="top">

Supported algorithms \(by the symmetric key\) for content encryption \(format Cipher/Operation Mode/Padding Scheme\): AES/GCM/NoPadding, AES/CCM/NoPadding, AES/CBC/PKCS5Padding, ARCFOUR/ECB/NoPadding, Camellia/CBC/PKCS5Padding, CAST5/CBC/PKCS5Padding, DES/CBC/PKCS5Padding, DESede/CBC/PKCS5Padding, RC2/CBC/PKCS5Padding.

</td>
</tr>
<tr>
<td valign="top">

Signing/verification of payload

</td>
<td valign="top">

Supported algorithms for content signing \(digest and encryption algorithm\): SHA3-224/RSA, SHA3-256/RSA, SHA3-384/RSA, SHA3-512/RSA, SHA512/RSA, SHA384/RSA, SHA256/RSA, SHA224/RSA, SHA/RSA, RIPEMD128/RSA, RIPEMD160/RSA, RIPEMD256/RSA, MD5/RSA, MD2/RSA, RIPEMD160andMGF1/RSA-ISO9796-2-2-3, SHAandMGF1/RSA-ISO9796-2-2-3, SHA3-512/DSA, SHA3-384/DSA, SHA3-256/DSA, SHA3-224/DSA, SHA512/DSA, SHA384/DSA, SHA256withDSA, SHA224withDSA, SHA/DSA, SHA3-224/ECDSA, SHA3-256/ECDSA, SHA3-384/ECDSA, SHA3-512/ECDSA, SHA512/ECDSA, SHA384/ECDSA, SHA256/ECDSA, SHA224/ECDSA, SHA1/ECDSA.

The generated signature conforms to the CAdES-BES \(CMS Advanced Electronic Signatures\) signature standard according to the ETSI TS 101 733 V1.7.4, 1.8.1, 1.8.3, 2.1.1. and 2.2.1 specifications published at: [https://www.etsi.org/deliver/etsi\_ts/101700\_101799/101733/02.02.01\_60/ts\_101733v020201p.pdf](https://www.etsi.org/deliver/etsi_ts/101700_101799/101733/02.02.01_60/ts_101733v020201p.pdf).

</td>
</tr>
<tr>
<td valign="top">

PKCS\#7/CMS Enveloped Data and Signed Data

</td>
<td valign="top">

Encryption/decryption and signing/verification of payload

</td>
<td valign="top">

Signature algorithms: AES/GCM/NoPadding, AES/CCM/NoPadding, MD5/RSA, RIPEMD128/RSA, RIPEMD160/RSA, RIPEMD256/RSA, SHA/RSA, SHA224/RSA, SHA256/RSA, SHA384/RSA, SHA512/RSA.

This is a subset of the algorithms that are supported for PKCS\#7/CMS Enveloped Data and Signed Data.

The generated signature **does not** conform to the CAdES-BES \(CMS Advanced Electronic Signatures\) signature standard.

</td>
</tr>
<tr>
<td valign="top">

Basic Digital Signature Option \(*Simple Signer*\)

</td>
<td valign="top">

Signing payload

</td>
<td valign="top">

Supported algorithms for content signing \(digest and encryption algorithm\): MD5/RSA, MD2/RSA, RIPEMD160andMGF1/RSA-ISO9796-2-2-3, RIPEMD128/RSA, RIPEMD160/RSA, RIPEMD256/RSA, SHA/RSA, SHA/DSA, SHA224/RSA, SHA256/RSA, SHA384/RSA, SHA512/RSA, SHAandMGF1/RSA-ISO9796-2-2-3, SHA256withDSA, SHA224withDSA, SHA3-224/RSA, SHA3-256/RSA, SHA3-384/RSA, SHA3-512/RSA, SHA3-512/DSA, SHA3-384/DSA, SHA3-256/DSA, SHA3-224/DSA, SHA512/DSA, SHA384/DSA, SHA3-224/ECDSA, SHA3-256/ECDSA, SHA3-384/ECDSA, SHA3-512/ECDSA, SHA512/ECDSA, SHA384/ECDSA, SHA256/ECDSA, SHA224/ECDSA, SHA1/ECDSA.

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Open Pretty Good Privacy \(PGP\)

</td>
<td valign="top">

Encryption/decryption of message content

</td>
<td valign="top">

Supported symmetric key algorithms for content encryption \(symmetric key algorithms\): AES with 128, 192, and 256-bit key, Blowfish \(128 bit key, 16 rounds\), CAST5 \(128 bit key, as per \[RFC2144\]\), DESede with 168-bit key, Twofish with 256-bit key. DES is not supported.

</td>
</tr>
<tr>
<td valign="top">

Encryption/decryption and signing/verification of the message

</td>
<td valign="top">

Supported signature algorithms for PGP signing: MD5, RIPE-MD/160, SHA-1, SHA-224, SHA-256, SHA-384, SHA-512.

</td>
</tr>
<tr>
<td valign="top">

XML Signature

</td>
<td valign="top">

Signing/verification of payload

</td>
<td valign="top">

Supported signature algorithms: SHA1/DSA, SHA1/RSA, SHA256/RSA, SHA384/RSA, SHA512/RSA, SHA224/ECDSA, SHA256/ECDSA, SHA384/ECDSA, SHA512/ECDSA.

</td>
</tr>
<tr>
<td valign="top">

XML Advanced Electronic Signature \(XAdES\)

Supported XAdES forms: XAdES Basic Electronic Signature and XAdES Explicit Policy based Electronic Signature

</td>
<td valign="top">

Signing payload

</td>
<td valign="top">

The same signature algorithms as for XML Signature are supported.

</td>
</tr>
<tr>
<td valign="top">

WS-Security

</td>
<td valign="top">

Signing/verification of SOAP body

Encryption/decryption of message content

</td>
<td valign="top">

The default signature algorithm is set by the data in the certificate, that is, one of the following: http://www.w3.org/2000/09/xmldsig\#rsa-sha1 or http://www.w3.org/2000/09/xmldsig\#dsa-sha1.

The default signature digest algorithm is: http://www.w3.org/2000/09/xmldsig\#sha1

</td>
</tr>
</table>

Strong encryption is supported for the following algorithms:

-   AES/CBC/PKCS5Padding
-   Camellia/CBC/PKCS5Padding

For these algorithms, the key lengths 192 and 256 are possible.

> ### Caution:  
> Algorithms starting with SHA1, MD2, or MD5 are still supported for compatibility reasons, but they no longer meet today's security requirements. Therefore, we recommend using stronger algorithms where possible. Check with your security experts or authorities like NIST for more detailed security recommendations.



## Recommendations

Some algorithms \(like MD2, MD5, DES or RC4\) are still supported for legacy reasons, but they are not considered secure any more. We recommend that you check the official recommendations from National Institute of Standards and Technology \(NIST\) or European Union Agency for Network and Information Security \(ENISA\) for advice on algorithms and key strengths \(for example, at: [https://www.enisa.europa.eu/activities/identity-and-trust/library/deliverables/algorithms-key-sizes-and-parameters-report](https://www.enisa.europa.eu/activities/identity-and-trust/library/deliverables/algorithms-key-sizes-and-parameters-report)\).

**Related Information**  


[How PKCS\#7 Works](how-pkcs-7-works-21325d5.md "You have the option to sign and encrypt message payloads based on PKCS#7/CMS Enveloped Data and Signed Data (PKCS stands for Public Key Cryptography Standards).")

[How XML Signature Works](how-xml-signature-works-9857d50.md "A digital signature ensures the authenticity of a message that way that it guarantees the identity of the signer and that the message was not altered after signing. You have the option to digitally sign and validate a message based on the XML Signature standard (issued by the W3C consortium). Applying this standard means that the digital signature of a document itself is stored as an XML element.")

[How WS-Security Works](how-ws-security-works-2f9a038.md "Messages can be protected according to the WS-Security standard.")

[How OpenPGP Works](how-openpgp-works-29bc188.md "You can use Open Pretty Good Privacy (Open PGP) to digitally sign and encrypt messages.")

