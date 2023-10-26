<!-- loio277635d687b048448dccfa4402da1bf4 -->

# Verify JWT

This policy describes about Verify JSON Web Token\(JWT\) Policy.

This policy verifies a signed JWT, with a configurable set of claims. When this policy executes, API Management verifies the signature of a JWT, and verifies that the JWT is valid according to the expiry and not-before times if they’re present. The policy can optionally also verify the values of specific claims on the JWT, such as the subject, the issuer, the audience, or the value of additional claims.If the JWT is verified and valid, then all of the claims contained within the JWT are extracted into context variables for use by subsequent policies or conditions, and the request is allowed to proceed. If the JWT signature can’t be verified or if the JWT is invalid because of one of the timestamps, all processing stops and an error is returned in the response.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

**Verify a JWT signed with the HS256 algorithm**

The sample provided below verifies a JWT signed with the HS256 encryption algorithm, HMAC using a SHA-256 checksum.HS256 relies on a shared secret for both signing and verifying the signature.

> ### Code Syntax:  
> ```
> 
> <VerifyJWT async=\"false\" continueOnError=\"false\" enabled=\"true\" xmlns=\"http://www.sap.com/apimgmt\">
>     <Algorithm>HS256</Algorithm>
>     <Source>request.formparam.jwt</Source>
>     <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>     <SecretKey>
>         <Value ref="private.secretkey"/>
>     </SecretKey>
>     <Subject>subject-subject</Subject>
>     <Issuer>urn://apim-JWT-policy-test</Issuer>
>     <Audience>audience1,audience2</Audience>
>     <AdditionalClaims>
>         <Claim name=\"additional-claim-name\" type=\"string\">additional-claim-value-goes-here</Claim>
>     </AdditionalClaims>
> </VerifyJWT>
> ```

Verify a JWT signed with the RS256 algorithm

This example policy verifies a JWT that was signed using the RS256 algorithm. For signing, a private key must be provided, and to verify, you need to provide the corresponding public key.

> ### Code Syntax:  
> ```
>  
> <VerifyJWT async=\"false\" continueOnError=\"false\" enabled=\"true\" xmlns=\"http://www.sap.com/apimgmt\">
>     <Algorithm>RS256</Algorithm>
>     <Source>request.formparam.jwt</Source>
>     <IgnoreUnresolvedVariables>false</IgnoreUnresolvedVariables>
>     <PublicKey>
>         <Value ref="public.publickey"/>
>     </PublicKey>
>     <Subject>subject-subject</Subject>
>     <Issuer>urn://apim-JWT-policy-test</Issuer>
>     <Audience>audience1,audience2</Audience>
>     <AdditionalClaims>
>         <Claim name=\"additional-claim-name\" type=\"string\">additional-claim-value-goes-here</Claim>
>     </AdditionalClaims>
> </VerifyJWT>
> 
> ```

The resulting JWT will have this header and payload and is valid, if the signature can be verified with the provided public key.

> ### Sample Code:  
> ```
> 
> # header
> {
>   "typ" : "JWT", 
>   "alg" : "RS256"
> }
> # payload
> { 
>   "sub" : "subject-subject",
>   "iss" : "urn://apim-edge-JWT-policy-test",
>   "aud" : "audience1,audience2",
>   "additional-claim-name": "additional-claim-value-goes-here"
> }
> ```

However, a JWT with the same header but different payload as shown below is invalid, even if the signature is verified. The "sub" claim included in the JWT does not match the required value of the "Subject" element as specified in the policy configuration.

> ### Sample Code:  
> ```
> 
> { 
>   "sub" : "subject1",
>   "iss" : "urn://apim-edge-JWT-policy-test",
>   "aud" : "audience1,audience2",
>   "additional-claim-name": "additional-claim-value-goes-here"
> }
> 
> ```

Following table lists the elements and attributes that you can configure on this policy


<table>
<tr>
<th valign="top">

**Elements and Attributes**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

Algorithm

</td>
<td valign="top">

Specifies the encryption algorithm to sign the token. HS256 employs a shared secret. RS256 employs a public/secret key pair.

Supported value: HS256, HS384, HS512, RS256, RS384, RS512

```
<Algorithm>HS256|RS256</Algorithm>
```



</td>
</tr>
<tr>
<td valign="top">

Audience \(optional\)

</td>
<td valign="top">

The policy verifies that the audience claim in the JWT matches the value specified in the configuration. If there is no match, the policy throws an error.

```
<Audience>audience</Audience>
```



</td>
</tr>
<tr>
<td valign="top">

AdditionalClaims \(optional\)

</td>
<td valign="top">

Validates additional claims in the payload of the JWT. An additional claim can be a string, a number, a boolean, a map, or an array. A map is simply a set of name/value pairs.

