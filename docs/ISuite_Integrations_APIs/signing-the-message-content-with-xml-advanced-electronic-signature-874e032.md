<!-- loio874e032e95e046178afa66510f2b368a -->

# Signing the Message Content with XML Advanced Electronic Signature

XML Advanced Electronic Signature \(XAdES\) allows you to create digital signatures based on XML Digital Signature that include additional qualifying properties.



## Context

The additional properties allow you to create signatures that are compliant with the European Directive \([http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2000:013:0012:0020:EN:PDF](http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2000:013:0012:0020:EN:PDF)\).

**XAdES** is an industry standard based on *XML Signature* and issued by the **European Telecommunications Standards Institute** \(**ETSI**\). It allows you to enhance the digital signature with additional data, for example, timestamps to provide evidence that the signature key was valid at the time the signature was created.

The following XAdES forms are supported:

**XAdES Forms**


<table>
<tr>
<th valign="top">

Form

</th>
<th valign="top">

Allows you to ...

</th>
</tr>
<tr>
<td valign="top">

*XAdES-BES* \(*XAdES-BES \(1\)* and *XAdES-BES \(2\)*\)

\(XAdES Basic Electronic Signature\)

</td>
<td valign="top">

Create an electronic signature based on *XML Digital Signature* that includes additional properties to further qualify the signature.

</td>
</tr>
<tr>
<td valign="top">

*XAdES-EPES*

\(XAdES Explicit Policy based Electronic Signature\)

</td>
<td valign="top">

Create an electronic signature based on *XML Digital Signature* that unambiguously refers to a signature policy agreed between signer and verifier. An electronic signature built in this way enforces the usage of the signature policy for signature validation and thus increases the security level of the usage of the digital signature.

</td>
</tr>
</table>

> ### Note:  
> There are additional XAdES forms defined by the specification. SAP currently only supports XAdES-BES and XAdES-EPES.

For more information, see [http://uri.etsi.org/01903/v1.3.2/ts\_101903v010302p.pdf](http://uri.etsi.org/01903/v1.3.2/ts_101903v010302p.pdf).



## Procedure

**Related Information**  


[Signing the Message Content with XAdES-BES \(1\)](signing-the-message-content-with-xades-bes-1-9aac1e2.md "This option allows you to add timestamps (for the signing time), a reference to the signer's key certificate, and other information that further qualifies the signature.")

[Signing the Message Content with XAdES-BES \(2\)](signing-the-message-content-with-xades-bes-2-2c569fc.md "This option allows you to add further contextual information to the signature, like, for example, the place where the signature has been created, or the type of commitment assured by the signer when creating the signature.")

[Signing the Message Content with XAdES-EPES](signing-the-message-content-with-xades-epes-5976731.md "This option allows you to create a digital signature based on XML Digital Signature that unambiguously refers to a signature policy agreed between signer and verifier. An electronic signature created this way enforces the usage of the signature policy for signature validation and thus increases the security level of the digital signature.")

[Message Headers](message-headers-e26ab8c.md "For certain message headers you can define specific elements in the XAdES form.")

[Limitations](limitations-08d4522.md "SAP currently only supports XAdES-BES and XAdES-EPES. There are a number of additional limitations.")

