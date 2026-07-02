<!-- loio29bc18899366482089eaa51985732450 -->

# How OpenPGP Works

You can use Open Pretty Good Privacy \(Open PGP\) to digitally sign and encrypt messages.

OpenPGP gives you the following options to protect communication at message level:

-   You can encrypt a payload.
-   You can sign and encrypt a payload.

OpenPGP does not support signing without encryption or just verifying without decryption. The tenant expects either an encrypted payload or a signed and encrypted payload.

During runtime, the encryptor/signer processor signs and encrypts the body of the inbound message and returns the resulting OpenPGP message in the body of the outbound message.

The required keys are stored in OpenPGP keyrings. The following types of keyrings exist:

**PGP Keyrings**


<table>
<tr>
<th valign="top">

Type of Keyring

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

PGP secret keyring

</td>
<td valign="top">

Contains the public/private key pairs of the sender. It can contain multiple key pairs, each identified by a user ID.

The private key is protected with a passphrase. For PGP secret keyrings deployed on tenants, the same passphrase has to be used to access all private keys of the PGP secret keyring.

</td>
</tr>
<tr>
<td valign="top">

PGP public keyring

</td>
<td valign="top">

Contains the public keys \(related to the private keys that are stored in the PGP secret keyring of the communication partner\).

</td>
</tr>
</table>



## OpenPGP Signing/Verifying

A digital signature ensures the authenticity of a message by guaranteeing the identity of the signer and that the message has not been altered since signing.

A message is digitally signed and verified as follows:

1.  The sender calculates a digest \(or hash value\) from the message content using a digest algorithm.

    The following hash algorithms are supported for PGP signing:

    -   For DSA key: SHA-1, SHA224, SHA256, SHA384, SHA512
    -   For RSA key: MD5, SHA-1, RIPE-MD/160, SH256, SHA384, SHA512, SHA224

2.  The sender encrypts the digest using a private key \(type RSA or DSA\). This is the actual signing step.

    The private key is looked up in the sender's PGP secret keyring.

3.  The encrypted hash value, together with the hash algorithm that has been used, is written to the signature element that is sent to the receiver together with the payload \(as PGP signature format\). The key ID of the signer of the private key is also written to the PGP signature format.
4.  The receiver obtains the PGP signature format.
5.  The receiver selects the key ID from the signature and uses the key ID to look up the right public key in the receiver's PGP public keyring. This is the public key that corresponds to the private key used to sign the payload.

    In addition, the receiver checks whether the user ID \(associated with the key ID\) corresponds to an allowed user.

6.  The receiver decrypts the hash value \(and verifies the payload\) using the public key.

The following figure illustrates the concept.

![](images/PGP_Signing_439f2f9.png)



## OpenPGP Encrypting/Decrypting

Digital encryption allows you to encode the content of a message in such a way that only authorized parties can read it.

A message is digitally encrypted and decrypted as follows:

1.  The sender generates a symmetric key.
2.  The sender encrypts the payload with the symmetric key.

    The following symmetric key algorithms for content encryption \(symmetric key algorithms\) are supported:

    TripleDES \(168bit key derived from 192\), CAST5 \(128 bit key, as per \[RFC2144\]\), Blowfish \(128 bit key, 16 rounds\), AES with 128, 192, and 256-bit key, Twofish with 256-bit key

    DES is not supported.

3.  The sender looks up a public PGP key in the PGP public keyring.
4.  The sender encrypts the symmetric key using the public PGP key \(from the PGP public keyring\).

    You can use the following key types to encrypt the symmetric key: RSA and Elgamal \(DAS is not supported\).

5.  The sender writes the encrypted symmetric key and the key ID into the Encryption Info element of the message.

    The key ID is used to identify the public key used for encryption \(as the PGP public keyring can contain more than one public key\).

    The Encryption Info element is sent to the receiver, together with the encrypted payload.

6.  The receiver obtains the message and, based on the key ID \(in the Encryption Info element\), looks up the correct private key \(associated with the public key used to encrypt the payload\) in the PGP secret keyring.

    A passphrase is required to access the private key.

7.  The receiver decrypts the symmetric key with the private key from the PGP secret keyring.
8.  The receiver decrypts the payload with the symmetric key.

There is an option to compress data before the encryption step. The following compression algorithms are supported: ZIP \[RFC1951\], ZLIB \[RFC1950\], BZip2.

The following figure illustrates the concept.

![](images/PGP_Encryption_36d114a.png)



The runtime supports the following features:

-   Signing with several private keys \(the resulting OpenPGP message then contains several signatures\).
-   Encryption with several public keys.

    More precisely, the symmetric encryption key can be encrypted by several public keys \(the resulting OpenPGP message then contains several *Public Key Encrypted Session Key* packets\).

-   Optional: OpenPGP compression and base 64 output or input.
-   OpenPGP allows you to apply two different kinds of keys: primary keys and subkeys. \(For simplicity, these are not differentiated in the figures above.\)

    When you generate OpenPGP keys, a primary key with at least one subkey is created. Only the primary key can be used for certification, that is, to certify the trustworthiness of other keys. In addition, the primary key is also typically used to sign payloads. The subkey is used to encrypt payloads.




## OpenPGP Message Format Specification

