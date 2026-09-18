<!-- loioa9cc79d4c84940179088cdf408f5288e -->

# Dynamic Configuration via Partner Directory

Configure the RNIF adapter to resolve Partner Interface Process \(PIP\) and security settings at runtime by looking up entries in the Partner Directory.

You can control the configuration mode with the *Configuration Source* setting in the integration flow channel \(**Processing** tab\).

The RNIF adapter supports two configuration modes:

-   **Static \(Channel-based\)**: Define all Partner Interface Process and security settings directly in the integration flow channel configuration.
-   **Dynamic \(Partner Directory-based\)**: The system resolves settings at runtime by looking up a Partner Directory entry based on values from the incoming message headers. The Partner Directory is a persistent store provided by the integration platform.

The RNIF 2.0 specification decouples the packaging \(encoding\) of the RosettaNet business message from its delivery. This means the system doesn't need to process the business content of the message to determine the sender and receiver partner information. Instead, the delivery header and service header contain all the information needed to resolve the processing configuration dynamically.



## Workflow of Dynamic Configuration

The following steps describe how the system resolves configuration dynamically at runtime:

1.  An incoming RNIF message arrives at the integration flow.
2.  The system checks the *Configuration Source* setting in the channel:
    -   If set to *Static*, the channel-defined settings are used directly.
    -   If set to *Dynamic*, the system reads the delivery header and service header from the message.