```

	<AdditionalClaims>
    <Claim name='claim1'>explicit-value-of-claim-here</Claim>
    <Claim name='claim2' ref='var-name'/>
    <Claim name='claim3' ref='var-name' type='boolean'/>
   </AdditionalClaims>

```

The <Claim\> element takes these attributes:

-   name: name of the claim.

    > ### Note:  
    > Don’t use any of the registered claim names in this element. They include: "iss", "sub", "aud", "iat", "exp", "nbf", and "jti".

-   ref: The name of a flow variable. If present, the policy will use the value of this variable as the claim. If both a ref attribute and an explicit claim value are specified, the explicit value is the default, and is used if the referenced flow variable is unresolved.
-   type: One of: string \(default\), number, boolean, or map
-   array: Set to true to indicate if the value is an array of types. Default: false.

Only name attribute is mandatory.

</td>
</tr>
<tr>
<td valign="top">

AdditionalHeaders \(optional\)

</td>
<td valign="top">

Validates additional claim in the header for the JWT.

```

	<AdditionalHeaders>
    <Claim name='claim1'>explicit-value-of-claim-here</Claim>
    <Claim name='claim2' ref='var-name'/>
    <Claim name='claim3' ref='var-name' type='boolean'/>
    <Claim name='claim4' ref='var-name' type='string' array='true'/>
 </AdditionalHeaders>

```

The <Claim\> element takes these attributes:

-   name: name of the claim.

    > ### Note:  
    > Do not use any of the registered claim names in this element. They include: "iss", "sub", "aud", "iat", "exp", "nbf", and "jti".

-   ref: The name of a flow variable. If present, the policy uses the value of this variable as the claim. If both a ref attribute and an explicit claim value are specified, the explicit value is the default, and is used if the referenced flow variable is unresolved.
-   type: One of: string \(default\), number, boolean, or map
-   array: Set to true to indicate if the value is an array of types. Default: false.

Only name attribute is mandatory.

</td>
</tr>
<tr>
<td valign="top">

Id \(Optional\)

</td>
<td valign="top">

The JWT ID \(jti\) claim is a unique identifier for the JWT. Id attribute verifies if the JWT contains the specific jti claim. When the text value and ref attribute are both empty, the policy generates a jti containing a random UUID.

```

	<Id>explicit-jti</Id>
		 -or-
	<Id ref='varname'/>
		 -or-
	<Id/>
```



</td>
</tr>
<tr>
<td valign="top">

IgnoreUnresolvedVariables \(Optional\)

</td>
<td valign="top">

Set to false if you want the policy to throw an error when any referenced variable specified in the policy is unresolvable. Set to true to treat any unresolvable variable as an empty string

```
<IgnoreUnresolvedVariables>true|false</IgnoreUnresolvedVariables>
```



</td>
</tr>
<tr>
<td valign="top">

Issuer \(Optional\)

</td>
<td valign="top">

The policy verifies that the issuer in the JWT matches the string specified in the configuration element.

```
<Issuer ref='variable-name-here'/>
<Issuer>issuer-string-here</Issuer>
```



</td>
</tr>
<tr>
<td valign="top">

<PublicKey/JWKS\> \(JWKS or Value element is required to verify a JWT signed with RSA algorithm\)

</td>
<td valign="top">

Specifies a value in the JSON web key set \(JWKS\) format containing a set of public keys. If the JWT contains a key ID in the set of JWKS, then the policy uses the correct public key to verify the JWT.



```
<PublicKey>
  <JWKS ref="public.jwks"/>
</PublicKey>

or

<PublicKey>
  <JWKS>JWKS-value</JWKS>
</PublicKey>
```



</td>
</tr>
<tr>
<td valign="top">

<PublicKey/Value\> \(JWKS or Value element is required to verify a JWT signed with RSA algorithm\)

</td>
<td valign="top">

Use this element only when the algorithm is an RSA variant. This element specifies the public key to verify the signature. Specify the PEM-encoded key directly or use the ref attribute to pass the key in a flow variable.



```
<PublicKey>
   <Value ref="public.publickey"/>
</PublicKey>
-or-
<PublicKey>
    <Value>
    -----BEGIN PUBLIC KEY-----
    MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAw2kPrRzcufvUNHvTH/WW
    Q0UrCw5c0+Y707KX3PpXkZGbtTT4nvU1jC0d1lHV8MfUyRXmpmnNxJHAC2F73IyN
    C5TBtXMORc+us7A2cTtC4gZV256bT4h3sIEMsDl0Joz9K9MPzVPFxa1i0RgNt06n
    Xn/Bs2UbbLlKP5Q1HPxewUDEh0gVMqz9wdIGwH1pPxKvd3NltYGfPsUQovlof3l2
    ALvO7i5Yrm96kknfFEWf1EjmCCKvz2vjVbBb6mp1ZpYfc9MOTZVpQcXSbzb/BWUo
    ZmkDb/DRW5onclGzxQITBFP3S6JXd4LNESJcTp705ec1cQ9Wp2Kl+nKrKyv1E5Xx
    DQIDAQAB
    -----END PUBLIC KEY-----
    </Value>
</PublicKey>
```

