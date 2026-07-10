<!-- loioc9bba0eb3f724dca8388d6f92eaae582 -->

# Parameters That Support Dynamic Configuration

The following tables list all parameters that can be configured dynamically \(for the various adapter types and integration flow steps\).

For more information on the individual adapter and step types, see the documentation of the related integration flow component.

**Adapters**


<table>
<tr>
<th valign="top">

Adapter Type

</th>
<th valign="top">

Dynamically Configurable Parameters

</th>
</tr>
<tr>
<td valign="top">

ELSTER receiver

\(See: [ELSTER Receiver Adapter](elster-receiver-adapter-e374ef7.md)\)

</td>
<td valign="top">

-   Data Type

-   Private Key Alias for Encryption

-   Private Key Alias for Signing




</td>
</tr>
<tr>
<td valign="top">

FTP receiver

\(See: [Configure the FTP Receiver Adapter](configure-the-ftp-receiver-adapter-c16d331.md)\)

</td>
<td valign="top">

-   Address

-   Automatically Disconnect

-   Change Directories Stepwise

-   Credential Name

-   Directory

-   Encryption

-   File Name

-   Flatten File Names

-   Handling for Existing Files \(uses SAP\_FtpAfterProc\)

-   Location ID

-   Maximum Reconnect Attempts

-   Reconnect Delay \(in ms\)

-   Timeout \(in ms\)




</td>
</tr>
<tr>
<td valign="top">

HTTP receiver

\(See: [HTTP Receiver Adapter](http-receiver-adapter-2da452e.md)\)

</td>
<td valign="top">

-   Address \(uses header CamelHttpUri\)

-   Location ID

-   Query \(uses header CamelHttpQuery\)

-   Method

-   Credential Name

-   Private Key Alias




</td>
</tr>
<tr>
<td valign="top">

IDoc receiver

\(See: [Configure the IDoc Receiver Adapter](configure-the-idoc-receiver-adapter-018aa88.md)\)

</td>
<td valign="top">

-   Address

-   Location ID

-   Private Key Alias

-   Credential Name




</td>
</tr>
<tr>
<td valign="top">

Kafka receiver

\(See: [Configure the Kafka Receiver Adapter](configure-the-kafka-receiver-adapter-fc6ee1f.md)\)

</td>
<td valign="top">

-   Topic




</td>
</tr>
<tr>
<td valign="top">

Mail receiver

\(See: [Configure the Mail Receiver Adapter](configure-the-mail-receiver-adapter-f68d5e0.md)\)

</td>
<td valign="top">

-   Location ID

-   From

-   To

-   Cc

-   Bcc

-   Subject

-   Mail Body

-   Attachment Name

-   Private Key Alias

-   Receiver Public Key




</td>
</tr>
<tr>
<td valign="top">

Mail sender

\(See: [Configure the Mail Sender Adapter](configure-the-mail-sender-adapter-e23e9cc.md)\)

</td>
<td valign="top">

-   Location ID




</td>
</tr>
<tr>
<td valign="top">

OData V2 receiver

\(See: [Configure the OData V2 Receiver Adapter](configure-the-odata-v2-receiver-adapter-c5c2e38.md)\)

</td>
<td valign="top">

-   Address

-   Credential Name

-   Location ID

-   Resource Path

-   Query Options




</td>
</tr>
<tr>
<td valign="top">

OData V4 receiver

\(See: [Configure the OData V4 Receiver Adapter](configure-the-odata-v4-receiver-adapter-cd66a12.md)\)

</td>
<td valign="top">

-   Address

-   Credential Name

-   Location ID

-   Resource Path

-   Query Options

-   Custom Query Options




</td>
</tr>
<tr>
<td valign="top">

ProcessDirect receiver

\(See: [Configure the ProcessDirect Receiver Adapter](configure-the-processdirect-receiver-adapter-5b7327d.md)\)

</td>
<td valign="top">

-   Address




</td>
</tr>
<tr>
<td valign="top">

RFC receiver

\(See: [RFC Receiver Adapter](rfc-receiver-adapter-5c76048.md)\)

</td>
<td valign="top">

-   Destination




</td>
</tr>
<tr>
<td valign="top">

SFTP receiver

\(See: [Configure the SFTP Receiver Adapter](configure-the-sftp-receiver-adapter-4ef52cf.md)\)

</td>
<td valign="top">

-   File Name

-   Directory

-   Address

-   Proxy Type \(via property `SAP_FtpProxyType`\)

-   Location ID

-   Authentication \(via property `SAP_FtpAuthMethod`\)

-   Credential Name

-   User Name

-   Private Key Alias

-   Fast Exists Check \(via property `SAP_FtpFastExistsCheck`\)




