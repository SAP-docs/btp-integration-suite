<!-- loiobb7665045b844711a8e311cbb4a09f18 -->

# Signing and Verifying a Message Using PKCS\#7/CMS

A digital signature ensures the authenticity of a message that way that it guarantees the identity of the signer and that the message wasn't altered after signing.



<a name="loiobb7665045b844711a8e311cbb4a09f18__section_N10014_N10011_N10001"/>

## Process Overview

In simple terms, digitally signing and verifying a message works in the following way:

1.  The sender signs the message using its own private key.

2.  The receiver verifies the signature by using the public key associated with the sender's private key.


![](images/Signing_Message_PKCS7_Overview_b7e5b6f.png)

On a more technical level, the signing and verifying process based on the PKCS\#7/CMS standard works in the following way.

![Digitally Signing a Message](images/Digitally_Signing_a_Message_e3c7261.png)

> ### Note:  
> To support this use case, Cloud Integration comes with the following integration flow components: *PKCS7/CMS Signer* and *PKCS7 Signature Verifyer*.
> 
> When referring to *sender* and *receiver* in the context of Cloud Integration and the PKCS\#7/CMS-based signing and verifying process, we therefore mean more specifically:
> 
> -   The *PKCS7/CMS Signer* step \(processed by the sender component in the figure above\)
> 
> -   The *PKCS7 Signature Verifyer* step \(processed by the receiver component in the figure above\)



<a name="loiobb7665045b844711a8e311cbb4a09f18__section_bzq_z3m_1yb"/>

## Steps Performed by the Sender

At runtime, the sender performs the following steps:

1.  Calculates from the message content a digest \(also referred to as *hash value*\) using a digest algorithm.

    > ### Tip:  
    > A digest \(also referred to as *hash value*\) is an expression with a fixed size calculated from an input value \(which can be of any size\). Performing the same hash algorithm on the same data results in the same digest. However, the inverse operation isn’t possible: The input value can’t be reproduced out of the hash value.

2.  Encrypts the digest using a private key \(type RSA or DSA\). This is actually the signing step.

    Supported algorithms for content signing \(digest and encryption algorithm\): SHA3-224/RSA, SHA3-256/RSA, SHA3-384/RSA, SHA3-512/RSA, SHA512/RSA, SHA384/RSA, SHA256/RSA, SHA224/RSA, SHA/RSA, RIPEMD128/RSA, RIPEMD160/RSA, RIPEMD256/RSA, MD5/RSA, MD2/RSA, RIPEMD160andMGF1/RSA-ISO9796-2-2-3, SHAandMGF1/RSA-ISO9796-2-2-3, SHA3-512/DSA, SHA3-384/DSA, SHA3-256/DSA, SHA3-224/DSA, SHA512/DSA, SHA384/DSA, SHA256withDSA, SHA224withDSA, SHA/DSA, SHA3-224/ECDSA, SHA3-256/ECDSA, SHA3-384/ECDSA, SHA3-512/ECDSA, SHA512/ECDSA, SHA384/ECDSA, SHA256/ECDSA, SHA224/ECDSA, SHA1/ECDSA.

3.  Sends the encrypted digest \(which corresponds to the signature\) together with the message content to the receiver.




<a name="loiobb7665045b844711a8e311cbb4a09f18__section_hyg_1jm_1yb"/>

## Steps Performed by the Receiver

At runtime, the receiver performs the following steps:

1.  Retrieves the information required to verify the signature.

    In particular, the receiver retrieves the message content, the signature \(that means, the encrypted digest of the message content\), the digest algorithm, and the public key \(associated with the private key that was used to sign the data\). In more detail, the *PKCS7 Signature Verifyer* performs the following steps:

    > ### Note:  
    > There are different options how the sender transfers this information to the receiver \(in a format called *Signed Data*\).
    > 
    > See also: [Options to Handle Signed Data](options-to-handle-signed-data-89f4220.md)

    1.  Checks if the property `SapCmsSignedData` exits.

        If this property exists, the *PKCS7 Signature Verifyer* takes the property value as Signed Data object and assumes that the message body contains the content to be verified.

    2.  If the property `SapCmsSignedData` does not exist, the *PKCS7 Signature Verifyer* checks if the header `SapCmsSignedData` exists.

        If the header exists, the *PKCS7 Signature Verifyer* takes the header value as Signed Data object and assumes that the message body contains the content to be verified.

    3.  If the header does not exist, the *PKCS7 Signature Verifyer* assumes that the message body contains a Signed Data object which includes the content.


2.  Decrypts the digest with the public key \(which is related to the senders’ private key\). The public key has the type RSA or DSA.

3.  Calculates the digest out of the content of the message \(which has been sent to it by the sender\).

    The receiver uses the same digest algorithm that the sender had used.

    > ### Note:  
    > PKCS\#7 ensures that the digest algorithm is transferred together with the signature of the message and therefore available for the receiver.

    This calculation is based on the message content. In case the message content has been transferred encrypted, a decryption step is needed before this step.

4.  Compares the decrypted digest \(from the sender\) with the one calculated at receiver side. In case both values \(digests\) are identical, the signature is verified.