> ### Restriction:  
> JWT validation fails RSA keys smaller than 2048 bits. Ensure that your keys are 2048 bits or larger.



</td>
</tr>
<tr>
<td valign="top">

<Source\> \(Optional\)

</td>
<td valign="top">

If present, specifies the flow variable in which the policy expects to find the JWT to verify.

```
<Source>jwt-variable</Source>
```



</td>
</tr>
<tr>
<td valign="top">

<Subject\> \(Optional\)

</td>
<td valign="top">

The policy verifies that the subject in the JWT matches the string specified in the policy configuration.

```
<Subject>subject-string-here</Subject>
```



</td>
</tr>
<tr>
<td valign="top">

<SecretKey/Value\> \(Optional\)

</td>
<td valign="top">

Provides the secret key used to verify or sign tokens with an HMAC algorithm. Use only when the algorithm is one of HS256, HS384, HS512. Use the ref attribute to pass the key in a flow variable.

```
<SecretKey>
  <Value ref="private.your-variable-name"/>
</SecretKey>
```



</td>
</tr>
<tr>
<td valign="top">

<TimeAllowance\> \(Optional\)

</td>
<td valign="top">

The "grace period" for times. For example, if the time allowance is configured to be 60s, then an expired JWT would be treated as still valid, for 60s after the asserted expiry. The not-before-time will be evaluated similarly. Default value is 0s.

```

	<TimeAllowance>60s</TimeAllowance>
```



</td>
</tr>
</table>

The following flow variables are available after the policy is executed:

**Flow Variables**


<table>
<tr>
<th valign="top">

Variable

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

header.algorithm

</td>
<td valign="top">

Signing algorithm used on JWT.

</td>
</tr>
<tr>
<td valign="top">

claim.subject

</td>
<td valign="top">

JWT subject claim.

</td>
</tr>
<tr>
<td valign="top">

claim.issuer

</td>
<td valign="top">

JWT issuer claim.

</td>
</tr>
<tr>
<td valign="top">

claim.audience

</td>
<td valign="top">

JWT audience claim. This value may be a string, or an array of strings.

</td>
</tr>
<tr>
<td valign="top">

claim.expiry

</td>
<td valign="top">

Expiration date or time, expressed in seconds.

</td>
</tr>
<tr>
<td valign="top">

expiry\_formatted

</td>
<td valign="top">

Expiration date or time, formatted as a human readable string. Example: 2019-18-28T21:30:45.000+0000

</td>
</tr>
<tr>
<td valign="top">

seconds\_remaining

</td>
<td valign="top">

Number of seconds before the token expires. If the token is expired, this number will be negative.

</td>
</tr>
<tr>
<td valign="top">

time\_remaining\_formatted

</td>
<td valign="top">

Time remaining before the token expires, formatted as a human-readable string. Example: 00:59:59.926

</td>
</tr>
<tr>
<td valign="top">

is\_expired

</td>
<td valign="top">

true or false

</td>
</tr>
<tr>
<td valign="top">

claim.issuedat

</td>
<td valign="top">

Token issued Date, expressed in seconds since epoch.

</td>
</tr>
<tr>
<td valign="top">

claim.notbefore

</td>
<td valign="top">

If the JWT includes a nbf claim, this variable will contain the value. This is expressed in seconds since epoch.

</td>
</tr>
<tr>
<td valign="top">

valid

</td>
<td valign="top">

In the case of VerifyJWT, this variable will be true when the signature is verified, and the current time is before the token expiry, and after the token notBefore value, if they are present. Otherwise false.

In the case of DecodeJWT, this variable is not set.

</td>
</tr>
<tr>
<td valign="top">

claim.name

</td>
<td valign="top">

The value of the named claim \(standard or additional\) in the payload. One of these will be set for every claim in the payload.

</td>
</tr>
<tr>
<td valign="top">

header.name

</td>
<td valign="top">

The value of the named header \(standard or additional\). One of these will be set for every additional header in the header portion of the JWT.

</td>
</tr>
<tr>
<td valign="top">

header.kid

</td>
<td valign="top">

The Key ID, if added when the JWT was generated.

</td>
</tr>
<tr>
<td valign="top">

header.type

</td>
<td valign="top">

Will be set to JWT.

</td>
</tr>
<tr>
<td valign="top">

