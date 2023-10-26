<!-- loio4d3dd24c5c2d451bad3cdb8b46aea93b -->

# Generate a Key Pair

Generate a key pair.





### 

Perform the following call:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

POST

</td>
<td valign="top">

`/KeyPairGenerationRequests` 

</td>
</tr>
</table>



### Input Properties

The following table indicates whether the properties are mandatory or not and also contains the default values:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Mandatory

</th>
<th valign="top">

Type

</th>
<th valign="top">

Default Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Hexalias

</td>
<td valign="top">

X

</td>
<td valign="top">

String

</td>
<td valign="top">



</td>
<td valign="top">

Any dummy hex value

System calculates the correct hex value from the specified `Alias` property.

</td>
</tr>
<tr>
<td valign="top">

Alias

</td>
<td valign="top">

X

</td>
<td valign="top">

String

</td>
<td valign="top">



</td>
<td valign="top">

Keystore entry alias

</td>
</tr>
<tr>
<td valign="top">

KeyType

</td>
<td valign="top">



</td>
<td valign="top">

String

</td>
<td valign="top">

"RSA"

</td>
<td valign="top">

Key type

Possible values are "RSA", "DSA", "EC".

If not specified, the default value is used.

</td>
</tr>
<tr>
<td valign="top">

SignatureAlgorithm

</td>
<td valign="top">



</td>
<td valign="top">

String

</td>
<td valign="top">

"SHA-512/RSA"

</td>
<td valign="top">

Signature Algorithm

Possible values depend on the KeyType value.

If KeyType="RSA", possible values are: "SHA-512/RSA", "SHA-256/RSA", "SHA-384/RSA", "SHA-224/RSA", "SHA-1/RSA".

If KeyType="DSA", possible values are: "SHA-256/DSA", "SHA-224/DSA", "SHA-1/DSA".

If KeyType="EC", possible values are: "SHA-512/ECDSA", "SHA-256/ECDSA", "SHA-1/ECDSA".

</td>
</tr>
<tr>
<td valign="top">

KeySize

</td>
<td valign="top">



</td>
<td valign="top">

Integer

</td>
<td valign="top">

4096

</td>
<td valign="top">

KeySize must be specified for KeyType="RSA" and "DSA"; in the case of KeyType="EC", either this property or the property "KeyAlgorithmParameter" must be specified. For KeyType="EC", the value must be either null or from 112 through 571.

</td>
</tr>
<tr>
<td valign="top">

KeyAlgorithmParameter

</td>
<td valign="top">



</td>
<td valign="top">

String

</td>
<td valign="top">

null

</td>
<td valign="top">

Currently only used for KeyType="EC": Either this property or the property "KeySize" must then be specified. This property can contain the standard name of the Elliptic Curve domain parameters.

Possible values:

secp160k1,secp160r1,secp160r2,secp192k1,

secp192r1,NIST P-192,X9.62 prime192v1,secp224k1,secp224r1,NIST P-224,secp256k1,secp256r1,NIST P-256,X9.62 prime256v1,secp384r1,NIST P-384,secp521r1,NIST P-521,X9.62 prime192v2,X9.62 prime192v3,X9.62 prime239v1,X9.62 prime239v2,X9.62 prime239v3,sect163k1,

NIST K-163,sect163r1,sect163r2,NIST B-163,sect193r1,sect193r2,sect233k1,NIST K-233,sect233r1,NIST B-233,sect239k1,sect283k1,NIST K-283,sect283r1,NIST B-283,sect409k1,NIST K-409,sect409r1,NIST B-409,sect571k1,NIST K-571,sect571r1,NIST B-571,X9.62 c2tnb191v1,X9.62 c2tnb191v2,X9.62 c2tnb191v3,X9.62 c2tnb239v1,X9.62 c2tnb239v2,X9.62 c2tnb239v3,X9.62 c2tnb359v1,X9.62 c2tnb431r1

We recommend using the following curves. • Curves over Fp – 192 bits: secp192k1 and secp192r1. – 224 bits: secp224k1 and secp224r1. – 256 bits: secp256k1 and secp256r1. – 384 bits: secp384r1. – 521 bits: secp521r1. • Curves over F2m – 163 bits: sect163k1, sect163r1, and sect163r2. – 233 bits: sect233k1 and sect233r1. – 239 bits: sect239k1. – 283 bits: sect283k1 and sect283r1. – 409 bits: sect409k1 and sect409r1. – 571 bits: sect571k1 and sect571r1.

