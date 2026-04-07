<!-- loio04b392f4fa7942fb9c9a0ba0f00f76e6 -->

# OFTP Adapter for Edge Integration Cell

Use the Odette File Transfer Protocol \(OFTP\) adapter to exchange EDI and business files with partners on your Edge Integration Cell.

The adapter supports the Odette File Transfer Protocol 2 \(OFTP2, RFC 5024\) over Transmission Control Protocol \(TCP\). It provides transport security through Transport Layer Security \(TLS\), and message-level security through Cryptographic Message Syntax \(CMS\) including encryption/decryption, signing/verification, compression/decompression, and secure handshake.

The adapter supports both sender and receiver channels:

-   **Sender channel**: Acts as a TCP server to receive files from partners. The sender adapter listens on configured local ports for inbound partner connections. You can configure optional TLS, which Istio handles.

    > ### Note:  
    > Istio manages the port for the sender adapter and its TLS termination.

-   **Receiver channel**: Acts as a TCP client to send files to partners. The receiver adapter connects and sends data to partner endpoints. You can configure optional TLS in the channels.



## Supported Features

-   You can transfer OFTP 2 data over TCP/IP with optional TLS.
-   You receive message-level security through CMS. This includes encryption and decryption, signature generation and verification, compression and decompression, and a secure handshake.
-   You can use fixed length, variable length, unstructured, and text file formats.
-   Encoding conversion is available for EBCDIC, ISO-8859-1/5/15, or no conversion.
-   You can set a maximum file size constraint in the sender adapter.
-   The sender adapter detects duplicate files.
-   The receiver adapter supports proxy usage \(HTTP or SOCKS\).
-   You can configure the receiver adapter dynamically. You can override most fields per message through headers or exchange properties. For more information, see [Dynamic Configuration and Per-message Overrides](configure-the-oftp-receiver-adapter-8a6b283.md#loio8a6b283dade6419eb907920117983156__dynamic).
-   You can set global adapter parameters for default values. For more information, see [Global Parameters](oftp-adapter-for-edge-integration-cell-04b392f.md#loio04b392f4fa7942fb9c9a0ba0f00f76e6__global).
-   You receive limited acknowledgement support \(EERP, NERP\). For more information, see [ERP Handling](oftp-adapter-for-edge-integration-cell-04b392f.md#loio04b392f4fa7942fb9c9a0ba0f00f76e6__erp).

> ### Restriction:  
> The adapter has some limitations for sender and receiver sides.
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Channel
> 
> </th>
> <th valign="top">
> 
> Limitations
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> Both
> 
> </td>
> <td valign="top">
> 
> -   The adapter does not integrate with the Partner Directory.
> -   B2B monitoring is not supported.
> -   Asynchronous acknowledgements \(ERPs on the sender side\) are not supported.
> -   OFTP restart is not supported.
> -   Automatic certificate exchange and partner information exchange via XML \(PDX\) are not supported.
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Receiver
> 
> </td>
> <td valign="top">
> 
> -   The receiver adapter can only send files. Outbound sessions do not allow receiving files during transmission.
> -   The receiver adapter does not detect duplicate file processing. You can handle this in your integration flow steps.
> 
> 
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> Sender
> 
> </td>
> <td valign="top">
> 
> -   Pull mode is not available for the sender adapter.
> -   Strict client authentication is not supported for the sender adapter.
> -   A separate TSL job is required.
> 
> 
> 
> </td>
> </tr>
> </table>



## Prerequisites

Before you configure the OFTP adapter, complete these prerequisites:

-   Create and maintain security materials in SAP Integration Suite:
    -   Manage keystore certificate aliases for your and your partners' CMS. Also maintain aliases for receiver TLS client authentication.
    -   Set password aliases \(secure parameters\) for your and your partner's Odette session passwords.
    -   Provide optional proxy credentials if you use a proxy in the receiver.

-   Align file format, encoding, and flow control parameters with your partner's OFTP 2 capabilities.
-   To know more about the specific prerequisites for the **sender** channel, see [Configure the OFTP Sender Adapter](configure-the-oftp-sender-adapter-3420f2a.md).



## Security

The OFTP adapter offers security services to protect a virtual file transmission across a hostile network, including confidentiality, integrity, non-repudiation of receipt, non-repudiation of origin, and secure authentication. These services are provided through:

-   Session-level encryption
-   File-level encryption
-   Signed files
-   Signed receipts
-   Session-level authentication
-   OFTP authentication

> ### Note:  
> Session-level protection is achieved by layering the OFTP protocol with TLS.

*Sender Adapter*

The OFTP sender adapter depends on Istio for TLS termination. It uses the same TLS configuration as HTTP-based adapters, including server certificates and trusted certificate authorities. Therefore, the adapter relies on the key pair specified by the Default Virtual Host Key Alias. For more information, see [Deploy the Edge Integration Cell Solution](../deploy-the-edge-integration-cell-solution-ab81b84.md).

The TLS server requests a client certificate but does not require one.

> ### Note:  
> Client authentication using certificates is optional for senders.

*Receiver Adapter*

The OFTP receiver adapter manages TLS communication internally. It supports optional client authentication and hostname verification. You can maintain the trust material and key used for client authentication in the keystore assigned to your Edge node. For more information, see [Managing Keystore Entries](managing-keystore-entries-2dc8942.md).

Message-level protection is based on Cryptographic Message Syntax \(CMS\). To use CMS options, you must maintain a key pair in the keystore. The adapter uses it for secure authentication, file signing, and decryption. You must also upload the partner's public certificate to the keystore. The adapter uses it for file encryption and signature verification. After you maintain the key pair and public certificate in the keystore, configure them in the OFTP adapter as *Own Certificate Alias* and *Partner Certificate Alias*. Your partner must perform similar configuration on their side.



<a name="loio04b392f4fa7942fb9c9a0ba0f00f76e6__erp"/>

## ERP Handling

*Sender Adapter*

The OFTP adapter offers limited support for end-to-end responses \(ERPs\). Supported scenarios include the following:

The sender adapter returns an EERP or NERP to the partner after it processes an inbound file. The returned ERP can be signed if you configure signing in the sender adapter and agree with the partner. The sender adapter uses SHA-256 as the default signing algorithm. You can't change or configure this algorithm.

*Receiver Adapter*

The OFTP adapter on the receiver side collects ERPs received during file transmission. It tries to correlate them to the corresponding outbound transfers. The receiver adapter returns the following aggregated ERP delivery report \(ERPDeliveryReportsPackage\) in the response:

```

    <ERPDeliveryReportsPackage>
      <PackageInfo>
        <PackageID>OUTFILE202601081534580664O2010CUSTOMERO017260560843801</PackageID>
        <CreatedBy></CreatedBy>
        <CreatedOn>2026-01-08T15:35:00.230044208</CreatedOn>
        <Description>ERP delivery reports for this message</Description>
      </PackageInfo>
      <ERPDeliveryReport>
        <CorrelationMPLID>AGlfzqIZbADnZFV3hiW1yWWqMUiX</CorrelationMPLID>
        <EERP>
          <EERPCMD>E</EERPCMD>
          <EERPDSN>outfile</EERPDSN>
          <EERPRSV1></EERPRSV1>
          <EERPDATE>20260108</EERPDATE>
          <EERPTIME>1534580664</EERPTIME>
          <EERPUSER></EERPUSER>
          <EERPDEST>O2010CUSTOMER</EERPDEST>
          <EERPORIG>O017260560843801</EERPORIG>
        </EERP>
      </ERPDeliveryReport>
    </ERPDeliveryReportsPackage>
  
```

Depending on the configuration, the system handles correlation failures in several ways. For example, if the adapter can't find the acknowledged file, the system can ignore the corresponding ERP. It can add the ERP to the response without correlation information. Alternatively, it can end the current session with an error.



<a name="loio04b392f4fa7942fb9c9a0ba0f00f76e6__global"/>

## Global Parameters

The following parameters are available for global configuration of the entire adapter. Some parameters control global settings, others provide default values if not set in the channel configuration.


<table>
<tr>
<th valign="top">

**Global Parameter Name** 

</th>
<th valign="top">

**Default Value** 

</th>
<th valign="top">

Value Range

</th>
<th valign="top">

**Description** 

</th>
</tr>
<tr>
<td valign="top">

`OFTP_ADAPTER_SENDER_MAX_CREDIT_COUN`T

</td>
<td valign="top">

15

</td>
<td valign="top">

1 to 999

</td>
<td valign="top">

The maximum credit count for all sender channels.

</td>
</tr>
<tr>
<td valign="top">

`OFTP_ADAPTER_SENDER_MAX_EXCHANGE_BUFFER_SIZE`

</td>
<td valign="top">

1024

</td>
<td valign="top">

128 to 99999

</td>
<td valign="top">

The maximum exchange buffer size for all sender channels.

</td>
</tr>
<tr>
<td valign="top">

`OFTP_ADAPTER_COMPRESSION_INDICATOR` 

</td>
<td valign="top">

true

</td>
<td valign="top">

true or false

</td>
<td valign="top">

The compression indicator for all channels.

</td>
</tr>
<tr>
<td valign="top">

`OFTP_ADAPTER_SENDER_CARRIAGE_RETURN`

</td>
<td valign="top">

0D

</td>
<td valign="top">

0D or 8D

</td>
<td valign="top">

The carriage return value for all sender channels.

</td>
</tr>
<tr>
<td valign="top">

`OFTP_ADAPTER_TCPIP_TIMEOUT_S`

</td>
<td valign="top">

300

</td>
<td valign="top">

5 to 3600

</td>
<td valign="top">

The timeout period in seconds before a TCP command is received.

</td>
</tr>
<tr>
<td valign="top">

`OFTP_ADAPTER_TCP_BACKLOG`

</td>
<td valign="top">

125

</td>
<td valign="top">

1 to 65535

</td>
<td valign="top">

The maximum queue length for incoming connection requests on the sender’s listening socket. If a connection request arrives when the queue is full, the connection is refused.

> ### Note:  
> This setting is operating system dependent.



</td>
</tr>
<tr>
<td valign="top">

`OFTP_ADAPTER_TRY_LOCK_MS` 

</td>
<td valign="top">

60000

</td>
<td valign="top">

\>= 1000

</td>
<td valign="top">

The timeout period to acquire a cluster-wide lock in milliseconds.

</td>
</tr>
<tr>
<td valign="top">

`OFTP_ADAPTER_SENDER_MAX_THREAD_POOL_SIZE`

</td>
<td valign="top">

50

</td>
<td valign="top">

1 to 200

</td>
<td valign="top">

The maximum thread pool size for the sender adapter.

</td>
</tr>
</table>

You can configure global parameters in the Operations Cockpit. For more information, see [Runtime Parameters](../runtime-parameters-63c5276.md).

> ### Note:  
> The configuration priority for properties is as follows, listed from highest to lowest:
> 
> 1.  Dynamic \(receiver\): `${header.<name>}` or `${property.<name>}`.
> 2.  Channel parameters
> 3.  Global adapter parameters

**Related Information**  


[Configure the OFTP Sender Adapter](configure-the-oftp-sender-adapter-3420f2a.md "Configure the OFTP sender adapter to receive files from partners and act as a Transmission Control Protocol (TCP) server.")

[Configure the OFTP Receiver Adapter](configure-the-oftp-receiver-adapter-8a6b283.md "Configure the OFTP Receiver Adapter to send files to partners and act as a Transmission Control Protocol (TCP) client.")

