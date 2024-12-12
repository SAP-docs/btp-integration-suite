<!-- loio9a013dba51dc45429b0103a866b0e484 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Sign the Message Content with XML Digital Signature

You sign a message with an XML digital signature to ensure authenticity and data integrity while sending an XML resource to the participants on the cloud.



## Context



<a name="loio9a013dba51dc45429b0103a866b0e484__steps_qhz_drp_vk"/>

## Procedure

1.  In the palette, choose :lock:, then *Signer* \> *XML Digital Signer*.

2.  Place *XML Digital Signer* in the integration process and define the message path.

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
    
    Enter a name for the signifier.
    
    </td>
    </tr>
    </table>
    
4.  Define the following parameters in the *Processing* tab to create an XML digital signature for the incoming message.

    ****


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
    
    *Private Key Alias* 
    
    </td>
    <td valign="top">
    
    Enter an alias for selecting a private key from keystore. You can also enter $\{header.headername\} or $\{property.propertyname\} to read the name dynamically from a header or exchange property.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signature Algorithm* 
    
    </td>
    <td valign="top">
    
    Signature algorithm for the RSA,DSA, or ECDSA private key type

    Using the private key, the sender encrypts the digest.

    Supported signature algorithms: SHA1/DSA, SHA1/RSA, SHA256/RSA, SHA384/RSA, SHA512/RSA, SHA224/ECDSA, SHA256/ECDSA, SHA384/ECDSA, SHA512/ECDSA.

    Default value: SHA1/DSA.

    > ### Caution:  
    > Algorithms starting with SHA1, MD2, or MD5 are still supported for compatibility reasons, but they no longer meet today's security requirements. Therefore, we recommend using stronger algorithms where possible. Check with your security experts or authorities like NIST for more detailed security recommendations.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Digest Algorithm* 
    
    </td>
    <td valign="top">
    
    Digest algorithm that is used to calculate a digest from the canonicalized XML document

    Supported digest algorithms:

    From Signature Algorithm \(uses digest algorithm from signature algorithm\), SHA1, SHA256, SHA384, SHA512.

    Default value: SHA1512.

    Note that if the digest algorithm is not specified, the digest algorithm of the signature algorithm is used by default.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signature Type* 
    
    </td>
    <td valign="top">
    
    -   *Enveloping XML Signature* 

        The input message body is signed and embedded in the signature. This means that the message body is wrapped by the `Object` element, where `Object` is a child element of the `Signature` element.

    -   *Enveloped XML Signature*

        The digital signature is embedded in the XML message to be signed. This means that the XML message contains the `Signature` element as one of its child elements.

    -   *Detached XML Signature*

        The digital signature is a sibling of the signed element. There can be several XML signatures in one XML document.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *XML Schema file path* \(only if the option *Detached XML Signatures* is selected\)
    
    </td>
    <td valign="top">
    
    Choose *Browse* and select the file path to the XML schema file that is used to validate the incoming XML document. This file has to be in the package source.main.resources.xsd
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signatures for Elements* \(only if the option *Detached XML Signatures* is selected\)
    
    </td>
    <td valign="top">
    
    Choose *Add* to enter the XPath to the attribute of type ID, in order to identify the element to be signed. Example: `/nsx:Document/SubDocument/@Id`

    Namespaces prefixes must be defined in the namespaces mapping of the runtime configuration.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Parent Node* \(only if the option *Enveloped XML Signature* is selected for the attribute *Signature Type*\)
    
    </td>
    <td valign="top">
    
    Specify how the parent element of the Signature element is to be specified. You have the following options:

    -   *Specified by Name and Namespace* \(using local name and namespace\)
    -   *Specified by XPath expression* \(using an *XML Path Language* \(*XPath*\)\)


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Parent Node Name* \(only if the option *Enveloped XML Signature* is selected for the attribute *Signature Type* and *Specified by Name and Namespace* is selected for *Parent Node*\)
    
    </td>
    <td valign="top">
    
    A local name of the parent element of the Signature element

    This attribute is only relevant for Enveloped XML Signature case. The Signature element is added at the end of the children of the parent.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Parent Node Namespace* \(only if the option *Enveloped XML Signature* is selected for the attribute *Signature Type* and *Specified by Name and Namespace* is selected for *Parent Node*\)
    
    </td>
    <td valign="top">
    
    Namespace of the parent element of the Signature element

    This attribute is only relevant for Enveloped XML Signature case. In the Enveloped XML Signature case, a null value is also allowed to support no namespaces. An empty value is not allowed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *XPath Expression* \(only if the option *Enveloped XML Signature* is selected for the attribute *Signature Type* and *Specified by XPath expression* is selected for *Parent Node*\)
    
    </td>
    <td valign="top">
    
    Enter an XPath expression for the parent node to be specified.

    This attribute is only relevant for Enveloped XML Signature case.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Info Content* 
    
    </td>
    <td valign="top">
    
    Specifies which signing key information will be included in the KeyInfo element of the XML signature. You can select a combination of the following attribute values:

    -   *X.509 Certificate Chain*

        X509Certificate elements representing the certificate chain of the signer key

        > ### Note:  
        > The KeyInfo element might not contain the whole certificate chain, but only the certificate chain that is assigned to the key pair entry.

    -   *X.509 Certificate* 

        X509Certificate element containing the X.509 certificate of the signer key

    -   *Issuer Distinguished Name and Serial Number*

        X509IssuerSerial element containing the issuer distinguished name and the serial number of the X.509 certificate of the signer key

    -   *Key Value*

        Key Value element containing the modulus and exponent of the public key

        > ### Note:  
        > You can use any combination of these four attribute values.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Sign Key Info* 
    
    </td>
    <td valign="top">
    
    With this attribute you can specify a reference to the KeyInfo element.
    
    </td>
    </tr>
    </table>
    
    For more information about the various attributes, see the following:

    [http://www.w3.org/TR/xmldsig-core/](http://www.w3.org/TR/xmldsig-core/)

5.  Define the following parameters in *Advanced* tab, under *Transformation Parameters*.

    ****


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Canonicalization Method for SignedInfo* 
    
    </td>
    <td valign="top">
    
    Specify the canonicalization method to be used to transform the `SignedInfo` element that contains the digest \(from the canonicalized XML document\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Transform Method for Payload* 
    
    </td>
    <td valign="top">
    
    Specify the canonicalization method to be used to transform the inbound message body before it is signed.
    
    </td>
    </tr>
    </table>
    
    The following canonicalization methods are available:

    For parameters *Canonicalization Method for SignedInfo* and *Transform Method for Payload*, you can choose between the following canonicalization methods:

    -   *XML Canonicalization Version 1.0*

        More information: [http://www.w3.org/TR/2001/REC-xml-c14n-20010315](http://www.w3.org/TR/2001/REC-xml-c14n-20010315)

    -   *XML Canonicalization with Comments Version 1.0*

        More information: [http://www.w3.org/TR/2001/REC-xml-c14n-20010315\#WithComments](http://www.w3.org/TR/2001/REC-xml-c14n-20010315#WithComments)

    -   *Exclusive XML Canonicalization Version 1.0*

        More information: [http://www.w3.org/2001/10/xml-exc-c14n](http://www.w3.org/2001/10/xml-exc-c14n#)

    -   *Exclusive XML Canonicalization with Comments Version 1.0*

        More information: [http://www.w3.org/2001/10/xml-exc-c14n\#WithComments](http://www.w3.org/2001/10/xml-exc-c14n#WithComments)

    -   *XML Canonicalization Version 1.1*

        More information: [http://www.w3.org/2006/12/xml-c14n11](http://www.w3.org/2006/12/xml-c14n11)

    -   *XML Canonicalization with Comments Version 1.1*

        More information: [http://www.w3.org/2006/12/xml-c14n11\#WithComments](http://www.w3.org/2006/12/xml-c14n11#WithComments)

    -   *None*


    > ### Tip:  
    > Canonicalization transforms an XML document into a form \(the canonical form\) that makes it possible to compare it with other XML documents.
    > 
    > In simple terms, canonicalization skips nonsignificant elements from an XML document. To give some examples, the following changes are applied during the canonicalization of an XML document: Unification of quotation marks and blanks, or encoding of empty elements as start/end pairs. The original message remains unchanged.

    -   CamelXmlSignatureTransformMethods

        Specifies transformation methods in a comma-separated list.

        You can use this header to specify transformation methods in a comma-separated list. This header will overwrite the value of the option *Transform Method for Payload*.

        > ### Example:  

        > ### Sample Code:  
        > Example of this use case: The XML signature verifier of the receiving system expects an XML signature as shown in the following code snippet.
        > 
        > The signature is a detached signature, because the signature element is a sibling of the signed element B. However, the receiving system requires the enveloped-signature transform method to be specified in the Transforms list. To ensure this, you have to configure a detached signature in the XML Signer step, then add a Content Modifier step before the XML Signer step, where you specify the header "CamelXmlSignatureTransformMethods" with the constant value “http://www.w3.org/2000/09/xmldsig\#enveloped-signature,http://www.w3.org/TR/2001/REC-xml-c14n-20010315".
        > 
        > ```
        > 
        > <?xml version="1.0" encoding="UTF-8" ?>
        > 
        > <root> 
        > 
        >             <B ID="IDforB">
        > 
        >                 ...
        > 
        >             </B>
        > 
        >             <ds:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#"
        > 
        >                 Id="_6bf13099-0568-4d76-8649-faf5dcb313c0">
        > 
        >                 <ds:SignedInfo>
        > 
        >                     ...
        > 
        >                     <ds:Reference URI="#IDforB">
        > 
        >                         <ds:Transforms>
        > 
        >                             <ds:Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature" />
        > 
        >                             <ds:Transform Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />
        > 
        >                         </ds:Transforms>
        > 
        >                         ...
        > 
        >                     </ds:Reference>
        > 
        >                 </ds:SignedInfo>
        > 
        >                 <ds:SignatureValue>aUDFmiG71</ds:SignatureValue>
        > 
        >             </ds:Signature>
        > 
        > <root>
        > 
        > ```


    For more information about the various methods, see the following:

    [http://www.w3.org/2000/09/xmldsig\#enveloped-signature,http://www.w3.org/TR/2001/REC-xml-c14n-20010315](http://www.w3.org/2000/09/xmldsig#enveloped-signature,http://www.w3.org/TR/2001/REC-xml-c14n-20010315)

    [http://www.w3.org/2000/09/xmldsig\#enveloped-signature](http://www.w3.org/2000/09/xmldsig#enveloped-signature)

    [http://www.w3.org/TR/2001/REC-xml-c14n-20010315](http://www.w3.org/TR/2001/REC-xml-c14n-20010315) 

    [http://www.w3.org/TR/2001/REC-xml-c14n-20010315\#WithComments](http://www.w3.org/TR/2001/REC-xml-c14n-20010315#WithComments) 

    [http://www.w3.org/2001/10/xml-exc-c14n\#](http://www.w3.org/2001/10/xml-exc-c14n) 

    [http://www.w3.org/2001/10/xml-exc-c14n\#WithComments](http://www.w3.org/2001/10/xml-exc-c14n#WithComments)

6.  On the *Advanced* tab page, under *XML Document Parameters*, specify the following parameters.

    ****


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Reference Type* 
    
    </td>
    <td valign="top">
    
    Enter the value of the type attribute of the content reference.

    If you enter null or empty, no reference type is created.

    More information: [http://www.w3.org/2000/09/xmldsig\#Object](http://www.w3.org/2000/09/xmldsig#Object)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Namespace Prefix* 
    
    </td>
    <td valign="top">
    
    Enter a prefix for the XML signature namespace.

    Default value is *ds*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signature Id* 
    
    </td>
    <td valign="top">
    
    Specifies the value of the Id attribute of the Signature element.

    If you specify no value, no Id attribute is added to the Signature element.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Output Encoding* 
    
    </td>
    <td valign="top">
    
    Select an encoding scheme for the output XML document.

    The encoded output document will be written into the message header. If no encoding scheme is specified, the output will be *UTF-8*-encoded.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Exclude XML Declaration* 
    
    </td>
    <td valign="top">
    
    Specify whether the XML declaration header shall be omitted in the output XML message.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Disallow DOCTYPE Declaration* 
    
    </td>
    <td valign="top">
    
    Specify whether DTD DOCTYPE declarations shall be disallowed in the incoming XML message.
    
    </td>
    </tr>
    </table>
    
7.  Define the following parameters in *XAdES-BES\(1\)* tab.

    More information: [Signing the Message Content with XAdES-BES \(1\)](signing-the-message-content-with-xades-bes-1-9aac1e2.md)

8.  Define the following parameters in *XAdES-BES\(2\)* tab.

    More information: [Signing the Message Content with XAdES-BES \(2\)](signing-the-message-content-with-xades-bes-2-2c569fc.md)

9.  Define the following parameters in *XAdES-EPES* tab.

    More information: [Signing the Message Content with XAdES-EPES](signing-the-message-content-with-xades-epes-5976731.md)

10. Save the changes.


**Related Information**  


[Message-Level Security](../40-RemoteSystems/message-level-security-463a908.md "Several standards are supported to protect the message content (message-level security).")

[XML Digital Signature](xml-digital-signature-ed4a663.md "")

[How XML Signature Works](../40-RemoteSystems/how-xml-signature-works-9857d50.md "A digital signature ensures the authenticity of a message that way that it guarantees the identity of the signer and that the message was not altered after signing. You have the option to digitally sign and validate a message based on the XML Signature standard (issued by the W3C consortium). Applying this standard means that the digital signature of a document itself is stored as an XML element.")