The OpenPGP message format is specified at [http://tools.ietf.org/html/rfc4880](http://tools.ietf.org/html/rfc4880). An OpenPGP message is composed of a sequence of packets. The following table contains the most important packet types.

**OpenPGP Message Format - Packets**


<table>
<tr>
<th valign="top">

Packet Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Public Key Encrypted Session Key

</td>
<td valign="top">

Session key encrypted with a public key, key ID of the public key, and public-key algorithm

</td>
</tr>
<tr>
<td valign="top">

Signature

</td>
<td valign="top">

Binding between a public key and some data.

There are several types of signature packets:

The certification, direct key, and subkey binding signature can be self-signed. The version 4 signature packet may also contain meta-information about the signature such as creation time, issuer, or key expiration time. The version 3 signature is deprecated.

</td>
</tr>
<tr>
<td valign="top">

Symmetric Key Encrypted Session Key

</td>
<td valign="top">

A symmetric key \(also called session key\) encrypted with a symmetric key; a symmetric algorithm is used. This packet is not supported.

</td>
</tr>
<tr>
<td valign="top">

One-Pass Signature

</td>
<td valign="top">

Placed at the beginning of the message before the data. It contains sufficient information to allow the system to start calculating the signature before the actual signature packet \(which is after the data\) is reached. There can be several such packets. One packet contains the public key algorithm, the hashing algorithm, the key ID of the signing key, and an indicator whether the signatures should be nested or not. A zero value indicates that the next packet is another One-Pass Signature packet that describes another signature to be applied to the same message data.

> ### Note:  
> Nested signatures are not supported. However, several signatures over the same data in one PGP message are supported.



</td>
</tr>
<tr>
<td valign="top">

Public Key

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Public Subkey

</td>
<td valign="top">

Contains similar information to a public key package, but it denotes a subkey.

</td>
</tr>
<tr>
<td valign="top">

Secret Key

</td>
<td valign="top">

Contains all the information that is found in a public key packet, but also includes the secret key \(encrypted private key\).

</td>
</tr>
<tr>
<td valign="top">

Secret Subkey

</td>
<td valign="top">

Contains similar information to a secret key package, but it denotes a subkey.

</td>
</tr>
<tr>
<td valign="top">

Compressed Data

</td>
<td valign="top">

Typically, this packet contains the contents of an encrypted packet, or follows a Signature or One-Pass Signature packet, and it contains a literal data packet.

</td>
</tr>
<tr>
<td valign="top">

Symmetrically Encrypted Data

</td>
<td valign="top">

Data encrypted with a symmetric key \(using a symmetric key algorithm\). The symmetric cipher used may be specified in a Public-Key or Symmetric-Key Encrypted Session Key packet that precedes the Symmetrically Encrypted Data packet. This packet uses a variant of the cipher feedback mode \(CFB\) \(as defined at [http://tools.ietf.org/html/rfc4880](http://tools.ietf.org/html/rfc4880)\).

</td>
</tr>
<tr>
<td valign="top">

Literal Data

</td>
<td valign="top">

Contains plain data \(binary or text\).

</td>
</tr>
<tr>
<td valign="top">

User ID

</td>
<td valign="top">

Indicates the holder of a key. The package contains the user name, e-mail address, and comment of the keyholder.

</td>
</tr>
<tr>
<td valign="top">

User Attribute

</td>
<td valign="top">

Variant of the User ID packet, which can contain more information about the user. It is only used together with key material. This packet is not supported.

</td>
</tr>
<tr>
<td valign="top">

Sym. Encrypted and Integrity Protected Data

</td>
<td valign="top">

Variant of the Symmetrically Encrypted Data packet. It contains data that is encrypted with a symmetric key algorithm \(using a symmetric key algorithm\) and is protected against modification by the SHA-1 hash algorithm \(less strong than a signature, but stronger than bare CFB encryption\). It does not use Open PGP CFB mode but pure CFB mode.

</td>
</tr>
</table>



## Restrictions for the Input Message Structure \(for Decryptor/Verifier\)

The input payload must have the following packet sequence:

**Public Key Encrypted Session Key ..., Sym. Encrypted and Integrity Protected Data | Sym. Encrypted Data, \(Compressed Data,\) \(One Pass Signature ...,\) Literal Data, \(Signature ...,\)**

Entries in brackets are optional, ellipses indicate repetition, commas represent sequential composition, and '|' separates alternatives.

For example, the Compressed Data packet is optional.



## Restrictions for the Output Message Structure \(for Encryptor/Signer\)

The output PGP message is restricted to the following packet sequence:

**Public Key Encrypted Session Key ..., Sym. Encrypted and Integrity Protected Data | Sym. Encrypted Data, Compressed Data, \(One Pass Signature ...,\) Literal Data, \(Signature ...,\)** 

Entries in brackets are optional, ellipses indicate repetition, commas represent sequential composition, and '|' separates alternatives.

This does mean the following:

-   A symmetric key cannot be encrypted with another symmetric key.

    The symmetric key that encrypts the payload cannot be encrypted by another symmetric key \(which is, for example, generated from a password\). OpenPGP allows this \(see Symmetric Key Encrypted Session Key packet\).

-   Compression cannot be switched off. The Compressed Data packet is always mandatory.

-   Encryption is always mandatory. It is not possible to only sign data.

-   Only one password for all private keys in the keyring can be used. This simplifies password maintenance.

-   Nested signatures are not supported: If there are multiple signatures in the PGP message, they all contain the same hash value built over the original payload. OpenPGP does allow nested signatures where the enclosing signature is a signature of the enclosed PGP message including the enclosed signatures.

-   DSA keys can only be combined with certain hash algorithms.


