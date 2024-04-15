<!-- loio9aac1e2f25ba45a985453ba0cb1765f7 -->

# Signing the Message Content with XAdES-BES \(1\)

This option allows you to add timestamps \(for the signing time\), a reference to the signer's key certificate, and other information that further qualifies the signature.



## Context

For more information on XAdES, see:

-   [Signing the Message Content with XML Advanced Electronic Signature](signing-the-message-content-with-xml-advanced-electronic-signature-874e032.md)

-   [http://uri.etsi.org/01903/v1.3.2/ts\_101903v010302p.pdf](http://uri.etsi.org/01903/v1.3.2/ts_101903v010302p.pdf)

-   [Limitations](limitations-08d4522.md)

-   [Message Headers](message-headers-e26ab8c.md)




## Procedure

1.  Add the signing time and the certificate to the signature.


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Time* 
    
    </td>
    <td valign="top">
    
    Select this option if you want to add the signing time to the signature.

    This measure helps to provide evidence that the signature key was valid at the time the signature was created.

    If you like to change the time zone used for the `SigningTime` element of the signature, you can set property `SAP_XadesSigningTimeZone`. The *XML Signer* step then transforms the value of the `SigningTime` element into the time zone specified by the property value.

    Example: Assume that the following signing time is generated for the signature if the property isn’t set \(uses GMT time zone\):

    `<xades:SigningTime>2024-04-01T20:00:00Z</xades:SigningTime>`

    If you specify the value of property `SAP_XadesSigningTimeZone` as `GMT+3:00`, the element created by the XML Signer step is changed to:

    `<xades:SigningTime>2024-04-01T23:00:00+03:00</xades:SigningTime>`

    See also: [Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Certificate* 
    
    </td>
    <td valign="top">
    
    Specify whether the certificate of the signing key is to be added to the signature.

    You have the following options:

    -   `None`

        Add no certificate.

    -   `Certificate Only`

        Add digest value, issuer, and serial number of the signing certificate.

    -   `Certificate Chain` 

        Add digest value, issuer, and serial number of the certificates of the certificate chain.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Digest Algorithm* \(only when either `Certificate Only` or `Certificate Chain` is selected for *Certificate*\)
    
    </td>
    <td valign="top">
    
    Specify a digest algorithm that is to be used to calculate a digest value from the certificate.

    This measure helps to control whether the certificate that is used to verify the message content corresponds to the one that has been used to sign the message content.

    `SHA256` is proposed as the default.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Certificate URI*
    
    </td>
    <td valign="top">
    
    Specify a reference to the certificate.

    If as *Certificate* you have selected `Certificate Only`, only one URI is allowed.

    If as *Certificate* you have selected `Certificate Chain`, you can add for each certificate in the certificate chain an URI. The URI must be added at the position where the corresponding certificate in the chain is located. At the position 0 the signing certificate URI must be placed. If for a certain certificate in the chain no URI is available, enter an empty string at the corresponding place in the URI list.
    
    </td>
    </tr>
    </table>
    
    Adding the signer's key certificate and its digest value to the signed document makes sure that the signed document contains an unambiguous reference to the signer's certificate.

2.  Specify the signer role.

    These properties allow you to specify the role of the signer in order to make clear the signer's position in the company or organization. Doing this helps provide evidence to the verifier that the signer is empowered by the organization to perform the signing task.


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Claimed Roles* \(optional\)
    
    </td>
    <td valign="top">
    
    Specify the claimed roles of the signer.

    To specify a claimed role, choose *Add* and enter a text or an XML fragment with the root element *ClaimedRole*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Certified Roles* \(optional\)
    
    </td>
    <td valign="top">
    
    Specify the roles of the signer which are certified by an attribute certificate.

    An attribute certificate associates the identifier of a certificate to some attributes of its owner, in this case, to a role

    The specified attribute certificates must be base-64 encoded.

    To specify a certified role, choose *Add* and specify the following attributes:

    -   *Encoding*

        Select the encoding scheme.

        An empty string indicates that the *Encoding* attribute is not specified. In this case, it is assumed that the PKI data is ASN.1 data encoded in DER.

    -   *ID* \(optional\)


    
    </td>
    </tr>
    </table>
    
3.  Under *Data Object Format*, specify the format of the signed data.


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Description* \(optional\)
    
    </td>
    <td valign="top">
    
    Provide an informal text to describe the format of the signed data.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *MIME Type* \(optional\)
    
    </td>
    <td valign="top">
    
    Specify the Internet Media Type \(MIME type\) that determines the data object format.

    You need to enter the MIME type manually.

    Example: `text/xml`
    
    </td>
    </tr>
    </table>
    
    This information can help to parse the signed document correctly.

4.  Specify the Identifier of the data object format.


    <table>
    <tr>
    <th valign="top">

    Option
    
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
    
    Specify an identifier to indicate the format of a signed data.

    You can specify the identifier by one of the following options:

    -   By means of a Uniform Resource Identifier \(URI\) \(preferred option when dealing with XML documents\)

        In this case, the *Name* of the identifier consists of the identifying URI. In this case, the property *Qualifier* must not be specified \(empty string\).

    -   By means Object Identifier \(OID\) when using ASN.1 \(Abstract Syntax Notation One\)

        To support an OID, the content of Identifier consists of an OID, either encoded as Uniform Resource Name \(URN\) or as Uniform Resource Identifier \(URI\). The optional *Qualifier* attribute can be used to provide a hint about the applied encoding \(values `OIDAsURN` or `OIDAsURI`\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Qualifier* \(only relevant if an Identifier *Name* has been specified\)
    
    </td>
    <td valign="top">
    
    Further qualify how the identifier is defined in case Abstract Syntax Notation One \(ASN 1\) is used.

    You can select one of the following values:

    -   `empty string` 
    -   `OIDAsURI` – uses Uniform Resource Name.
    -   `OIDAsURN` – uses Uniform Resource Name.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description* \(only relevant if an Identifier *Name* has been specified\)
    
    </td>
    <td valign="top">
    
    Provide a reference to further documentation of the identifier.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Documentation Reference* \(only relevant if an Identifier *Name* has been specified\)
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    

