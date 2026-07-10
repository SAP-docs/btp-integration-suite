<!-- loio5976731ce4d74cb0938511220c942f17 -->

# Signing the Message Content with XAdES-EPES

This option allows you to create a digital signature based on XML Digital Signature that unambiguously refers to a signature policy agreed between signer and verifier. An electronic signature created this way enforces the usage of the signature policy for signature validation and thus increases the security level of the digital signature.



## Context

A signature policy is a set of rules for the creation and validation of a digital signature.

For more information on XAdES, see:

-   [Signing the Message Content with XML Advanced Electronic Signature](signing-the-message-content-with-xml-advanced-electronic-signature-874e032.md)

-   [http://uri.etsi.org/01903/v1.3.2/ts\_101903v010302p.pdf](http://uri.etsi.org/01903/v1.3.2/ts_101903v010302p.pdf)

-   [Limitations](limitations-08d4522.md)

-   [Message Headers](message-headers-e26ab8c.md)




## Procedure

Specify the properties of the signature.


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

*Signature Policy*

</td>
<td valign="top">

Specify whether a signature policy is to be added, and, if yes, in which form this should be done.

-   `None`
-   `Implied`

    The signature policy can be unambiguously derived from the semantics of the type of data object\(s\) being signed, and some other information.

    Using this option, the *SignaturePolicyImplied* element will be part of the signature.

-   `Explicit ID`

    The signature contains an identifier of a signature policy together with a hash value of the signature policy that allows verification that the policy selected by the signer is the one being used by the verifier.




</td>
</tr>
<tr>
<td valign="top">

*Identifier* \(only if the value `Explicit ID` has been selected for *Signature Policy*\)

</td>
<td valign="top">

Specify an identifier that uniquely identifies a specific version of the signature policy.

You can specify the identifier by one of the following options:

-   By means of a Uniform Resource Identifier \(URI\) \(preferred option when dealing with XML documents\)

    In this case, the Name of the Identifier consists of the identifying URI. In this case, the property Qualifier must not be specified \(empty string\).

-   By means of an Object Identifier when using ASN.1 \(Abstract Syntax Notation One\)

    To support an OID, the content of Identifier consists of an OID, either encoded as a Uniform Resource Name \(URN\) or as a Uniform Resource Identifier \(URI\). The optional Qualifier attribute can be used to provide information about the applied encoding \(values OIDAsURN or OIDAsURI\).




</td>
</tr>
<tr>
<td valign="top">

*Identifier Qualifier* \(only if the value `Explicit ID` has been selected for *Signature Policy*\)

</td>
<td valign="top">

Qualify how the identifier is defined in case Abstract Syntax Notation One \(ASN 1\) is used.

You can select one of the following values:

-   `Empty string` 
-   `OIDAsURI` – uses Uniform Resource Name.
-   `OIDAsURN` – uses Uniform Resource Name.



</td>
</tr>
<tr>
<td valign="top">

*Description* \(only if the value `Explicit ID` has been selected for *Signature Policy*\)

</td>
<td valign="top">

Enter a description of the signature policy.

</td>
</tr>
<tr>
<td valign="top">

*Documentation Reference* \(only if the value `Explicit ID` has been selected for *Signature Policy*\)

</td>
<td valign="top">

Provide a reference to further documentation of the signature policy.

</td>
</tr>
<tr>
<td valign="top">

*Digest Algorithm* \(only if the value `Explicit ID` has been selected for *Signature Policy*\)

</td>
<td valign="top">

Specify the digest algorithm used to calculate the digest value of the signature policy document.

As default, SHA256 is used.

</td>
</tr>
<tr>
<td valign="top">

*Digest Value* \(only if the value `Explicit ID` has been selected for *Signature Policy*\)

</td>
<td valign="top">

Specify the digest value of the signature policy document \(base 64-encoded\).

You can either enter the digest value manually or calculate it.

To calculate the digest value, you have the following options:

-   *Calculate from Identifier*

    Calculates the digest value from the value of the *Identifier* provided above. Note that the Identifier must be a valid URL and start with `http://` or `https://`.

-   *Browse to local File*

    Calculates the digest value from the content of a file.




</td>
</tr>
<tr>
<td valign="top">

*Policy Qualifier* \(only if the value `Explicit ID` has been selected for *Signature Policy*\)

</td>
<td valign="top">

Enter additional information qualifying the signature policy. To do this, enter text or an XML fragment with the root element `SigPolicyQualifier`.

</td>
</tr>
</table>

