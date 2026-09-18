<!-- loio556d7e34c799464894e137db90b3790f -->

# Configure the RNIF Receiver Adapter

Configure the RNIF receiver adapter for SAP Cloud Integration to send RosettaNet messages to a trading partner over HTTPS.

After you create a receiver channel and select the RNIF receiver adapter, configure the following attributes:



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

Target Endpoint

</td>
<td valign="top">

Enter the target URL of the partner endpoint for outbound requests. Use HTTPS for secured communication.

</td>
</tr>
<tr>
<td valign="top">

*Authorization*

</td>
<td valign="top">

Target Endpoint

</td>
<td valign="top">

Select the authorization type for outbound requests:

-   *Basic Authentication*. Send user/password credentials.
-   *Client Certificate*. Authenticate using a client certificate.



</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

> ### Note:  
> Only visible when *Basic Authentication* is selected as the authorization method.



</td>
<td valign="top">

Target Endpoint

</td>
<td valign="top">

Enter the name of the user credentials artifact deployed on the tenant.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias* 

> ### Note:  
> Only visible when *Client Certificate* is selected as the authorization method.



</td>
<td valign="top">

Target Endpoint

</td>
<td valign="top">

Enter the private key alias from the keystore used for certificate-based authentication.

</td>
</tr>
<tr>
<td valign="top">

*Socket Timeout \(in ms\)*

</td>
<td valign="top">

Target Endpoint

</td>
<td valign="top">

The time, in milliseconds, that you wait for a connection or socket to open before timing out. A value of zero means you wait indefinitely. The default value is `300,000`.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)*

</td>
<td valign="top">

Target Endpoint

</td>
<td valign="top">

The time, in milliseconds, that you wait for a response before timing out. A value of zero means you wait indefinitely. The default value is `300,000`.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

Proxy Settings

</td>
<td valign="top">

For the Cloud Integration runtime, select the proxy type to connect to the receiver system:

-   *Internet*. Connects to a cloud system.
-   *On-Premise*. Connects to an on-premise system.

For the Edge Integration Cell runtime, select:

-   *Internet*. Connects to a cloud system.
-   *Manual*. Enter the Proxy Host and Proxy Port in the corresponding fields.



</td>
</tr>
<tr>
<td valign="top">

*Location ID* 

> ### Note:  
> Only visible when *On-Premise* is selected as the Proxy Type.



</td>
<td valign="top">

Proxy Settings

</td>
<td valign="top">

Enter the Location ID configured in the SAP Cloud Connector. Leave empty if the default location is used.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Host* 

> ### Note:  
> Only visible when *Manual* is selected as the Proxy Type.



</td>
<td valign="top">

Proxy Settings

</td>
<td valign="top">

Enter the host name of the manual proxy.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Port* 

> ### Note:  
> Only visible when *Manual* is selected as the Proxy Type.



</td>
<td valign="top">

Proxy Settings

</td>
<td valign="top">

Enter the port of the manual proxy.

</td>
</tr>
</table>



## Processing Tab

Select the *Processing* tab and enter these values:


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

Partner Interface Process Details

</td>
<td valign="top">

Select how to derive the processing configuration:

-   *Dynamic*. Derive it at runtime from message headers or Camel exchange parameters.
-   *Static*. Derive it from the channel configuration.



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

Select the PIP \(Partner Interface Process\) action type:

-   *Single-Action Synchronous Request*
-   *Two-Action Synchronous Request*



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

Enter the PIP code.

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

Enter the PIP version.

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

Enter the requesting action.

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

Enter the current role in the PIP exchange.

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

Enter the partner role in the PIP exchange.

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
<tr>
<td valign="top">

*Process Name*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the process name.

</td>
</tr>
<tr>
<td valign="top">

*Transaction Name*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the transaction name.

</td>
</tr>
<tr>
<td valign="top">

*Current Classification Code*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the current classification code.

</td>
</tr>
<tr>
<td valign="top">

*Partner Classification Code*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the partner classification code.

</td>
</tr>
</table>



## Security Tab

Select the *Security* tab and provide values in these fields.

> ### Remember:  
> When *Configuration Source* is set to *Dynamic*, the system reads the security parameters directly from the Partner Directory, and you cannot edit the fields below. For more information, see [Dynamic Configuration via Partner Directory](dynamic-configuration-via-partner-directory-a9cc79d.md).


<table>
<tr>
<th valign="top">

**Field**

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

*Sign Request Message*

</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Choose this option to digitally sign the outbound request.

</td>
</tr>
<tr>
<td valign="top">

*Signing Algorithm*

</td>
<td valign="top">

Request Security

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

*Public Key Alias \(Request Signing\)*

</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Enter the public key alias used to sign the request.

</td>
</tr>
<tr>
<td valign="top">

*Encrypt Request Message*

</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Choose this option to encrypt the outbound request.

</td>
</tr>
<tr>
<td valign="top">

*Encryption Scope*

</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Select which part of the request is encrypted:

-   *Payload*
-   Payload Container



</td>
</tr>
<tr>
<td valign="top">

*Encryption Algorithm*

</td>
<td valign="top">

Request Security

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

*Public Key Alias \(Request Encryption\)*

</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Enter the public key alias used to encrypt the request.

</td>
</tr>
<tr>
<td valign="top">

*Decrypt Response Message*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Choose this option to decrypt the inbound response message.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias \(Response Decryption\)*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Enter the private key alias used for response decryption.

</td>
</tr>
<tr>
<td valign="top">

*Verify Response Message*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Choose this option to verify the digital signature of the inbound response.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias \(Response Verification\)*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Enter the private key alias used for signature verification.

</td>
</tr>
</table>

**Related Information**  


[Dynamic Configuration via Partner Directory](dynamic-configuration-via-partner-directory-a9cc79d.md "Configure the RNIF adapter to resolve Partner Interface Process (PIP) and security settings at runtime by looking up entries in the Partner Directory.")

[Configure the RNIF Sender Adapter](configure-the-rnif-sender-adapter-8dbb4ac.md "Configure the RNIF sender adapter for SAP Cloud Integration to receive RosettaNet messages from a trading partner over HTTPS.")

