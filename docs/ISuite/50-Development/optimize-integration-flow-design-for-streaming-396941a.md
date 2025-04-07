<!-- loio396941a8c12441ab999f0f300b862eaa -->

# Optimize Integration Flow Design for Streaming

Use streaming to process large messages.

Processing large messages can lead to high processing times and high memory consumption. In the worst case, processing large messages leads to out of memory errors and hence a downtime of the SAP Integration Suite runtime components. To avoid such situations, streaming can help. In addition to decreasing memory consumption, this feature also improves runtime performance.

If you just pass a message through SAP Integration Suite from sender to receiver without modifying the payload, streaming is automatically supported if the involved adapters support streaming. As the payload isn't parsed, also larger messages can be transferred. However, in most integration scenarios a modification of the message is required. Note that not all integration flow steps support streaming. Therefore, check and, if necessary, redesign your integration scenario using streaming-enabled integration flow components. This can help avoid splitting of the payload into chunks. In the table below, all steps and their streaming capability are listed.

> ### Note:  
> Even when using streaming, there are limits in terms of message size because a temporary file is used that is stored in the tenant's file system. The size of the temporary storage limits the maximum file size that can be transferred.

For an overview of the available resources of tenants deployed in the Cloud Foundry environment, see[System Scope for Cloud Integration in the Cloud Foundry Environment](../system-scope-for-cloud-integration-8ea3822.md).

To monitor the total storage used by temporary files, see [Inspect Temporary Storage](inspect-temporary-storage-7cdfaa7.md).

If you cannot avoid using a non-streaming integration flow component, you have to apply the following approach to process a large message: Split it into chunks and process each chunk individually.



****


<table>
<tr>
<th valign="top">

Component Type

</th>
<th valign="top">

Component

</th>
<th valign="top">

Characteristics

</th>
<th valign="top">

Streaming Supported

</th>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

AMQP

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

Ariba

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

AS2

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

AS4

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

ELSTER

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

Facebook

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

FTP

</td>
<td valign="top">

Parameter *Change Directories Stepwise* disabled

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

FTP

</td>
<td valign="top">

Parameter *Change Directories Stepwise* enabled

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

HTTP

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

IDoc

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

JDBC

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

JMS

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

LDAP

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

Mail

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

OData V2

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

OData V4

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

ODC

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

RFC

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

SFTP

</td>
<td valign="top">

Parameter *Change Directories Stepwise* disabled

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

SFTP

</td>
<td valign="top">

Parameter *Change Directories Stepwise* enabled

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

SOAP \(SAP RM\)

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

SOAP \(SOAP 1.x\)

</td>
<td valign="top">

In general

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

SOAP \(SOAP 1.x\)

</td>
<td valign="top">

*WS Security* enabled

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

SuccessFactors OData V4

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

SuccessFactors REST

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

SuccessFactors SOAP

</td>
<td valign="top">

Use *Pagination* as an alternative.

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

Twitter

</td>
<td valign="top">



</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

XI

</td>
<td valign="top">

Parameter *Quality of Service* set to *Best Effort* 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

XI

</td>
<td valign="top">

Parameter *Quality of Service* set to *Exactly Once*

Parameter *Temporary Storage* set to *Data Store*

Environment: Cloud Foundry

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

XI

</td>
<td valign="top">

Parameter *Quality of Service* set to *Exactly Once*

Parameter *Temporary Storage* set to *Data Store*

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Adapter

</td>
<td valign="top">

XI

</td>
<td valign="top">

Parameter *Quality of Service* set to *Exactly Once*

Parameter *Temporary Storage* set to *JMS Queue*

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Routing

</td>
<td valign="top">

Aggregator

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Routing

</td>
<td valign="top">

Gather

</td>
<td valign="top">

Parameter *Aggregation Algorithm* set to *Combine* 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Routing

</td>
<td valign="top">

Gather

</td>
<td valign="top">

Parameter *Aggregation Algorithm* set to *Combine at XPath* 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Routing

</td>
<td valign="top">

Router

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Routing

</td>
<td valign="top">

PKCS\#7/CMS Splitter

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Routing

</td>
<td valign="top">

General Splitter

</td>
<td valign="top">

Configurable parameter

\(see: [Define General Splitter](define-general-splitter-a6c1916.md)\)

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Routing

</td>
<td valign="top">

Iterating Splitter

</td>
<td valign="top">

Configurable parameter

\(see: [Define Iterating Splitter](define-iterating-splitter-d61d6ec.md)\)

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Routing

</td>
<td valign="top">

IDoc Splitter

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Routing

</td>
<td valign="top">

ZIP/TAR Splitter

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Routing

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

CSV to XML Converter

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

XML to CSV Converter

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

JSON to XML Converter

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

XML to JSON Converter

</td>
<td valign="top">

Configurable parameter

\(see: [Define XML to JSON Converter](define-xml-to-json-converter-a60a282.md)\)

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

EDI to XML Converter

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

XML to EDI Converter

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

Filter

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

Message Digest

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

Message Mapping

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

Base64 Encoder

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

Base64 Decoder

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

GZIP Encoder

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

GZIP Decoder

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

ZIP Encoder

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

ZIP Decoder

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

MIME Multipart Encoder

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Message Transformer

</td>
<td valign="top">

MIME Multipart Decoder

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

External Call

</td>
<td valign="top">

Content Enricher

</td>
<td valign="top">

Parameter *Aggregation Algorithm* set to *Combine* 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

External Call

</td>
<td valign="top">

Content Enricher

</td>
<td valign="top">

Parameter *Aggregation Algorithm* set to *Enrich* 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Message Validators

</td>
<td valign="top">

XML Schema Validation

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Security

</td>
<td valign="top">

PKCS\#7 Decryptor

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Security

</td>
<td valign="top">

PKCS\#7 Encryptor

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Security

</td>
<td valign="top">

PKCS\#7 Signer

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Security

</td>
<td valign="top">

PKCS\#7 Signature Verifier

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Security

</td>
<td valign="top">

Simple Signer

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Security

</td>
<td valign="top">

XML Digital Signer

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Security

</td>
<td valign="top">

XML Signature Verifier

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Security

</td>
<td valign="top">

PGP Decryptor

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Security

</td>
<td valign="top">

PGP Encryptor

</td>
<td valign="top">

 

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Persistence

</td>
<td valign="top">

Persist

</td>
<td valign="top">



</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Persistence

</td>
<td valign="top">

Persist

</td>
<td valign="top">

Environment: Cloud Foundry

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Persistence

</td>
<td valign="top">

Data Store Write

</td>
<td valign="top">



</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Persistence

</td>
<td valign="top">

Data Store Write

</td>
<td valign="top">

Environment: Cloud Foundry

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Persistence

</td>
<td valign="top">

Data Store Get

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Persistence

</td>
<td valign="top">

Data Store Select

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Persistence

</td>
<td valign="top">

Write Variables

</td>
<td valign="top">

 

</td>
<td valign="top">

No

</td>
</tr>
</table>