</td>
</tr>
<tr>
<td valign="top">

CommonName

</td>
<td valign="top">

X

</td>
<td valign="top">

String

</td>
<td valign="top">



</td>
<td valign="top">

Common name of the subject distinguished name of the certificate

</td>
</tr>
<tr>
<td valign="top">

OrganizationUnit

</td>
<td valign="top">



</td>
<td valign="top">

String

</td>
<td valign="top">



</td>
<td valign="top">

Organization unit of the subject distinguished name of the certificate

</td>
</tr>
<tr>
<td valign="top">

Organization

</td>
<td valign="top">



</td>
<td valign="top">

String

</td>
<td valign="top">



</td>
<td valign="top">

Organization of the subject distinguished name of the certificate

</td>
</tr>
<tr>
<td valign="top">

Locality

</td>
<td valign="top">



</td>
<td valign="top">

String

</td>
<td valign="top">



</td>
<td valign="top">

Locality of the subject distinguished name of the certificate

</td>
</tr>
<tr>
<td valign="top">

State

</td>
<td valign="top">



</td>
<td valign="top">

String

</td>
<td valign="top">



</td>
<td valign="top">

State/province of the subject distinguished name of the certificate

</td>
</tr>
<tr>
<td valign="top">

Country

</td>
<td valign="top">

X

</td>
<td valign="top">

String

</td>
<td valign="top">



</td>
<td valign="top">

Country or region of the subject distinguished name of the certificate, two characters required.

</td>
</tr>
<tr>
<td valign="top">

Email

</td>
<td valign="top">



</td>
<td valign="top">

String

</td>
<td valign="top">



</td>
<td valign="top">

E-mail of the subject distinguished name of the certificate

</td>
</tr>
<tr>
<td valign="top">

ValidNotBefore

</td>
<td valign="top">



</td>
<td valign="top">

Date

</td>
<td valign="top">

Current time

</td>
<td valign="top">

Lower boundary of the validity period of the certificate

</td>
</tr>
<tr>
<td valign="top">

ValidNotAfter

</td>
<td valign="top">



</td>
<td valign="top">

Date

</td>
<td valign="top">

Current time + 3 years

</td>
<td valign="top">

Upper boundary of the validity period of the certificate

</td>
</tr>
</table>

When the KeyType "EC" is used together with a KeySize value, the NIST-recommended elliptic curve domain parameters will be used according to the following table: KeySize Parameter Used Domain Parameter keysize ≤ 192 P-192 192 < keysize ≤ 224 P-224 224 < keysize ≤ 256 P-256 256 < keysize ≤ 384 P-384 384 < keysize P-521

Certain values \(for example, for the alias when indicated in the example request as `<hexalias>`\) need to be provided in hexadecimal notation. String characters are stored by the computer as numbers. When the hexadecimal notation is required, the text is to be provided not as decimal number but as a hexadecimal number instead. For example: The string `my alias` is expressed by the following decimal numbers: `109 121 32 97 108 105 97 115` \(because, according to the American Standard Code for Information Interchange \(ASCII \), the letter `m` is translated to the decimal number `109`, and so forth\). If you convert each number to a hexadecimal number, you get: `6D 79 20 61 6C 69 61 73`. Note that `6D` is the hexadecimal representation of `109`, and so forth. If you like to specify `my alias` in an example request, enter `6D7920616C696173`.



### Request Example

For example, you can use the following request body:

```
{"Hexalias":"<any dummy hex value",
"Alias":"cust_alias",
"KeyType":"RSA",
"SignatureAlgorithm":"SHA256/RSA",
"KeySize":2048,
"CommonName":"cpi.test.wdf.sap.com",
"OrganizationUnit":"My Organization Unit",
"Organization":"My Organization",
"Locality":"My Location",
"State":"My State",
"Country":"DE",
"Email":"mymail@myorganization.com",
"ValidNotBefore":"/Date(1469685029780)/",
"ValidNotAfter":"/Date(1469775029780)/"}
```

