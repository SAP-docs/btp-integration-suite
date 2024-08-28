<!-- loio7a07766899c84ed2bb38897e3a332032 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define PGP Encryptor



## Context

You use the PGP Encryptor to encrypt or sign and encrypt the payload using OpenPGP standard.



## Procedure

1.  In the palette, choose :lock:, then ** \> *Encryptor* \> *PGP Encryptor*.

2.  Place *PGP Encryptor* in integration process and define the message path.

3.  Define the following parameter in the *General* tab.


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    Enter a name for the encryptor.
    
    </td>
    </tr>
    </table>
    
4.  In the Processing tab,** provide values in the fields based on the following description.


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Signatures* 
    
    </td>
    <td valign="top">
    
    Select *Including* if you want to sign the payload with a signature.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Content Encryption Algorithm* 
    
    </td>
    <td valign="top">
    
    In the dropdown list, select the algorithm you want to use to encrypt the payload.

    Supported symmetric key algorithms for content encryption \(symmetric key algorithms\): AES with 128, 192, and 256-bit key, Blowfish \(128 bit key, 16 rounds\), CAST5 \(128 bit key, as per \[RFC2144\]\), DESede with 168-bit key, Twofish with 256-bit key. DES is not supported.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Secret Key Length* 
    
    </td>
    <td valign="top">
    
    Enter the secret key length.

    > ### Note:  
    > The length of the secret key depends on the encryption algorithm that you choose.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Compression Algorithm* 
    
    </td>
    <td valign="top">
    
    Select the algorithm you want to use to compress the payload.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Armored* 
    
    </td>
    <td valign="top">
    
    Select if you want the output to be radix 64 \(base64\) encoded with additional header.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Integrity Protected Data Packet* 
    
    </td>
    <td valign="top">
    
    Select if you want to create an Encrypted Integrity Protected Data Packet. This is a specific format where an additional hash value is calculated \(using SHA-1 algorithm\) and added to the message.

    This increases the message security level.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Encryption User ID of Key\(s\) from Public Keyring* 
    
    </td>
    <td valign="top">
    
    You can specify the encryption key user IDs \(or parts of them\). Based on this setting, the system picks all public keys associated with User IDs that contains this value from PGP public keyring. \(see [Outbound: Message-Level Security with OpenPGP](../40-RemoteSystems/outbound-message-level-security-with-openpgp-8641a15.md)\).

    You can enter `${header.headername}` or `${property.propertyname}` to read the encryption key user ID dynamically from a header or exchange property.

    > ### Note:  
    > Consider the security implications when deriving information from header attributes as it can be influenced by inbound adapters or exported/published by outbound adapters. It's more secure to use \(exchange\) properties for this purpose.
    > 
    > More information: [About Headers and Exchange Properties](about-headers-and-exchange-properties-0974c4f.md)

    You can specify multiple user IDs.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signature Algorithm*

    \(only if for *Signatures* the option *Including* has been selected\)
    
    </td>
    <td valign="top">
    
    Select the digest algorithm for the signature.

    The signature is created by transferring the message content into a digest \(hash value\) using a digest algorithm.

    Supported signature algorithms for PGP signing: MD5, RIPE-MD/160, SHA-1, SHA-224, SHA-256, SHA-384, SHA-512.

    Default value: SHA-512.

    > ### Caution:  
    > Algorithms starting with SHA1, MD2, or MD5 are still supported for compatibility reasons, but they no longer meet today's security requirements. Therefore, we recommend using stronger algorithms where possible. Check with your security experts or authorities like NIST for more detailed security recommendations.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signer User ID of Key\(s\) from Secret Keyring*

    \(only if for *Signatures* the option *Including* has been selected\)
    
    </td>
    <td valign="top">
    
    You can specify the signer user IDs \(or parts of them\). Based on this setting, the system picks all private keys associated with User IDs that contains this value from PGP secret keyring. All matching private keys will be used to sign the message \(may yield multiple signatures\). \(see [Outbound: Message-Level Security with OpenPGP](../40-RemoteSystems/outbound-message-level-security-with-openpgp-8641a15.md)\).

    You can enter `${header.headername}` or `${property.propertyname}` to read the Signer User ID dynamically from a header or exchange property.

    > ### Note:  
    > Consider the security implications when deriving information from header attributes as it can be influenced by inbound adapters or exported/published by outbound adapters. It's more secure to use \(exchange\) properties for this purpose.
    > 
    > More information: [About Headers and Exchange Properties](about-headers-and-exchange-properties-0974c4f.md)

    You can specify multiple user IDs.
    
    </td>
    </tr>
    </table>
    
5.  Save or deploy the configuration.




## Example

Assume that you like to send an encrypted and signed message to multiple receivers. The receiver is determined based on some value in the inbound message, for example, a customer number. Furthermore, the message is to be encrypted and signed by receiver-specific keys. To implement such a scenario, you can store the customer number as a property and use this property to dynamically define the encryption key user IDs and the signer user IDs.

**Related Information**  


[How OpenPGP Works](../40-RemoteSystems/how-openpgp-works-29bc188.md "You can use Open Pretty Good Privacy (Open PGP) to digitally sign and encrypt messages.")

[Deploying a PGP Public Keyring](deploying-a-pgp-public-keyring-7f04458.md "This artifact contains the public key that enables the tenant to encrypt or verify messages using the Pretty Good Privacy (PGP) standard.")

[Deploying a PGP Secret Keyring](deploying-a-pgp-secret-keyring-9d8e1a9.md "This artifact contains the PGP secret keys for the usage of Open Pretty Good Privacy (PGP). The private key enables the tenant to decrypt or sign messages.")

[Outbound: Message-Level Security with OpenPGP](../40-RemoteSystems/outbound-message-level-security-with-openpgp-8641a15.md "")

