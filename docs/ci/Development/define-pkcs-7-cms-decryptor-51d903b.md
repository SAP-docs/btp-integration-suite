<!-- loio51d903b94b9e42efbe4e658c8f7b4531 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define PKCS\#7/CMS Decryptor



## Context

You use the PKCS\#7 decryptor to decrypt messages from a participant on the cloud. You can also verify the authenticity of a signed message by verifying the signature of `SignedAndEnvelopedData` object.

To decrypt a message, the decryptor requires a private key that must be deployed on the tenant \(as part of a key pair\). Note that the tenant keystore can contain multiple key pairs. To make sure that the right private key is used for decryption, the encrypted message \(processed by the decryptor\) contains a reference that enables the system to uniquely identify the right private key. In particular, for the PKCS\#7/CMS decryptor, the message contains an issuer distinguished name and an issuer-specific serial number that uniquely identify the certificate for the corresponding public key.



## Procedure

1.  In the palette, choose :lock:, then *Decryptor* \> *PKCS\#7 Decryptor*.

2.  Place *PKCS\#7 Decryptor* in integration process and define the message path.

3.  Enter the following parameter in the *General* tab.


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
    
    Enter a name for the decryptor.
    
    </td>
    </tr>
    </table>
    
4.  Enter the following parameters in the *Processing* tab.


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
    
    *Body is Base64 Encoded*
    
    </td>
    <td valign="top">
    
    Select if you expect the body of payload to be `Base64` encoded.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signatures*
    
    </td>
    <td valign="top">
    
    Select option based on the following description:

    -   *Signed and Enveloped Data*: Select if you want decryptor to process payloads that are signed and encrypted.
    -   *Enveloped or "Signed and Enveloped" Data*: Select if you want decryptor to process both encrypted payloads and, encrypted and signed payloads.
    -   *Enveloped Data Only*: Select if you want decryptor to process only encrypted payloads.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Public Key Alias*

    \(only if you have selected *Signed and Enveloped Data* or *Enveloped or Signed and Enveloped Data* for *Signatures*\)
    
    </td>
    <td valign="top">
    
    Choose *Add* to enter the public key alias of the expected senders.

    You can enter `${header.headername}` or `${property.propertyname}` to read the name dynamically from a header or exchange property.

    > ### Note:  
    > -   You can add multiple aliases of all the expected senders.
    > 
    > -   Consider the security implications when deriving key aliases from header attributes as they might be influenced by inbound adapters or exported/published by outbound adapters. It is more secure to use \(exchange\) properties for this purpose.


    
    </td>
    </tr>
    </table>
    
5.  Save or deploy the configuration.


