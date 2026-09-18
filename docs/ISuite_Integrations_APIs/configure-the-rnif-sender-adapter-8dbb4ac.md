<!-- loio8dbb4acd4f854d369314469fe4b7c9a9 -->

# Configure the RNIF Sender Adapter

Configure the RNIF sender adapter for SAP Cloud Integration to receive RosettaNet messages from a trading partner over HTTPS.

After you create a sender channel and select the RNIF sender adapter, configure the following attributes:

> ### Note:  
> If a parameter is not set, the corresponding feature is disabled or default values are used.



## Connections Tab

Select the *Connections* tab and provide values in the following fields:


<table>
<tr>
<th valign="top">

**Parameter**

</th>
<th valign="top">

**Section**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Endpoint Configuration

</td>
<td valign="top">

Configure the URL path for the endpoint. The address must start with `/` and must be unique per tenant. The full path is: `/RNIF/RNIF/{url}`

</td>
</tr>
<tr>
<td valign="top">

*Authorization*

</td>
<td valign="top">

Endpoint Configuration

</td>
<td valign="top">

Select the authorization type for incoming requests:

-   *User Role*: Authorization is performed against a configured user role.
-   *Client Certificate*: Authorization is performed using the client certificate presented by the sender.



</td>
</tr>
<tr>
<td valign="top">

*User Role* 

> ### Note:  
> Only visible when *User Role* is selected.



</td>
<td valign="top">

Endpoint Configuration

</td>
<td valign="top">

Enter the user role required to access this endpoint. The default is: `ESBMessaging.send`

</td>
</tr>
<tr>
<td valign="top">

*Subject DN* 

> ### Note:  
> Only visible when *Client Certificate* is selected.



</td>
<td valign="top">

Client Certificate Authorization

</td>
<td valign="top">

Enter the allowed client certificate Subject DN entries, separated by commas. The system only accepts certificates with a matching Subject DN.

</td>
</tr>
<tr>
<td valign="top">

*Issuer DN* 

> ### Note:  
> Only visible when *Client Certificate* is selected.



</td>
<td valign="top">

Client Certificate Authorization

</td>
<td valign="top">

Enter the allowed client certificate Issuer DN entries, separated by commas. The system accepts only certificates issued by these certificate authorities.

</td>
</tr>
</table>



## Processing Tab

Select the *Processing* tab and provide values in the following fields:


<table>
<tr>
<th valign="top">

**Parameter**

</th>
<th valign="top">

**Section**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

*Configuration Source*

</td>
<td valign="top">

Partner Interface Process \(PIP\) Details

</td>
<td valign="top">

Choose the source for the processing configuration:

-   *Dynamic*: The incoming message. The system reads all PIP and security parameters from the Partner Directory at runtime. For more details, see [Dynamic Configuration via Partner Directory](dynamic-configuration-via-partner-directory-a9cc79d.md).
-   *Static*: The channel configuration.



</td>
</tr>
</table>

These fields are visible only when *Configuration Source* is set to *Static*:


<table>
<tr>
<th valign="top">

**Parameter**

</th>
<th valign="top">

**Section**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

*Action Type*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Select the PIP action type:

-   **Single-Action Synchronous Request**
-   **Two-Action Synchronous Request**



</td>
</tr>
<tr>
<td valign="top">

*PIP Code*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the PIP standard code \(for example, `3A4`\).

</td>
</tr>
<tr>
<td valign="top">

*PIP Version*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the PIP version \(for example, `V02.02`\).

</td>
</tr>
<tr>
<td valign="top">

*Business Transaction Activity*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the business transaction activity name.

</td>
</tr>
<tr>
<td valign="top">

*Requesting Action*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the requesting action of the PIP.

</td>
</tr>
<tr>
<td valign="top">

*Current Role*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the current role in the PIP exchange \(for example, `Buyer`\).

</td>
</tr>
<tr>
<td valign="top">

*Partner Role*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the partner role in the PIP exchange \(for example, `Seller`\).

</td>
</tr>
<tr>
<td valign="top">

*Current Business Service Code*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the current business service code.

</td>
</tr>
<tr>
<td valign="top">

*Partner Business Service Code*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the partner business service code.

</td>
</tr>
</table>



## Security Tab

Select the *Security* tab and provide values in the following fields.

> ### Remember:  
> When *Configuration Source* is set to *Dynamic*, the system reads the security parameters directly from the Partner Directory, and you cannot edit the fields below. For more information, see [Dynamic Configuration via Partner Directory](dynamic-configuration-via-partner-directory-a9cc79d.md).


<table>
<tr>
<th valign="top">

**Parameter**

</th>
<th valign="top">

**Section**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

*Validate Signature of Request Message*

</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Choose this option to validate the digital signature on the incoming request message.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias \(Signature Validation\)* 

> ### Note:  
> Only visible when *Validate Signature* is enabled.



</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Enter the private key alias used for signature validation.

</td>
</tr>
<tr>
<td valign="top">

*Decrypt Request Message*

</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Choose this option to decrypt inbound request messages.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias \(Decryption\)* 

> ### Note:  
> Only visible when *Decrypt Request Message* is enabled.



</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Enter the private key alias used for decryption.

</td>
</tr>
<tr>
<td valign="top">

*Encrypt Response Message*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Choose this option to encrypt the outgoing response message.

</td>
</tr>
<tr>
<td valign="top">

*Encryption Scope*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Select which part of the response is encrypted:

-   **Payload**
-   **Payload Container**



</td>
</tr>
<tr>
<td valign="top">

*Encryption Algorithm*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Select the encryption algorithm:

-   *RC2*
-   *3DES*
-   *AES128*
-   *AES256*



</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias \(Encryption\)*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Enter the public key alias used to encrypt the response.

</td>
</tr>
<tr>
<td valign="top">

*Sign Response Message*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Choose this option to digitally sign the outgoing response message.

</td>
</tr>
<tr>
<td valign="top">

*Signing Algorithm*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Select the signing algorithm:

-   *SHA-1*
-   *SHA-256*
-   *SHA-384*
-   *SHA-512*



</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias \(Signing\)*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Enter the public key alias used for signing.

</td>
</tr>
</table>

**Related Information**  


[Configure the RNIF Receiver Adapter](configure-the-rnif-receiver-adapter-556d7e3.md "Configure the RNIF receiver adapter for SAP Cloud Integration to send RosettaNet messages to a trading partner over HTTPS.")

[Dynamic Configuration via Partner Directory](dynamic-configuration-via-partner-directory-a9cc79d.md "Configure the RNIF adapter to resolve Partner Interface Process (PIP) and security settings at runtime by looking up entries in the Partner Directory.")

