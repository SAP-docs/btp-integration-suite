<!-- loio9857d50b6bcc4b55aaa3432952bc3cdf -->

# How XML Signature Works

A digital signature ensures the authenticity of a message that way that it guarantees the identity of the signer and that the message was not altered after signing. You have the option to digitally sign and validate a message based on the XML Signature standard \(issued by the W3C consortium\). Applying this standard means that the digital signature of a document itself is stored as an XML element.

XML Signature can be applied to any XML document.

The following options for XML Signature are supported:

**Options to Apply XML Signature**


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

Enveloped Signature

</td>
<td valign="top">

Digital signature/validation is applied to XML element that contains the signature as an element \(the Signature element\).

Using this option, the digital signature is part of the XML document to be signed/validated.

</td>
</tr>
<tr>
<td valign="top">

Enveloping Signature

</td>
<td valign="top">

Digital signature/validation is applied to content within an Object element which is part of the Signature element.

That way, the Signature elements acts as an envelope for the signed content. Using this option, the digital signature is part of the XML document to be signed/validated.

</td>
</tr>
</table>

> ### Note:  
> You configure the usage of XML Signature in the related integration flow.

For more information on the supported signature algorithms and canonicalization methods, see: [Sign the Message Content with XML Digital Signature](../50-Development/sign-the-message-content-with-xml-digital-signature-9a013db.md).



<a name="loio9857d50b6bcc4b55aaa3432952bc3cdf__section_N10077_N10012_N10001"/>

## Background Information

In a simplified view, when configured correctly, digitally signing a message based on XML Signature implies the following main steps:

1.  The sender of the message canonicalizes the XML message content that is to be signed.

    Canonicalization transforms the XML document to a standardized \(reference\) format. This step is required because an XML document can have more than one valid representations. Calculating a digest out of two different representations of the same document \(according to step 2\) results in different digests \(or hash values\). This would make the whole signing/validating process invalid.

2.  Out of the canonicalized XML document, a digest is calculated using a digest algorithm.
3.  The sender builds up a *SignedInfo* element that contains the digest.
4.  The sender canonicalizes the *SignedInfo* element.
5.  The sender builds a second digest for the *SignedInfo* element which contains the first digest.
6.  The sender encrypts the digest using its private key.
7.  The sender builds up the *SignatureValue* element which contains the encrypted digest from step 5 \(the signature\).
8.  The message is sent to the receiver.

Digitally verifying \(validating\) a message based on XML Signature works the following way:

1.  The receiver decrypts the encrypted digest \(which is part of the *SignatureValue* element of the received message\) using the sender’s public key.
2.  The receiver calculates the digest out of the *SignedInfo* element of the message.
3.  The receiver compares the two digests that result out of steps 1 and 2.

    That way it is the authenticity of the sender is checked.

4.  The receiver canonicalizes the XML message content.
5.  The receiver calculates the digest out of the XML message content.
6.  The receiver compares the digest that results from the canonicalized message content with that one contained in the *SignedInfo* element of the message.

    That way, it is made sure that the content of the message has not been altered during message processing.


