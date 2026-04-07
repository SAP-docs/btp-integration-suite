<!-- loio8a6b283dade6419eb907920117983156 -->

# Configure the OFTP Receiver Adapter

Configure the OFTP Receiver Adapter to send files to partners and act as a Transmission Control Protocol \(TCP\) client.



The OFTP receiver adapter acts as an initiator according to the OFTP2 specification. The adapters connect to the partners' configured hosts and ports.

> ### Note:  
> The receiver adapter can't receive files during transmission. File receiving and file transmitting can't occur at the same time.

Before you configure the OFTP Receiver Adapter, make sure that you have completed all the prerequisites listed in [OFTP Adapter for Edge Integration Cell](https://help.sap.com/docs/integration-suite/sap-integration-suite/oftp-adapter-for-edge-integration-cell?version=CLOUD#prerequisites).



## Supported Features

-   **File handling**: Supports unstructured \(binary\), fixed length \(with sentence length\), Text \(with carriage return\), and variable formats. Offers encoding conversion options, including no conversion, ISO-8859-1, ISO-8859-5, ISO-8859-15, and EBCDIC.

-   **Security**: Uses Cryptographic Message Syntax \(CMS\) for outbound encryption, signing, and decompression handshake. It also supports secure OFTP handshake, TLS, client authentication and hostname verification.

-   **Acknowledgement \(ERP\) support**: The adapter can request signed ERP messages. When it receives an ERP \(EERP or NERP\), the adapter tries to correlate them to processed messages or files and adds them to an `ERPDeliveryReportsPackage` XML in the response.

-   **Proxy**: Supports optional proxy usage for HTTP or SOCKS protocols.

-   **Dynamic Configuration**: Provides dynamic configuration. You can override most fields for each message through headers or exchange properties. See [Dynamic Configuration and Per-message Overrides](configure-the-oftp-receiver-adapter-8a6b283.md#loio8a6b283dade6419eb907920117983156__dynamic).


> ### Note:  
> There is no built-in duplicate detection. You can handle this in the integration flow if needed. The adapter generates unique timestamps for sent files.



## Configuring the OFTP Receiver Adapter

Once you have created a receiver channel and selected the OFTP Adapter, you can configure the following attributes. See [Overview of Integration Flow Editor](https://help.sap.com/docs/integration-suite/sap-integration-suite/overview-of-integration-flow-editor?locale=en-US&state=DRAFT&version=CLOUD).

> ### Note:  
> Global parameters provide default values where channel settings are unspecified.

Select the *Connection* tab and enter values in these fields:




<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Section

</th>
<th valign="top">

Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Partner Host\** 

</td>
<td valign="top">

TCP/IP SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Host name or IP address of the partner’s OFTP 2 server.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Partner Port\** 

</td>
<td valign="top">

TCP/IP SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

TCP port of the partner’s OFTP 2 server.

Typically, the default port number for plain TCP connections is 3305 and 6619 for TLS connections.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Own Odette-ID\**



</td>
<td valign="top">

CONNECTION SETTINGS



</td>
<td valign="top">

Text

</td>
<td valign="top">

Your system’s Odette identifier \(as initiator\), presented in SSID.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Partner Odette-ID\**



</td>
<td valign="top">

CONNECTION SETTINGS



</td>
<td valign="top">

Text

</td>
<td valign="top">

Expected partner's Odette identifier in SSID.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Final File Destination \(SFIDDEST\)*



</td>
<td valign="top">

CONNECTION SETTINGS



</td>
<td valign="top">

Text

</td>
<td valign="top">

Expected partner's Odette identifier in SSID. This parameter determines the destination of the final recipient of the virtual file.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*File Originator \(SFIDORIG\)* 



</td>
<td valign="top">

CONNECTION SETTINGS



</td>
<td valign="top">

Text

</td>
<td valign="top">

Expected originator for the virtual file. This parameter determines the originator of the virtual file.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Own Password Alias \(Sender\)\**



</td>
<td valign="top">

CONNECTION SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Alias for your Odette session password stored in the secure store. Used when the adapter operates as responder.

> ### Note:  
> The maximum allowed length for the password is 8 characters.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Partner Password Alias \(Receiver\)\** 



</td>
<td valign="top">

CONNECTION SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Alias for the partner’s Odette session password. Used to validate mutual credentials

> ### Note:  
> The maximum allowed length for the password is 8 characters.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Connect with TLS*

</td>
<td valign="top">

TLS SETTINGS

</td>
<td valign="top">

-   *Disable*
-   *Enable*
-   *Dynamic*



</td>
<td valign="top">

Select *Enable* to use TLS for transport connections to partner hosts.

Select *Dynamic* to allow per-message overrides by using the `SAP_OFTP_Outbound_TLS` header.

</td>
</tr>
<tr>
<td valign="top">

*Client Authentication*

> ### Note:  
> Only visible if *Connect with TLS* is *Enable* or *Dynamic*.



</td>
<td valign="top">

TLS SETTINGS

</td>
<td valign="top">

-   *Disable*
-   *Enable*
-   *Dynamic*



</td>
<td valign="top">

Select *Enable* to perform client authentication by validating the security certificates with your private key alias.

Select *Dynamic* to allow per-message override by using the `SAP_OFTP_Outbound_Client_Authentication`header.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias\**

> ### Note:  
> Only visible if *Client Authentication* is *Enable* or *Dynamic*.



</td>
<td valign="top">

TLS SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Alias of your client TLS certificate/private key.



> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Verify Hostname*

> ### Note:  
> Only visible if *Connect with TLS* is *Enable* or *Dynamic*.



</td>
<td valign="top">

TLS SETTINGS

</td>
<td valign="top">

-   *Disable*
-   *Enable*
-   *Dynamic*



</td>
<td valign="top">

This parameter lets adapters verify the hostnames of the systems that send messages.



Select *Dynamic* to allow per-message override by using the `SAP_OFTP_Outbound_Verify_Hostname` header.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Protocol*

</td>
<td valign="top">

PROXY SETTINGS

</td>
<td valign="top">

-   *None*
-   *HTTP*
-   *SOCKS4*
-   *SOCKS5*
-   *Dynamic*



</td>
<td valign="top">

Enable communication via proxy.



Select *Dynamic* to allow per-message override by using the `SAP_OFTP_Outbound_Proxy_Protocol`header.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Host\**

> ### Note:  
> Visible for all *Proxy Type* options except *None*.



</td>
<td valign="top">

PROXY SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Host name or IP of proxy.



> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Proxy Port\** 

> ### Note:  
> Visible for all *Proxy Type* options except *None*.



</td>
<td valign="top">

PROXY SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

The proxy port.



> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Proxy Credential Name*

> ### Note:  
> Visible for all *Proxy Type* options except *None*.



</td>
<td valign="top">

PROXY SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Enter the credential name used for proxy authentication.



> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in s\)*

> ### Note:  
> Visible for all *Proxy Type* options except *None*.



</td>
<td valign="top">

PROXY SETTINGS

</td>
<td valign="top">

Positive number

> ### Note:  
> The default value is 30.



</td>
<td valign="top">

Timeout for proxy connection.



> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or a property.



</td>
</tr>
</table>



Select the *Processing* tab and enter values in these fields:


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Section

</th>
<th valign="top">

Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Outgoing Virtual File Dataset Name\** 

</td>
<td valign="top">

FILE SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Use this parameter to set the Virtual File Dataset Name in SFID for outgoing files.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or property.



</td>
</tr>
<tr>
<td valign="top">

*Encoding* 

</td>
<td valign="top">

FILE SETTINGS

</td>
<td valign="top">

-   *No Conversion*
-   *EBCDIC*
-   *ISO-8859-1*
-   *ISO-8859-5*
-   *ISO-8859-15*
-   *Dynamic*



</td>
<td valign="top">

Use this parameter to select the file encoding format before transmission. The available formats are:

-   EBCDIC
-   ISO-8859-1
-   ISO-8859-5
-   ISO-8859-15

To override the encoding per message, select *Dynamic* and use the header `SAP_OFTP_Outbound_File_Encoding`.

</td>
</tr>
<tr>
<td valign="top">

*File Format*

</td>
<td valign="top">

FILE SETTINGS

</td>
<td valign="top">

-   *Unstructured*
-   *Fixed length*
-   *Text* 
-   *Variable*
-   *Dynamic*



</td>
<td valign="top">

Use this parameter to set the format of outgoing files. The available options are:

-   *Unstructured*: creates files with raw binary content.
-   *Fixed length*: creates files with records of fixed length. Set the *Sentence Length* parameter.
-   *Text*: creates text files that use line delimiters. Set the *Carriage Return* option.
-   *Variable*: creates files with variable-length records supported by OFTP 2.

To override the file format per message, select *Dynamic* and use the header `SAP_OFTP_Outbound_File_Format`.

</td>
</tr>
<tr>
<td valign="top">

*Sentence Length*

> ### Note:  
> Only visible if *File Format* is *Fixed Length* or *Dynamic*.



</td>
<td valign="top">

FILE SETTINGS

</td>
<td valign="top">

Positive number

</td>
<td valign="top">

Enter the record length in bytes for files that use the fixed length format.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or property.



</td>
</tr>
<tr>
<td valign="top">

*Description* 

</td>
<td valign="top">

FILE SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Enter a free text description to store in SFID.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or property.



</td>
</tr>
<tr>
<td valign="top">

*Carriage Return* 

</td>
<td valign="top">

TECHNICAL SETTINGS

</td>
<td valign="top">

-   *0D*
-   *8D*
-   *Dynamic*



</td>
<td valign="top">

Use the value that matches your partner’s requirements for text file lines.

To override this value per message, select *Dynamic* and use the header `SAP_OFTP_Outbound_Carriage_Return`.

</td>
</tr>
<tr>
<td valign="top">

*Max Credit Count\** 

</td>
<td valign="top">

TECHNICAL SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Set the maximum credit count for the pipeline to negotiate with your partner. The valid range is 1 to 999. The default value is 15.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or property.



</td>
</tr>
<tr>
<td valign="top">

*Max Exchange Buffer Size\** 

</td>
<td valign="top">

TECHNICAL SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Set the maximum exchange buffer size for the pipeline to negotiate with your partner. The valid range is 128 to 99999. The default value is 128.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or property.



</td>
</tr>
<tr>
<td valign="top">

*User Field SSID* 

</td>
<td valign="top">

TECHNICAL SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Specify a custom SSID user field \(corresponds to SSIDUSER\).

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or property.



</td>
</tr>
<tr>
<td valign="top">

*User Field SFID* 

</td>
<td valign="top">

TECHNICAL SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Specify a custom SFID user field.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to read the value dynamically from a header or property.



</td>
</tr>
</table>



Select the *Security* tab and provide values in the fields as follows.


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Section

</th>
<th valign="top">

Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*CMS Settings*

</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

-   *Disable*
-   *Enable*
-   *Dynamic*



</td>
<td valign="top">

Use this setting to enable message-level security with CMS.

Select *Dynamic* to allow a per-message override using the `SAP_OFTP_Outbound_CMS`.

</td>
</tr>
<tr>
<td valign="top">

*Own Certificate Alias*

> ### Note:  
> Only visible if *CMS Settings* is *Enable* or *Dynamic*.



</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Specify the alias for your certificates or private keys used for signing.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to retrieve the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Partner Certificate Alias*

> ### Note:  
> Only visible if *CMS Settings* is *Enable* or *Dynamic*.



</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Specify the alias of the partner’s certificate used for encryption.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to retrieve the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Encryption Algorithm*

</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

-   *None*
-   *Dynamic*
-   *AES\_256\_CBC*
-   *3DES\_EDE\_CBC\_3K*



</td>
<td valign="top">

Select the encryption algorithm if you need encryption.

> ### Note:  
> The system supports 3DES\_EDE\_CBC\_3K only for compliance with the OFTP2 specification. Using this algorithm in production environments isn't recommended.

Choose *Dynamic* to allow a per-message override using the header `SAP_OFTP_Outbound_Encryption_Algorithm}`.

</td>
</tr>
<tr>
<td valign="top">

*Signing Algorithm*

> ### Note:  
> Only visible if *CMS Settings* is *Enable* or *Dynamic*.



</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

-   *None*
-   *Dynamic*
-   *SHA1*
-   *SHA224*
-   *SHA256*
-   *SHA384*
-   *SHA512*



</td>
<td valign="top">

Choose the signing algorithm if you need signing.

> ### Note:  
> The SHA-1 algorithm is included only for compliance with the OFTP2 specification. Using this algorithm in production environments is not recommended.

Select *Dynamic* to allow a per-message override using header `SAP_OFTP_Outbound_Signing_Algorithm`.

</td>
</tr>
<tr>
<td valign="top">

*Secure Handshake*

> ### Note:  
> Only visible if *CMS Settings* is *Enable* or *Dynamic*.



</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

-   *Disable*
-   *Enable*
-   *Dynamic*



</td>
<td valign="top">

Enable to perform an OFTP 2 secure handshake with certificate validation.

Select *Dynamic* to allow a per-message override using header `SAP_OFTP_Outbound_Secure_Handshake`.

</td>
</tr>
<tr>
<td valign="top">

*File Compression*

</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

-   *Disable*
-   *Enable*
-   *Dynamic*



</td>
<td valign="top">

Compress outbound files at the CMS layer.

Select *Dynamic* to allow a per-message override using header `SAP_OFTP_Outbound_File_Compression`.

</td>
</tr>
<tr>
<td valign="top">

*Request Signed ERP* 

</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

-   *Disable*
-   *Enable*
-   *Dynamic*



</td>
<td valign="top">

Request the partner to send a signed end-to-end response.

Select *Dynamic* to allow a per-message override using header `SAP_OFTP_Outbound_Request_Signed_ERP`.

</td>
</tr>
</table>

Select the *ERP* tab and provide values in the fields as follows.


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Section

</th>
<th valign="top">

Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*ERP Persist Time \(in d\)\** 

</td>
<td valign="top">

END-TO-END RESPONSE \(EERP/NERP\) SETTINGS

</td>
<td valign="top">

Positive number

</td>
<td valign="top">

Specify how long to retain data for ERP acknowledgment correlation.

> ### Note:  
> You can enter `${header.headername}` or `${property.propertyname}` to retrieve the value dynamically from a header or a property.



</td>
</tr>
<tr>
<td valign="top">

*Unexpected ERP Handling*

</td>
<td valign="top">

END-TO-END RESPONSE \(EERP/NERP\) SETTINGS

</td>
<td valign="top">

-   *Ignore*
-   *End Session*
-   *Add to ERP XML*
-   *Dynamic*



</td>
<td valign="top">

Select how to handle ERPs that don't match any outstanding transfers. No correlation information is found in these cases. Available options are:

-   *Ignore*: The system ignores the ERP.
-   *End Session*: The system ends the current session and provides a reason for not accepting the ERP.
-   *Add to ERP XML*: The system adds the ERP to the response ERP list without correlation information.

Select *Dynamic* to allow a per-message override by using the header `SAP_OFTP_Outbound_Unexpected_ERP_Handling`.

</td>
</tr>
<tr>
<td valign="top">

*Fail Message on Negative ERP*

</td>
<td valign="top">

END-TO-END RESPONSE \(EERP/NERP\) SETTINGS

</td>
<td valign="top">

-   *Disable*
-   *Enable*
-   *Dynamic*



</td>
<td valign="top">

If this parameter is enabled and the system receives an ERP for the current session, it processes negative ERPs as failures.

Select *Dynamic* to allow a per-message override using header `SAP_OFTP_Outbound_Fail_On_Negative_ERP`.

</td>
</tr>
</table>



<a name="loio8a6b283dade6419eb907920117983156__dynamic"/>

## Dynamic Configuration and Per-message Overrides

You can resolve most receiver properties dynamically by using message headers or exchange properties. Use expressions like `${header.headername}` or `${property.propertyname`\} in property fields.

For drop-down fields other than *Text* fields, select *Dynamic*. Then, add the following headers and properties in previous integration flow steps:

**Fixed Header Names**


<table>
<tr>
<th valign="top">

Header Name

</th>
<th valign="top">

Value Range

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_Proxy_Protocol`

</td>
<td valign="top">

-   None
-   HTTP
-   SOCKS4
-   SOCKS5



</td>
<td valign="top">

Proxy type

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_File_Format`

</td>
<td valign="top">

-   Unstructured
-   Fixed Length
-   Text
-   Variable



</td>
<td valign="top">

File format

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_File_Encoding`

</td>
<td valign="top">

-   None
-   ebcdic
-   iso88591
-   iso88595
-   iso885915



</td>
<td valign="top">

File encoding

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_Carriage_Return`

</td>
<td valign="top">

-   0D
-   8D



</td>
<td valign="top">

Carriage return type

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_Signing_Algorithm`

</td>
<td valign="top">

-   SHA1
-   SHA224
-   SHA256
-   SHA384
-   SHA512
-   None



</td>
<td valign="top">

Signing algorithm

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_Encryption_Algorithm`

</td>
<td valign="top">

-   AES\_256\_CBC
-   3DES\_EDE\_CBC\_3K
-   None



</td>
<td valign="top">

Encryption algorithm

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_Unexpected_ERP_Handling`

</td>
<td valign="top">

-   Ignore
-   End Session
-   Add to ERP XML



</td>
<td valign="top">

Handling of ERPs without correlation information

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_Fail_On_Negative_ERP`

</td>
<td valign="top">

-   Enable
-   Disable



</td>
<td valign="top">

Controls message processing when the system receives a negative ERP for files in the current session.

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_TLS`

</td>
<td valign="top">

-   Enable
-   Disable



</td>
<td valign="top">

TLS communication in the receiver

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_Client_Authentication`

</td>
<td valign="top">

-   Enable
-   Disable



</td>
<td valign="top">

TLS client authentication in the receiver

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_Verify_Hostname`

</td>
<td valign="top">

-   Enable
-   Disable



</td>
<td valign="top">

Host name verification in the receiver

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_CMS`

</td>
<td valign="top">

-   Enable
-   Disable



</td>
<td valign="top">

Message-level security \(CMS\) in the receiver

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_Secure_Handshake`

</td>
<td valign="top">

-   Enable
-   Disable



</td>
<td valign="top">

Secure handshake in the receiver

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_File_Compression`

</td>
<td valign="top">

-   Enable
-   Disable



</td>
<td valign="top">

File compression in the receiver

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Outbound_Request_Signed_ERP`

</td>
<td valign="top">

-   Enable
-   Disable



</td>
<td valign="top">

Request for signed ERPs

</td>
</tr>
</table>

**Related Information**  


[OFTP Adapter for Edge Integration Cell](oftp-adapter-for-edge-integration-cell-04b392f.md "Use the Odette File Transfer Protocol (OFTP) adapter to exchange EDI and business files with partners on your Edge Integration Cell.")

[Configure the OFTP Sender Adapter](configure-the-oftp-sender-adapter-3420f2a.md "Configure the OFTP sender adapter to receive files from partners and act as a Transmission Control Protocol (TCP) server.")