3.  The system constructs the PID using the pattern: `DUNS_PIPCode_PIPVersion_PartnerRole`.
4.  The system searches the Partner Directory for the constructed Partner ID \(PID\). For more information about PIDs, see [Partner Identifier \(PID\)](dynamic-configuration-via-partner-directory-a9cc79d.md#loioa9cc79d4c84940179088cdf408f5288e__dynamic)

    > ### Note:  
    > If the PID is not found, the system rejects the message and returns an error.

5.  If the PID is found, the system loads the String Parameters, Binary Parameters, Alternative Partners, and Authorized Users entries from the PID.
6.  The system fills the PIP details and security fields from the loaded parameters and processes the message.



<a name="loioa9cc79d4c84940179088cdf408f5288e__dynamic"/>

## Partner Identifier \(PID\)

A Partner ID \(PID\) is an entry you create in the Partner Directory. It identifies the partner and the corresponding integration flow that processes the message. The PID consists of four values delimited by underscores: `{DUNS}_{PIPCode}_{PIPVersion}_{PartnerRole}`

> ### Example:  
> `123123_3A4_V0202_Buyer`

The four values are extracted from the inbound message as follows:


<table>
<tr>
<th valign="top">

**Value**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

`DUNS`

</td>
<td valign="top">

The `GlobalBusinessIdentifier` from the delivery header.

> ### Note:  
> A single DUNS identifier can have multiple PIDs \(one for each Partner Interface Process, version, and role combination\). The Partner Directory can therefore contain many PIDs across different partners and Partner Interface Processes.



</td>
</tr>
<tr>
<td valign="top">

`PIPCode`

</td>
<td valign="top">

The `GlobalProcessIndicatorCode` from the service header.

</td>
</tr>
<tr>
<td valign="top">

`PIPVersion`

</td>
<td valign="top">

The `VersionIdentifier` from the service header.

</td>
</tr>
<tr>
<td valign="top">

`PartnerRole`

</td>
<td valign="top">

The `GlobalPartnerRoleClassificationCode` from the service header.

</td>
</tr>
</table>

Inside each PID, you can configure entries across the following four parameter types:

> ### Note:  
> You must define all keys inside the Partner Directory without spaces, using underscores as separators. For example: `PIP_Code`, `Action_Type`, `Partner_Role`.



### String Parameters

String parameters contain text-based configuration values, PIP details, and security settings. The following keys are available:

**PIP Details**


<table>
<tr>
<th valign="top">

**Key**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

`Action_Type`

</td>
<td valign="top">

The type of action for the PIP.

</td>
</tr>
<tr>
<td valign="top">

`PIP_Code`

</td>
<td valign="top">

The PIP standard code.

</td>
</tr>
<tr>
<td valign="top">

`PIP_Version`

</td>
<td valign="top">

The PIP version identifier.

</td>
</tr>
<tr>
<td valign="top">

`Business_Transaction_Activity`

</td>
<td valign="top">

The business transaction activity name.

</td>
</tr>
<tr>
<td valign="top">

`Requesting_Action`

</td>
<td valign="top">

The requesting action of the PIP.

</td>
</tr>
<tr>
<td valign="top">

`Current_Role`

</td>
<td valign="top">

The role of the current partner.

</td>
</tr>
<tr>
<td valign="top">

`Partner_Role`

</td>
<td valign="top">

The role of the trading partner.

</td>
</tr>
<tr>
<td valign="top">

`Current_Business_Service_Code`

</td>
<td valign="top">

The business service code of the current partner.

</td>
</tr>
<tr>
<td valign="top">

`Partner_Business_Service_Code`

</td>
<td valign="top">

The business service code of the trading partner.

</td>
</tr>
</table>

**Request Security**


<table>
<tr>
<th valign="top">

**Key**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

`Validate_Signature_Of_Request_Message`

</td>
<td valign="top">

Use this key to validate the digital signature on incoming request messages.

</td>
</tr>
<tr>
<td valign="top">

`Validate_Signature_Private_Key_Alias`

</td>
<td valign="top">

The private key alias used for signature validation.

</td>
</tr>
<tr>
<td valign="top">

`Decrypt_Request_Message`

</td>
<td valign="top">

Use this key to decrypt incoming request messages.

</td>
</tr>
<tr>
<td valign="top">

`Decrypt_Private_Key_Alias`

</td>
<td valign="top">

The private key alias used for decryption.

</td>
</tr>
</table>

**Response Security**


<table>
<tr>
<th valign="top">

**Key**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

`Encrypt_Response_Message`

</td>
<td valign="top">

Use this key to encrypt outgoing response messages.

</td>
</tr>
<tr>
<td valign="top">

`Encryption_Scope`

</td>
<td valign="top">

The scope of encryption to apply.

</td>
</tr>
<tr>
<td valign="top">

`Encryption_Algorithm`

</td>
<td valign="top">

The encryption algorithm to use.

</td>
</tr>
<tr>
<td valign="top">

`Encrypt_Public_Key_Alias`

</td>
<td valign="top">

The public key alias used for encryption.

</td>
</tr>
<tr>
<td valign="top">

`Sign_Response_Message`

</td>
<td valign="top">

Use this key to digitally sign outgoing response messages.

</td>
</tr>
<tr>
<td valign="top">

`Signing_Algorithm`

</td>
<td valign="top">

The signing algorithm to use.

</td>
</tr>
<tr>
<td valign="top">

`Sign_Public_Key_Alias`

</td>
<td valign="top">

The public key alias used for signing.

</td>
</tr>
</table>



### Binary Parameters

Binary parameters store binary content such as certificates or keystores needed for security operations.


<table>
<tr>
<th valign="top">

**Key**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

\(as needed\)

</td>
<td valign="top">

Certificates or keystores for security.

</td>
</tr>
</table>



### Alternative Partners

Alternative partners allow mapping of alternative partner identifiers for a given PID.


<table>
<tr>
<th valign="top">

**Key**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

\(as needed\)

</td>
<td valign="top">

Map alternative partner identifiers.

</td>
</tr>
</table>



### Authorized Users

Authorized Users entries limit authorization to specific client IDs. This restricts which clients can send messages for this PID. Each Authorized Users entry contains a client ID that is allowed to send messages. Multiple Authorized Users entries in the Partner Directory mean that multiple client IDs are allowed.



## Example of a Partner Directory

> ### Example:  
> The following example shows a complete Partner Directory entry for a PIP exchange.
> 
> **Partner ID \(PID\)**: `123456789_3A4_V02.02_Buyer`
> 
> Constructed from:
> 
> -   DUNS = `123456789`
> -   PIPCode = `3A4`
> -   PIPVersion = `V02.02`
> -   PartnerRole = `Buyer`
> 
> **Parameter Types:**
> 
> **String Parameters \(PIP Details\)**
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> **Key**
> 
> </th>
> <th valign="top">
> 
> **Sample Value**
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> `Action_Type`
> 
> </td>
> <td valign="top">
> 
> Single-Action Synchronous Request
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `PIP_Code`
> 
> </td>
> <td valign="top">
> 
> 3A4
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `PIP_Version`
> 
> </td>
> <td valign="top">
> 
> V02.02
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Business_Transaction_Activity`
> 
> </td>
> <td valign="top">
> 
> Purchase Order Request Action
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Requesting_Action`
> 
> </td>
> <td valign="top">
> 
> Purchase Order Request
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Current_Role`
> 
> </td>
> <td valign="top">
> 
> Buyer
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Partner_Role`
> 
> </td>
> <td valign="top">
> 
> Seller
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Current_Business_Service_Code`
> 
> </td>
> <td valign="top">
> 
> Buyer Service
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Partner_Business_Service_Code`
> 
> </td>
> <td valign="top">
> 
> Seller Service
> 
> </td>
> </tr>
> </table>
> 
> **String Parameters \(Request Security\)**
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> **Key**
> 
> </th>
> <th valign="top">
> 
> **Sample Value**
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> `Validate_Signature_Of_Request_Message`
> 
> </td>
> <td valign="top">
> 
> true
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Validate_Signature_Private_Key_Alias`
> 
> </td>
> <td valign="top">
> 
> partner\_sign\_cert
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Decrypt_Request_Message`
> 
> </td>
> <td valign="top">
> 
> true
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Decrypt_Private_Key_Alias`
> 
> </td>
> <td valign="top">
> 
> my\_decrypt\_key
> 
> </td>
> </tr>
> </table>
> 
> **String Parameters \(Response Security\)**
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> **Key**
> 
> </th>
> <th valign="top">
> 
> **Sample Value**
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> `Encrypt_Response_Message`
> 
> </td>
> <td valign="top">
> 
> true
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Encryption_Scope`
> 
> </td>
> <td valign="top">
> 
> Payload
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Encryption_Algorithm`
> 
> </td>
> <td valign="top">
> 
> AES256
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Encrypt_Public_Key_Alias`
> 
> </td>
> <td valign="top">
> 
> partner\_encrypt\_cert
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Sign_Response_Message`
> 
> </td>
> <td valign="top">
> 
> true
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Signing_Algorithm`
> 
> </td>
> <td valign="top">
> 
> SHA-256
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> `Sign_Public_Key_Alias`
> 
> </td>
> <td valign="top">
> 
> my\_sign\_key
> 
> </td>
> </tr>
> </table>
> 
> **Authorized Users**
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> **Key**
> 
> </th>
> <th valign="top">
> 
> **Sample Value**
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> `Authorized_Users`
> 
> </td>
> <td valign="top">
> 
> sb-client1!b123
> 
> </td>
> </tr>
> </table>
> 
> **Binary Parameters**
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> **Key**
> 
> </th>
> <th valign="top">
> 
> **Description**
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> \(as needed\)
> 
> </td>
> <td valign="top">
> 
>  
> 
> </td>
> </tr>
> </table>
> 
> **Alternative Partners**
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> **Key**
> 
> </th>
> <th valign="top">
> 
> **Description**
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> \(as needed\)
> 
> </td>
> <td valign="top">
> 
>  
> 
> </td>
> </tr>
> </table>

