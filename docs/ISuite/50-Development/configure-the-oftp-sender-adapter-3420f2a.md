<!-- loio3420f2aab78f441d840cf8331de5893b -->

# Configure the OFTP Sender Adapter

Configure the OFTP sender adapter to receive files from partners and act as a Transmission Control Protocol \(TCP\) server.

The OFTP sender adapter acts as a responder according to the OFTP 2 specification. It listens on the local ports you set for inbound connections.

The sender adapters use multi-step integration flow filtering. This process includes transport \(port\), session, and file filtering and matching. If multiple sender channels listen on the same port, make sure that the Partner Odette IDs are different or use the same values for the required fields across channels. For more information, see [Channel Matching for Incoming Files](configure-the-oftp-sender-adapter-3420f2a.md#loio3420f2aab78f441d840cf8331de5893b__matching).



## Prerequisites

Before you configure the OFTP Sender Adapter, make sure that you have completed all the prerequisites listed in [OFTP Adapter for Edge Integration Cell](https://help.sap.com/docs/integration-suite/sap-integration-suite/oftp-adapter-for-edge-integration-cell?version=CLOUD#prerequisites).

Specific prerequisites for the sender channel:

-   Configure and open the required TCP ports between your Edge Integration Cell and partner network endpoints. To open ports in Edge Integration Cells, specify them in the *Additional Ports* or *Additional Ports TLS* parameters when you deploy your Edge Integration Cell solution. For more information, see [Deploy the Edge Integration Cell Solution](../deploy-the-edge-integration-cell-solution-ab81b84.md).

    > ### Note:  
    > In existing installations, manage ports through Istio solution properties

-   TLS communication is recommended to ensure transport security. Since the OFTP sender adapter uses the same TLS setup as the *Default Virtual Host*, you must configure the *Default Virtual Host* correctly before you use TLS. For more information, see [Deploy the Edge Integration Cell Solution](../deploy-the-edge-integration-cell-solution-ab81b84.md), and [Istio / Understanding TLS Configuration](https://istio.io/latest/docs/ops/configuration/traffic-management/tls-configuration/).
-   If you rely on Enterprise Messaging for store, or JMS queues for delivery assurance, configure them accordingly. For more information, see [Managing Message Queues](managing-message-queues-cdcce24.md) and [Activating Enterprise Messaging](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/activating-enterprise-messaging?version=Cloud).



## Configuring the OFTP Sender Adapter

After you create a sender channel and select the OFTP Adapter, configure the following attributes. For details, see [Overview of Integration Flow Editor](https://help.sap.com/docs/integration-suite/sap-integration-suite/overview-of-integration-flow-editor?locale=en-US&state=DRAFT&version=CLOUD).

Select the *Connection* tab and enter values in these fields:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Section

</th>
<th valign="top">

Values

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Local Port\** 

</td>
<td valign="top">

TCP/IP SETTINGS

</td>
<td valign="top">

Positive integer

</td>
<td valign="top">

TCP port \(with or without Enabled TLS\) on which the channel binds and listens for inbound OFTP 2 connections.

Common default port numbers are 3305 for plain connections and 6619 for TLS connections.

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

Your system’s Odette identifier for responder, as presented in SSID.

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

Expected destination for the virtual file \(expected SFID destination ID\).

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

Expected originator for the virtual file \(expected SFID originator ID\).

</td>
</tr>
<tr>
<td valign="top">

*Own Password Alias \(Receiver\)\** 

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



</td>
</tr>
<tr>
<td valign="top">

*Partner Password Alias \(Sender\)\** 

</td>
<td valign="top">

CONNECTION SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Alias for the partner’s Odette session password. Used to validate the partner’s SSID credentials.

> ### Note:  
> The maximum allowed length for the password is 8 characters.



</td>
</tr>
</table>

Select the *Processing* tab and enter values in these fields:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Section

</th>
<th valign="top">

Values

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Expected Virtual File Dataset Name\**

</td>
<td valign="top">

FILE SETTINGS

</td>
<td valign="top">

Text

</td>
<td valign="top">

The dataset names of the virtual files to match and accept.

> ### Note:  
> This field supports regular expressions.



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
-   *ISO-8859-1*
-   *ISO-8859-5*
-   *ISO-8859-15*
-   *EBCDIC*



</td>
<td valign="top">

File encoding conversion.

Use *No Conversion* to keep the original bytes, and specific encodings for text-format payloads that need conversion.

</td>
</tr>
<tr>
<td valign="top">

*Max File Size \(MB\)\**

</td>
<td valign="top">

FILE SETTINGS

</td>
<td valign="top">

Positive integer

> ### Tip:  
> Use a maximum of 100 MB.



</td>
<td valign="top">

The adapter rejects files that are larger than this size.

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

Custom SSID user field which corresponds to SSIDUSER.

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

Custom SFID user field.

</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check* 

</td>
<td valign="top">

TECHNICAL SETTINGS

</td>
<td valign="top">

-   *Enable*
-   *Disable*



</td>
<td valign="top">

Enable duplicate handling. The system checks if the current file received by the sender channel matches a previously processed file. If a duplicate exists, the file is rejected.

</td>
</tr>
<tr>
<td valign="top">

*Duplicate Expiration Period \(in days\)*

> ### Note:  
> Only visible if *Duplicate Check* is selected.



</td>
<td valign="top">

TECHNICAL SETTINGS

</td>
<td valign="top">

Positive number.

> ### Note:  
> The default is 30 days.



</td>
<td valign="top">

The duplicate check retention period, in days. This field controls how long information is kept for duplicate checking.

</td>
</tr>
</table>

Select the *Security* tab and enter values in these fields:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Section

</th>
<th valign="top">

Values

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



</td>
<td valign="top">

When enabled, you can configure file decryption, signature verification, and secure handshake.

</td>
</tr>
<tr>
<td valign="top">

*Own Certificate Alias\**

> ### Note:  
> Only visible if *CMS Settings* is not Enabled.



</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Alias for your certificate and private key. Used for signing ERP or decrypting inbound content.

> ### Remember:  
> You need to create and maintain certificate aliases \(keystore\) as security material in SAP Integration Suite.



</td>
</tr>
<tr>
<td valign="top">

*Partner Certificate Alias\**

> ### Note:  
> Only visible if *CMS Settings* is not Enabled.



</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

Text

</td>
<td valign="top">

Alias for the partner’s certificate. Used for signature verification or content decryption.

> ### Remember:  
> You need to create and maintain certificate aliases \(keystore\) as security material in SAP Integration Suite.



</td>
</tr>
<tr>
<td valign="top">

*File Decryption*

> ### Note:  
> Only visible if *CMS Settings* is not Enabled.



</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

-   *Disable*
-   *Enable*



</td>
<td valign="top">

Enable if the partner encrypts inbound files.

</td>
</tr>
<tr>
<td valign="top">

*Signature Verification*

> ### Note:  
> Only visible if *CMS Settings* is not Enabled.



</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

-   *Disable*
-   *Enable*



</td>
<td valign="top">

Enable to verify partner signatures on inbound files.

</td>
</tr>
<tr>
<td valign="top">

*Secure Handshake*

> ### Note:  
> Only visible if *CMS Settings* is not Enabled.



</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

-   *Disable*
-   *Enable*



</td>
<td valign="top">

This option enables OFTP 2 secure authentication for certificate-based session validation.

</td>
</tr>
<tr>
<td valign="top">

*File Decompression* 

</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

-   *Disable*
-   *Enable*



</td>
<td valign="top">

Enable if the partner compresses CMS payloads.

</td>
</tr>
<tr>
<td valign="top">

*Send Signed ERP* 

</td>
<td valign="top">

CRYPTOGRAPHIC MESSAGE SYNTAX PARAMETERS

</td>
<td valign="top">

-   *Disable*
-   *Enable*



</td>
<td valign="top">

When enabled, the adapter sends signed end-to-end responses \(ERP\) as required by the partner.

</td>
</tr>
</table>

Select the *Delivery Assurance* tab and enter values in these fields:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Section

</th>
<th valign="top">

Values

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Quality of Service*

</td>
<td valign="top">

DELIVERY ASSURANCE PARAMETERS

</td>
<td valign="top">

-   *Best Effort*

    The message is sent synchronously; this means that the tenant waits for a response before it continues processing.

    No temporary storage of the message needs to be configured, as message request and response are processed immediately after another.

-   *At Least Once*

    The message is sent asynchronously. This means that the tenant does not wait for a response before continuing processing. It is expected that the receiver guarantees that the message is processed exactly once.

    This option guarantees that the message is processed at least once on the tenant. If a message with identical message ID is received multiple times from a sender, all of them will be processed.

    If you choose this option, the message needs to be temporarily stored on the tenant \(in the storage configured under *Temporary Storage*\). As soon as the message is stored there, the sender receives successfully received status message. If an error occurs, the message is retried from the temporary storage.

-   *Exactly Once* \(Only possible if as *Temporary Storage* the option *Data Store* is selected\)

    The message is sent asynchronously. This means that the tenant does not wait for a response before continuing processing.

    This option guarantees that the message is processed exactly once on the tenant. If a message with identical message ID is received multiple times from a sender, only the first one will be processed. The subsequent messages can be identified as duplicates and will not be processed.

    If you choose this option, the message needs to be temporarily stored on the tenant \(in the storage configured under *Temporary Storage*\). As soon as the message is stored there, the sender receives successfully received status message. If an error occurs, the message is retried from the temporary storage.




</td>
<td valign="top">

Defines how the message is processed by the tenant.

</td>
</tr>
<tr>
<td valign="top">

*Temporary Storage*

\(only if as *Quality of Service* the option *Exactly Once* or *At Least Once* is selected\)

</td>
<td valign="top">

DELIVERY ASSURANCE PARAMETERS

</td>
<td valign="top">

-   *Data Store*

    The message is temporarily stored in the database of the tenant \(in case of an error\). In case of successful message processing, the message is immediately removed from the data store.

    You can monitor the content of the data store in the *Monitor* section of the Web UI under *Manage Stores* in the *Data Stores* tile.

    > ### Note:  
    > The data store name is automatically generated and contains the following parts:
    > 
    > ***<name of participant connected with OFTP adapter\>\_< OFTP channel name\>***
    > 
    > This automatically generated name is subject to a length restriction and must be no more than 40 characters \(including the underscore\). If the data store name exceeds this limit, you must shorten the participant name or channel name accordingly.
    > 
    > Below the data store name, you find a reference to the associated integration flow in the following form: ***<integration flow name\>/OFTP***

-   *JMS Queue*

    The message is stored temporarily in a JMS queue on the configured message broker.

    If possible, use this option as it comes with a better performance.

    You can monitor the content of the data store in the *Monitor* section of the Web UI under *Manage Stores* in the *Message Queues* tile.

    > ### Note:  
    > The name of the JMS queue is automatically generated and contains the following parts:
    > 
    > ***OFTP.<Integration Flow Name\>.<Channel Name\>.<Guide\>***

    > ### Note:  
    > This option is only available if you have an *Enterprise Edition* license.




</td>
<td valign="top">

Temporary storage location for messages that are processed asynchronously. Messages for which processing runs into an error can be retried from the temporary storage.

</td>
</tr>
<tr>
<td valign="top">

*Lock Timeout \(in min\)*

\(only configurable if *Data Store* is selected\)

</td>
<td valign="top">

DELIVERY ASSURANCE PARAMETERS

</td>
<td valign="top">

 

</td>
<td valign="top">

Enter a value for the retry timeout of the in-progress repository.

</td>
</tr>
<tr>
<td valign="top">

*Retry Interval \(in min\)*

</td>
<td valign="top">

DELIVERY ASSURANCE PARAMETERS

</td>
<td valign="top">

 

</td>
<td valign="top">

Enter a value for the amount of time to wait before retrying message delivery.

</td>
</tr>
<tr>
<td valign="top">

*Exponential Backoff*

</td>
<td valign="top">

DELIVERY ASSURANCE PARAMETERS

</td>
<td valign="top">

 

</td>
<td valign="top">

Select this option to double the retry interval after each unsuccessful retry.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Retry Interval \(in min\)*

\(only configurable when *Exponential Backoff* is selected\)

</td>
<td valign="top">

DELIVERY ASSURANCE PARAMETERS

</td>
<td valign="top">

 

</td>
<td valign="top">

You can set an upper limit on that value to avoid an endless increase of the retry interval. The default value is 60 minutes. The minimum value is 10 minutes.

</td>
</tr>
<tr>
<td valign="top">

*Dead-Letter Queue*

\(only if as *Temporary Storage* the option *JMS Queue* is selected\)

</td>
<td valign="top">

DELIVERY ASSURANCE PARAMETERS

</td>
<td valign="top">

 

</td>
<td valign="top">

Select this option to place the message in the dead-letter queue if it cannot be processed after three retries caused by an out-of-memory. Processing of the message is stopped then.

In such cases, a lock entry is created which you can view and release in the *Monitor* section of the Web UI under *Managing Locks*.

Use this option to avoid out-of-memory situations \(caused in many cases by large messages\).

For more information, read the SAP Community blog [Cloud Integration – Configure Dead Letter Handling in JMS Adapter![Information published on SAP site]()](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fblogs.sap.com%2F2017%2F07%2F17%2Fcloud-integration-configure-dead-letter-handling-in-jms-adapter%2F).

</td>
</tr>
<tr>
<td valign="top">

*Encrypt Message During Persistence*

</td>
<td valign="top">

DELIVERY ASSURANCE PARAMETERS

</td>
<td valign="top">

 

</td>
<td valign="top">

Select this option in case the messages should be stored in an encrypted way during certain processing steps.

</td>
</tr>
</table>



## Message Headers

Processed messages include the following standard headers:


<table>
<tr>
<th valign="top">

Header Name

</th>
<th valign="top">

Description/Value

</th>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Inbound_Virtual_File_Dataset_Name`

</td>
<td valign="top">

Inbound Virtual File Dataset Name

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Inbound_SFID_Origin`

</td>
<td valign="top">

File Originator \(SFIDORIG\)

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Inbound_SFID_Destination`

</td>
<td valign="top">

Final File Destination \(SFIDDEST\)

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Inbound_Own_Id`

</td>
<td valign="top">

Own Odette-ID

</td>
</tr>
<tr>
<td valign="top">

`SAP_OFTP_Inbound_Partner_Id`

</td>
<td valign="top">

Partner Odette-ID

</td>
</tr>
</table>



<a name="loio3420f2aab78f441d840cf8331de5893b__matching"/>

## Channel Matching for Incoming Files

When multiple channels use the same port, the system decides which channel receives the incoming file. This decision relies on a step-by-step matching process that narrows the options until only one channel remains.

The procedure includes the following steps:

1.  Port assignment when starting a channel. When you start a channel, the system checks if other channels already use the same port. If multiple channels use the same *Port* and *Partner Odette ID*, the configuration must use identical values for these fields:
    -   *Own Odette-ID*
    -   *Own Password*
    -   *Secure Handshake*

2.  Session filtering. When a connection starts, the system filters the available channels based on the following fields:
    -   *Partner Odette-ID*
    -   *Partner Password*
    -   *Secure Handshake*

3.  File filtering. When a file transfer begins, the system further narrows the channels based on these fields:
    -   *Expected Virtual File Dataset Name*
    -   *File Originator \(SFIDORIG\)*
    -   *Final File Destination \(SFIDDEST\)*


If multiple channels match all criteria, the system does not accept the file. This result indicates an ambiguous configuration.



## Concurrency and Thread Pool

The adapter manages several incoming connections simultaneously when it receives files. A thread pool reuses threads to increase efficiency. It also assigns consistent names to each thread for monitoring purposes. By default, the thread pool starts with one thread and can scale up to 50 threads.

You can change the maximum number of threads by setting the global property `OFTP_ADAPTER_SENDER_MAX_THREAD_POOL_SIZE`.

**Related Information**  


[Configure the OFTP Receiver Adapter](configure-the-oftp-receiver-adapter-8a6b283.md "Configure the OFTP Receiver Adapter to send files to partners and act as a Transmission Control Protocol (TCP) client.")

[OFTP Adapter for Edge Integration Cell](oftp-adapter-for-edge-integration-cell-04b392f.md "Use the Odette File Transfer Protocol (OFTP) adapter to exchange EDI and business files with partners on your Edge Integration Cell.")

