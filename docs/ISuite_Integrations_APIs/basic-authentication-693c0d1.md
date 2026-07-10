<!-- loio693c0d1720644d57918ed77acc6a95ef -->

# Basic Authentication

Basic authentication policy takes a username and password, encode them to Base64 format and writes the resulting value to a variable. The resulting value is typically written to an HTTP header, such as the `Authorization` header in the form `Basic Base64EncodeString`.

> ### Note:  
> This policy does not enforce basic authentication on a request to an API proxy. Instead, you use it to Base64 encode or decode credentials, typically when connecting to a backend server or using a service callout policy that requires basic authentication.

The policy has two modes of operations:

-   Encode: Base64 encodes a username and password stored in variables

-   Decode: Decodes the username and password from a Base64 encoded string


The username and password are commonly stored the key/value store and then read from the key/value store at runtime.

You can attach this policy in the following locations: ![](images/Flow_policy_116062b.png)

An example payload for the policy is as follows:

> ### Code Syntax:  
> ```
> 
> <!–-  Use Case: Create and set authorization header for the current request from the given user name and password.
>  The policy retrieves user name and password from the request body which is supplied as form parameters.
> -->
> 
> 
> <BasicAuthentication async='true' continueOnError='false' enabled='true' xmlns='http://www.sap.com/apimgmt'>
> 	<Operation>Encode</Operation>
> 	<IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
> 	<User ref='request.formparam.username'></User>
> 	<Password ref='request.formparam.password'></Password>
> 	<AssignTo createNew="false">request.header.Authorization</AssignTo>
> </BasicAuthentication>
> 
> 
> <!–- Use case: Extract the user credentials from the authorization header
> User name and password is extracted from the authorization header of the incoming request.
> The user name and password is set into the flow variables named as “current.username” and “current.password” respectively.
> -->
> 
> <BasicAuthentication async='true' continueOnError='false' enabled='true' xmlns='http://www.sap.com/apimgmt'>
> 	<Operation>Decode</Operation>
> 	<IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
> 	<User ref='current.username'></User>
> 	<Password ref='current.password'></Password>
> 	<Source>request.header.Authorization</Source>
> </BasicAuthentication>
> 
> 
> ```


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

Operation \(Mandatory\)

</td>
<td valign="top">

Supports values `Encode` or `Decode`. This setting will enable you to encode credentials to populate an HTTP header on an outbound request, or decode encoded credentials from HTTP header of an inbound request.

</td>
</tr>
<tr>
<td valign="top">

IgnoreUnresolvedVariables \(Optional\)

</td>
<td valign="top">

Supports values `true` or `false`. This setting determines whether to throw an error if the variables defined in the policy is not resolved. If set to true, the policy will not throw an error if a variable cannot be resolved. In basic authentication policy, it is recommended to set this value to false, because it is beneficial to throw an error if a username or password cannot be found in the variables specified.

</td>
</tr>
<tr>
<td valign="top">

User ref \(Mandatory\)

</td>
<td valign="top">

Settings for username.

For encoding, set a reference attribute to the username to dynamically retrieve value from a variable.

For decoding, specify the flow variable in which the decoded username is to be placed.

</td>
</tr>
<tr>
<td valign="top">

Password ref \(Mandatory\)

</td>
<td valign="top">

Settings for password.

For encoding, set a reference attribute to the password to dynamically retrieve the value from a variable.

For decoding, specify the flow variable in which the decoded password is to be placed.

</td>
</tr>
<tr>
<td valign="top">

AssignTo

</td>
<td valign="top">

Assigns the encoded value of username and password to a variable. Do not use this if the operation is `Decode`.

</td>
</tr>
<tr>
<td valign="top">

Source

</td>
<td valign="top">

The encoded value of username and password.is retrieved from Source. Do not use this if the operation is `Encode`.

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

UnresolvedVariable

</td>
<td valign="top">

The required source variables for the decode or encode are not present. This error can only occur if IgnoreUnresolvedVariables is false.

</td>
</tr>
<tr>
<td valign="top">

InvalidBasicAuthenticationSource

</td>
<td valign="top">

On a decode when the incoming Base64 encoded string does not contain a valid value or the header is malformed \(for example does not start with "Basic"\).

</td>
</tr>
<tr>
<td valign="top">

UserNameRequired

</td>
<td valign="top">

The <User\> element must be present for the named operation. See the fault string.

</td>
</tr>
<tr>
<td valign="top">

PasswordRequired

</td>
<td valign="top">

The <Password\> element must be present for the named operation. See the fault string.

</td>
</tr>
<tr>
<td valign="top">

AssignToRequired

</td>
<td valign="top">

The <AssignTo\> element must be present for the named operation. See the fault string.

</td>
</tr>
<tr>
<td valign="top">

SourceRequired

</td>
<td valign="top">

The <Source\> element must be present for the named operation. See the fault string.

</td>
</tr>
</table>

Following fault variables are set when the policy triggers an error at runtime:

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

\[prefix\].\[policy\_name\].failed

</td>
<td valign="top">

The \[prefix\] is BasicAuthentication.

The \[policy\_name\] is the name of the policy that threw the error.

</td>
<td valign="top">

BasicAuthentication.BA-Authenticate.failed = true

</td>
</tr>
<tr>
<td valign="top">

fault.\[error\_name\]

</td>
<td valign="top">

\[error\_name\] = The specific error name to check for as listed in the table above.

</td>
<td valign="top">

fault.name Matches "UnresolvedVariable"

</td>
</tr>
</table>

**Related Information**  


[Key Value Map Operations](key-value-map-operations-b72dc3f.md "The key value map operations policy allows you to create a key value map and perform update, read, and delete operations on the map.")

