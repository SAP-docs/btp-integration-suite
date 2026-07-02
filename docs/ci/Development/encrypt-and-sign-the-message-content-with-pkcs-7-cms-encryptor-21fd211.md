<!-- loio21fd21135941432fbade76e67b9e7194 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Encrypt and Sign the Message Content with PKCS\#7/CMS Encryptor



<a name="loio21fd21135941432fbade76e67b9e7194__context_N10014_N10011_N10001"/>

## Context

You perform this task to protect the message content from being altered while it is being sent to other participants on the cloud, by encrypting the content. In the integration flow model, you configure the *Encryptor* by providing information on the public key alias, content encryption algorithm, and secret key length. The encryptor uses one or more receiver public key aliases to find the public key in the keystore. The encryption process uses a symmetric key of specified length for content encryption. The symmetric key is encrypted by the public recipient key with the cipher. The encryption is determined by the type of *Content Encryption Algorithm* that you select. The encrypted content and the receiver information containing the symmetric encryption key are placed in the message body.

In addition to encrypting the message content, you can also sign the content to make your identity known to the participants and thus ensure the authenticity of the messages you are sending. This task guarantees your identity by signing the messages with one or more private keys using a signature algorithm.



## Procedure

1.  In the palette, choose :lock: , then *Encryptor* \> *PKCS7 Encryptor*.

2.  Place *PKCS7 Encryptor* in the integration process and define the message path.

3.  Define the following parameters in the *General* tab.


    <table>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    Enter a name for the encryptor.
    
    </td>
    </tr>
    </table>
    
4.  Define the following parameters for encryption in the *Processing* tab.


    <table>
    <tr>
    <td valign="top">
    
    *Block Size \(in bytes\)* 
    
    </td>
    <td valign="top">
    
    Enter the size of the data that is to be encoded.

    If you enter a value equal to or less than `0`, the whole data is encoded.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Encode Body with Base64* 
    
    </td>
    <td valign="top">
    
    Select this option if the message body will be base64-encoded.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signatures* 
    
    </td>
    <td valign="top">
    
    Select one of the following options:

    -   *Enveloped Data Only*

        Select this option if you want to apply encryption only.

    -   *Signed and Enveloped Data*

        Select this option if you want to apply both encryption and signing.



    
    </td>
    </tr>
    </table>
    
5.  Define the parameters for the encryption process.


    <table>
    <tr>
    <td valign="top">
    
    *Content Encryption Algorithm* 
    
    </td>
    <td valign="top">
    
    Specify the algorithm that is to be used to encrypt the payload.

    Supported algorithms \(by the symmetric key\) for content encryption \(format Cipher/Operation Mode/Padding Scheme\): AES/GCM/NoPadding, AES/CCM/NoPadding, AES/CBC/PKCS5Padding, ARCFOUR/ECB/NoPadding, Camellia/CBC/PKCS5Padding, CAST5/CBC/PKCS5Padding, DES/CBC/PKCS5Padding, DESede/CBC/PKCS5Padding, RC2/CBC/PKCS5Padding.

    The following options are available when for *Signatures* the option *Enveloped Data Only* is selected: AES/GCM/NoPadding, AES/CCM/NoPadding,AES/CCM/NoPadding, AES/GCM/NoPadding.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Secret Key Length* 
    
    </td>
    <td valign="top">
    
    Specify the key length.

    The offered key lengths depend on the chosen encryption algorithm.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Receiver Public Key Alias* 
    
    </td>
    <td valign="top">
    
    Specify one or more aliases.

    Enter an alias to select the public key from the keystore. You can enter `${header.headername}` or `${property.propertyname}` to read the name dynamically from a header or exchange property.
    
    </td>
    </tr>
    </table>
    
6.  Define the parameters for the signing process \(only if you selected `Signed and Enveloped Data` for *Signatures*\).


    <table>
    <tr>
    <td valign="top">
    
    *Signer Parameters* 
    
    </td>
    <td valign="top">
    
    For each private key alias, define the following parameters:

    -   *Private Key Alias* 

        Enter an alias for selecting a private key from the keystore. You can enter `${header.headername}` or `${property.propertyname}` to read the name dynamically from a header or exchange property.

        > ### Note:  
        > Consider the security implications when deriving key aliases from header attributes as they might be influenced by inbound adapters or exported/published by outbound adapters. It is more secure to use \(exchange\) properties for this purpose.

    -   *Signature Algorithm*

        Specify the signature \(digest\) algorithm.

        Signature algorithms: AES/GCM/NoPadding, AES/CCM/NoPadding, MD5/RSA, RIPEMD128/RSA, RIPEMD160/RSA, RIPEMD256/RSA, SHA/RSA, SHA224/RSA, SHA256/RSA, SHA384/RSA, SHA512/RSA.

        > ### Caution:  
        > Algorithms starting with SHA1, MD2, or MD5 are still supported for compatibility reasons, but they no longer meet today's security requirements. Therefore, we recommend using stronger algorithms where possible. Check with your security experts or authorities like NIST for more detailed security recommendations.

    -   *Include Certificates*

        If you activate this option \(value `true`\), the certificate chain corresponding to the private key will be added to the SignedAndEnvelopedData element.



    
    </td>
    </tr>
    </table>
    
7.  Save the changes.