</td>
</tr>
<tr>
<td valign="top">

SFTP sender

\(See: [Configure the SFTP Sender Adapter](configure-the-sftp-sender-adapter-2de9ee5.md)\)

</td>
<td valign="top">

-   File Name




</td>
</tr>
<tr>
<td valign="top">

SOAP 1.x receiver

\(See: [Configure the SOAP \(SOAP 1.x\) Receiver Adapter](configure-the-soap-soap-1-x-receiver-adapter-57f7b34.md)\)

</td>
<td valign="top">

-   Address

-   Location ID

-   Credential Name

-   Private Key Alias for Signing \(WS Security\)

-   Public Key Alias for Encryption \(WS Security\)

-   Credential Name \(Username Token under WS Security\)




</td>
</tr>
<tr>
<td valign="top">

SOAP 1.x sender

\(See: [Configure the SOAP \(SOAP 1.x\) Sender Adapter](configure-the-soap-soap-1-x-sender-adapter-a178913.md)\)

</td>
<td valign="top">

-   Private Key Alias for Response Signing \(WS Security\)

-   Public Key Alias for Response Encryption \(WS Security\)




</td>
</tr>
<tr>
<td valign="top">

SOAP SAP RM receiver

\(See: [Configure the SOAP \(SAP RM\) Receiver Adapter](configure-the-soap-sap-rm-receiver-adapter-8366495.md)\)

</td>
<td valign="top">

-   Address

-   Location ID

-   Credential Name

-   Private Key Alias




</td>
</tr>
<tr>
<td valign="top">

Success Factors \(SOAP\) sender

\(See: [Configure the SOAP \(SOAP 1.x\) Sender Adapter](configure-the-soap-soap-1-x-sender-adapter-a178913.md)\)

</td>
<td valign="top">

-   Query




</td>
</tr>
<tr>
<td valign="top">

XI receiver

\(See: [Configure the XI Receiver Adapter](configure-the-xi-receiver-adapter-5d2670f.md)\)

</td>
<td valign="top">

-   Address

-   Credential Name

-   Private Key Alias

-   XI-specific identifiers \(Communication Party \(for sender and receiver\), Communication Component \(for sender and receiver\), Service Interface \(for receiver\), and Service Interface Namespace \(for receiver\)\)




</td>
</tr>
</table>

**Integration Flow Steps**


<table>
<tr>
<th valign="top">

Step Type

</th>
<th valign="top">

Dynamically Configurable Parameters

</th>
</tr>
<tr>
<td valign="top">

Data Store Select

\(See: [Define Data Store Select Operations](define-data-store-select-operations-8cfe004.md)\)

</td>
<td valign="top">

-   Data Store Name

-   Number of Polled Messages




</td>
</tr>
<tr>
<td valign="top">

Data Store Write

\(See: [Define Data Store Write Operations](define-data-store-write-operations-46260ee.md)\)

</td>
<td valign="top">

-   Data Store Name

-   Entry ID




</td>
</tr>
<tr>
<td valign="top">

Data Store Get

\(See: [Define Data Store Get Operations](define-data-store-get-operations-232ac46.md)\)

</td>
<td valign="top">

-   Data Store Name

-   Entry ID




</td>
</tr>
<tr>
<td valign="top">

Data Store Delete

\(See: [Define Data Store Delete Operations](define-data-store-delete-operations-5efa3ac.md)\)

</td>
<td valign="top">

-   Data Store Name

-   Entry ID




</td>
</tr>
<tr>
<td valign="top">

Simple Signer

\(See: [Sign the Message Content with Simple Signer](sign-the-message-content-with-simple-signer-9879fc3.md)\)

</td>
<td valign="top">

Private Key Alias

</td>
</tr>
<tr>
<td valign="top">

XML Signer

\(See: [Sign the Message Content with XML Digital Signature](sign-the-message-content-with-xml-digital-signature-9a013db.md)\)

</td>
<td valign="top">

Private Key Alias

</td>
</tr>
<tr>
<td valign="top">

PGP Encryptor

\(See: [Define PGP Encryptor](define-pgp-encryptor-7a07766.md)\)

</td>
<td valign="top">

Encryption User ID of Key\(s\) from Public Keyring

Signer User ID of Key\(s\) from Secret Keyring

</td>
</tr>
<tr>
<td valign="top">

PGP Decryptor

\(See: [Define PGP Decryptor](define-pgp-decryptor-d0dc511.md)\)

</td>
<td valign="top">

Signer User ID of Key\(s\) from Public Keyring

</td>
</tr>
</table>

**Related Information**  


[Dynamic Parameters \(Example\)](dynamic-parameters-example-5705f2b.md)

