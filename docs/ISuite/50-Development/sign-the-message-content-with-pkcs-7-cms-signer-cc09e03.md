<!-- loiocc09e03e28984f609b1a05788e8c6129 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Sign the Message Content with PKCS\#7/CMS Signer



## Context

You work with the PKCS\#7/CMS signer to make your identity known to the participants and thus ensure the authenticity of the messages you're sending on the cloud. This task guarantees your identity by signing the messages with one or more private keys using a signature algorithm.

> ### Tip:  
> Fore more information on how signing and verifying works and about the technical concepts, check out [Signing and Verifying a Message Using PKCS\#7/CMS](../40-RemoteSystems/signing-and-verifying-a-message-using-pkcs-7-cms-bb76650.md).



## Procedure

1.  In the palette, choose :lock:, then *Signer* \> *PKCS7 Signer*.

2.  Place *PKCS7 Signer* in the integration process and define the message path.

3.  Define the following parameters in the *General* tab.


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
    
    Enter a name of the signer.
    
    </td>
    </tr>
    </table>
    
4.  Define the following parameter in the *Processing* tab to sign the incoming message with one or more signatures.

    **Parameters and Values of PKCS\#7/CMS Signer**


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
    
    *Block Size \(in bytes\)* 
    
    </td>
    <td valign="top">
    
    Enter the size of the data that is to be encoded.

    If you enter a value equal to or less than `0`, the whole data is encoded.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Include Content in Signed Data* 
    
    </td>
    <td valign="top">
    
    You can choose to include the original content that is to be signed in the `SignedData` element. This `SignedData` element is written to the message body.

    You also have the option to keep the original content in the message body and to include the signed data elsewhere: Up to version 1.2 of the PKCS\#7/CMS Signer you can choose to include the signed data in the *SapCmsSignedData* header. From version 1.3 of the PKCS\#7/CMS Signer onwards, you can include the signed data in the *SapCmsSignedData* property.

    See also [Options to Handle Signed Data](../40-RemoteSystems/options-to-handle-signed-data-89f4220.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *OID for Content Type*

    \(only available when *Include Content in Signed Data* is deselected\)
    
    </td>
    <td valign="top">
    
    Specify the object identifier \(OID\) for the content type.

    You have the following options to specify the OID:

    -   Select one of the predefined values.

        There are the following predefined values:

        -   `1.2.840.113549.1.7.1 (Data)`

        -   `1.2.840.113549.1.7.5 (Digested Data)`


    -   Overwrite the predefined value by entering another OID value in the *OID for Content Type* field.

    -   Overwrite the predefined value by entering a dynamic expression to have the system determine the OID value at runtime based on a header or property. To use this option, enter an expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Encode Signed Data with Base64* 
    
    </td>
    <td valign="top">
    
    You can also Base64-encode the signed data in either the message body or the message header, to further protect it during message exchange.

    > ### Note:  
    > When you Base64-encode the signed data, you encode either the message header or body, depending on where the signed data is placed. When verifying the message, make sure you specify which part of the message \(header or body\) was Base64-encoded.

    See also [Options to Handle Signed Data](../40-RemoteSystems/options-to-handle-signed-data-89f4220.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signer Parameters* 
    
    </td>
    <td valign="top">
    
    For each private key alias, define the following parameters:

    -   *Private Key Alias* 

        Enter an alias for selecting a private key from the keystore. You can enter `${header.headername}` or `${property.propertyname}` to read the name dynamically from a header or exchange property

        > ### Note:  
        > Consider the security implications when deriving key aliases from header attributes as they might be influenced by inbound adapters or exported/published by outbound adapters. It's more secure to use \(exchange\) properties for this purpose.

    -   *Signature Algorithm*

        Specify the signature \(digest\) algorithm.

        Supported algorithms for content signing \(digest and encryption algorithm\): SHA3-224/RSA, SHA3-256/RSA, SHA3-384/RSA, SHA3-512/RSA, SHA512/RSA, SHA384/RSA, SHA256/RSA, SHA224/RSA, SHA/RSA, RIPEMD128/RSA, RIPEMD160/RSA, RIPEMD256/RSA, MD5/RSA, MD2/RSA, RIPEMD160andMGF1/RSA-ISO9796-2-2-3, SHAandMGF1/RSA-ISO9796-2-2-3, SHA3-512/DSA, SHA3-384/DSA, SHA3-256/DSA, SHA3-224/DSA, SHA512/DSA, SHA384/DSA, SHA256withDSA, SHA224withDSA, SHA/DSA, SHA3-224/ECDSA, SHA3-256/ECDSA, SHA3-384/ECDSA, SHA3-512/ECDSA, SHA512/ECDSA, SHA384/ECDSA, SHA256/ECDSA, SHA224/ECDSA, SHA1/ECDSA.

    -   *Include Certificates*

        If you activate this option \(value `true`\), the certificate chain corresponding to the private key will be added to the SignedData element.

    -   *Include Signing Time*

        If you activate this option \(value `true`\), the signing time for the signed attributes will be added to the SignedData element.



    
    </td>
    </tr>
    </table>
    
5.  Save the changes.


