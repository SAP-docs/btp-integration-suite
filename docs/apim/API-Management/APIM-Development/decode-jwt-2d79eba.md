<!-- loio2d79eba55e9740db8e6b075b3c5901f4 -->

# Decode JWT

This policy describes about Decode JSON Web Token\(JWT\) Policy.

This policy verifies a signed JWT, with a configurable set of claims. When this policy executes, API Management verifies the signature of a JWT, and verifies that the JWT is valid according to the expiry and not-before times if they are present. The policy can optionally also verify the values of specific claims on the JWT, such as the subject, the issuer, the audience, or the value of additional claims.If the JWT is verified and valid, then all of the claims contained within the JWT are extracted into context variables for use by subsequent policies or conditions, and the request is allowed to proceed. If the JWT signature cannot be verified or if the JWT is invalid because of one of the timestamps, all processing stops and an error is returned in the response.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

The policy shown below decodes a JWT found in the flow variable var.jwt. This variable must be present and contain a viable \(decodable\) JWT. The policy can obtain the JWT from any flow variable.

> ### Code Syntax:  
> ```
> 
> <DecodeJWT async=\"false\" continueOnError=\"false\" enabled=\"true\" xmlns=\"http://www.sap.com/apimgmt\">
>     <Source>var.jwt</Source>
> </DecodeJWT>
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

<Source\> \(Optional\)

</td>
<td valign="top">

If present, specifies the flow variable in which the policy expects to find the JWT to decode.

```
<Source>jwt-variable</Source>
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

steps.jwt.FailedToDecode

</td>
<td valign="top">

Occurs when the policy is unable to decode the JWT. The JWT may be malformed, invalid or otherwise not decodable.

</td>
</tr>
<tr>
<td valign="top">

steps.jwt.InvalidToken

</td>
<td valign="top">

Occurs when the flow variable specified in the <Source\> element of the policy is out of scope or can't be resolved.

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

[Verify JWT](verify-jwt-277635d.md "This policy describes about Verify JSON Web Token(JWT) Policy.")