payload-claim-names

</td>
<td valign="top">

An array of claims supported by the JWT.

</td>
</tr>
<tr>
<td valign="top">

payload-json

</td>
<td valign="top">

Payload in JSON format.

</td>
</tr>
<tr>
<td valign="top">

header-json

</td>
<td valign="top">

Header in JSON format.

</td>
</tr>
</table>

During the policy execution, the following errors can occur:

**Error Cause**


<table>
<tr>
<th valign="top">

Error Name

</th>
<th valign="top">

Cause

</th>
</tr>
<tr>
<td valign="top">

steps.jwt.AlgorithmInTokenNotPresentInConfiguration

</td>
<td valign="top">

Occurs when the verification policy has multiple algorithms.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.AlgorithmMismatch

</td>
<td valign="top">

The algorithm specified in the Generate policy did not match the one expected in the Verify policy. The algorithms specified must match

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.FailedToDecode

</td>
<td valign="top">

The policy was unable to decode the JWT. The JWT is possibly corrupted.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.GenerationFailed

</td>
<td valign="top">

The policy was unable to generate the JWT.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.InsufficientKeyLength

</td>
<td valign="top">

For a key less than 32 bytes for the HS256 algorithm, less than 48 bytes for the HS386 algortithm, and less than 64 bytes for the HS512 algorithm.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.InvalidClaim

</td>
<td valign="top">

For a missing claim or claim mismatch, or a missing header or header mismatch.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.InvalidCurve

</td>
<td valign="top">

The curve specified by the key is not valid for the Elliptic Curve algorithm.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.InvalidJsonFormat

</td>
<td valign="top">

Invalid JSON found in the header or payload.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.InvalidToken

</td>
<td valign="top">

This error occurs when the JWT signature verification fails.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.JwtAudienceMismatch

</td>
<td valign="top">

The audience claim failed on token verification.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.JwtIssuerMismatch

</td>
<td valign="top">

The issuer claim failed on token verification.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.JwtSubjectMismatch

</td>
<td valign="top">

The subject claim failed on token verification.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.KeyIdMissing

</td>
<td valign="top">

The Verify policy uses a JWKS as a source for public keys, but the signed JWT does not include a kid property in the header

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.KeyParsingFailed

</td>
<td valign="top">

The public key could not be parsed from the given key information.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.NoAlgorithmFoundInHeader

</td>
<td valign="top">

Occurs when the JWT contains no algorithm header.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.NoMatchingPublicKey

</td>
<td valign="top">

The Verify policy uses a JWKS as a source for public keys, but the kid in the signed JWT is not listed in the JWKS.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.SigningFailed

</td>
<td valign="top">

In GenerateJWT, for a key less than the minimum size for the HS384 or HS512 algorithms

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.TokenExpired

</td>
<td valign="top">

The policy attempts to verify an expired token.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.TokenNotYetValid

</td>
<td valign="top">

The token is not yet valid.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.UnknownException

</td>
<td valign="top">

An unknown exception occurred.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.WrongKeyType

</td>
<td valign="top">

Wrong type of key specified. For example, if you specify an RSA key for an Elliptic Curve algorithm, or a curve key for an RSA algorithm.

</td>
</tr>
</table>

The following fault variables are set when the policy triggers an error at runtime:

**Fault Variables**


<table>
<tr>
<th valign="top">

Variable Set

</th>
<th valign="top">

Where

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

fault.name="fault\_name"

</td>
<td valign="top">

fault\_name is the name of the fault, as listed in the Runtime errors table above. The fault name is the last part of the fault code.

</td>
<td valign="top">

fault.name Matches "TokenExpired"

</td>
</tr>
<tr>
<td valign="top">

jwt.policy\_name.failed

</td>
<td valign="top">

policy\_name is the user-specified name of the policy that threw the fault.

</td>
<td valign="top">

jwt.JWT-Policy.failed = true

</td>
</tr>
</table>

Following is an example of a fault rule:

> ### Sample Code:  
> ```
> <FaultRules>
>     <FaultRule name="JWT Policy Errors">
>         <Step>
>             <Name>JavaScript-1</Name>
>             <Condition>(fault.name Matches "TokenExpired")</Condition>
>         </Step>
>         <Condition>jwt.JWT-1.failed=true</Condition>
>     </FaultRule>
> </FaultRules>
> ```

**Related Information**  


[JSON Web Tokens](json-web-tokens-bb1e955.md "This topic describes about JSON Web Tokens (JWT) policies available in API Management.")

[Generate JWT](generate-jwt-c28be0e.md "This topic describes about Generate JSON Web Token(JWT) Policy.")

[Decode JWT](decode-jwt-2d79eba.md "This policy describes about Decode JSON Web Token(JWT) Policy.")

