<!-- loiof095dc6b9bb04530bbdaf037b250dd7f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Verify the PKCS\#7/CMS Signature

You perform this task to ensure that the signed message received over the cloud is authentic.



<a name="loiof095dc6b9bb04530bbdaf037b250dd7f__context_N10014_N10011_N10001"/>

## Context

In the integration flow model, you configure the *Verifier* by providing information about the public key alias, and whether the message header or body is Base64-encoded, depending on where the Signed Data is placed. For example, consider the following two cases:

-   If the Signed Data contains the original content, then in the Signature Verifier you retrieve the Signed Data from the message body.
-   If the Signed Data does not contain the original content, then in the Signature Verifier you retrieve the Signed Data from the header or property `SapCmsSignedData` and the original content in the message body.

For more details, see:

-   [Signing and Verifying a Message Using PKCS\#7/CMS](../40-RemoteSystems/signing-and-verifying-a-message-using-pkcs-7-cms-bb76650.md)

-   [Options to Handle Signed Data](../40-RemoteSystems/options-to-handle-signed-data-89f4220.md)


The Verifier uses the public key alias to obtain the public keys of type DSA or RSA that are used to decrypt the message digest. In this way the authenticity of the participant who signed the message is verified. If the verification is not successful, the Signature Verifier informs the user by raising an exception.

Under *Public Key Alias* you can enter one or multiple public key aliases for the Verifier.

> ### Note:  
> In general, an alias is a reference to an entry in a keystore. A keystore can contain multiple public keys. You can use a public key alias to refer to and select a specific public key from a keystore.

You can use this attribute to support the following use cases:

-   Management of the certificate lifecycle. Certificates have a certain validity period. Using the *Public Key Alias* attribute in the Verifier step, you can enter both an alias of an existing certificate \(which will expire within a certain time period\) and an alias for a new certificate \(which does not necessarily have to exist already in the keystore\). In this way, the Verifier is configured to verify messages signed by either the old or the new certificate. As soon as the new certificate has been installed and imported into the keystore, the Verifier refers to the new certificate. In this way, certificates can be renewed without any downtime.
-   You can use different aliases to support different signing senders with the same Verifier step. Using the *Public Key Alias* attribute, you can specify a list of signing senders.

> ### Note:  
> Exceptions that occur during runtime are displayed in the *Message Processing Log* view of the *Operations Integration* perspective.

> ### Tip:  
> Fore more information on how signing and verifying works and about the technical concepts, check out [Signing and Verifying a Message Using PKCS\#7/CMS](../40-RemoteSystems/signing-and-verifying-a-message-using-pkcs-7-cms-bb76650.md).



<a name="loiof095dc6b9bb04530bbdaf037b250dd7f__steps_lzm_3qs_vk"/>

## Procedure

1.  In the palette, choose :lock:, then choose ** \> *Verifier* \> *PKCS\#7 Verifier*.

2.  Place *PKCS\#7 Verifier* in integration process and define the message path.

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
    
    Enter the name of the verifier.
    
    </td>
    </tr>
    </table>
    
4.  Enter the following details in the *Processing* tab to verify the signatures of the incoming message.

    **Parameters and Values of PKCS\#7/CMS Signature Verifier**


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
    
    *Header is Base64 Encoded* 
    
    </td>
    <td valign="top">
    
    Select this option to verify if the Signed Data encoded in Base64 is included in the header/property `SapCmsSignedData`.

    See also [Options to Handle Signed Data](../40-RemoteSystems/options-to-handle-signed-data-89f4220.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Body is Base64 Encoded* 
    
    </td>
    <td valign="top">
    
    Select this option to verify if the Signed Data encoded in Base64 is included in the message body.

    See also [Options to Handle Signed Data](../40-RemoteSystems/options-to-handle-signed-data-89f4220.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Public Key Alias* 
    
    </td>
    <td valign="top">
    
    Enter an alias name to select a public key and corresponding certificate from the keystore. You can enter `${header.headername}` or `${property.propertyname}` to read the name dynamically from a header or exchange property.

    > ### Note:  
    > Consider the security implications when deriving key aliases from header attributes as they might be influenced by inbound adapters or exported/published by outbound adapters. It is more secure to use \(exchange\) properties for this purpose.


    
    </td>
    </tr>
    </table>
    
5.  Save the changes.


**Related Information**  


[How PKCS\#7 Works](../40-RemoteSystems/how-pkcs-7-works-21325d5.md "You have the option to sign and encrypt message payloads based on PKCS#7/CMS Enveloped Data and Signed Data (PKCS stands for Public Key Cryptography Standards).")

