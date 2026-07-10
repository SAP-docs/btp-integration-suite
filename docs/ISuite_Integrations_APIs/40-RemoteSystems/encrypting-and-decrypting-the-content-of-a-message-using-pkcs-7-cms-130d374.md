<!-- loio130d3742193244a69c8e77ab04120d7f -->

# Encrypting and Decrypting the Content of a Message Using PKCS\#7/CMS

Encode the content of a message in such a way that only authorized parties can read it.



Digital encryption using PKCS\#7/CMS works two-stage based on symmetric and asymmetric key technology:

1.  The sender encrypts the content of the message using a symmetric key.

    > ### Note:  
    > The following algorithms for content encryption \(by the symmetric key\) are supported \(format Cipher/Operation Mode/Padding Scheme\): DESede/CBC/PKCS5Padding, DES/CBC/PKCS5Padding, AES/CBC/PKCS5Padding, ARCFOUR/ECB/NoPadding, Camellia/CBC/PKCS5Padding, RC2/CBC/PKCS5Padding, CAST5/CBC/PKCS5Padding.

2.  The sender encrypts the symmetric key using a public key.

    > ### Note:  
    > To encrypt the symmetric key, a public key of type RSA \(with the cipher – or algorithm – RSA/ECB/PKCS1Padding\) is used for each recipient.

3.  The sender sends the encrypted message and the encrypted symmetric key to the receiver.
4.  The receiver decrypts the symmetric key using a private key \(which is related to the public key used by the sender\).

    > ### Note:  
    > For this decryption step, you need a private key of type RSA.

5.  The receiver decrypts the content of the message using the decrypted symmetric key.

> ### Note:  
> Strong encryption is supported for the following algorithms:
> 
> -   AES/CBC/PKCS5Padding
> -   Camellia/CBC/PKCS5Padding
> 
> For these algorithms also the key lengths 192 and 256 are possible.

The following figure illustrates the process of digitally encrypting and decrypting the content of a message.

![Digitally Encrypting Message Content](images/Digitally_Encrypting_Message_Content_b535cfe.png)

