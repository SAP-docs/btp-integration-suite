<!-- loioe32cedef6e8c4af5816c446541c7f527 -->

# Integration Capabilities

There is a wide range of integration capabilities that define different ways how messages can be processed on the integration platform and exchanged between sender and receiver systems.

Cloud Integration supports various integration patterns, or ways how applications can be integrated with each other.

The following figure illustrates, as one example, the routing pattern, that allows you to forward a message from one participant to multiple receivers.

![](images/HCI_Integration_Pattern_Routing_4a51110.png)

When using Cloud Integration, you specify the desired integration pattern by adding a dedicated **integration flow step** or a combination of various integration flow steps to an integration flow.

The following table lists the available integration capabilities, arranged by the related integration flow step types.

**Message Transformation**


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Mapping

</td>
<td valign="top">

Transforms the data structure and format used by the sender into a structure and format that the receiver can process.

Supports the following kinds of mappings:

-   Message mappings designed with a graphical editor as part of the Cloud Integration toolset \(supports XSD and EDMX structures\)

-   Custom-mapping functions defined in scripts

-   XSLT mappings \(defined in an XSLT resource\)




</td>
</tr>
<tr>
<td valign="top">

ID Mapping

</td>
<td valign="top">

Maps the source message ID to a target message ID. You can use this feature to implement scenarios with exactly once processing of messages.

</td>
</tr>
<tr>
<td valign="top">

Content Modifier

</td>
<td valign="top">

Modifies the content of an inbound message by changing the header or body of the message.

A message is composed of a message body and message headers. Furthermore, when being processed on a Cloud Integration tenant, additional data associated with the message can be passed along in an additional container \(referred to as *message exchange*\) to make it available at a later point in time during message processing. The Content Modifier can read data from and write data to the message body, the message header, and the properties area of the message exchange. That way, the content of a message can flexibly be modified and prepared for a receiver or subsequent processing steps.

Certain constraints apply with regard to the supported data formats \(as described in the product documentation\).

</td>
</tr>
<tr>
<td valign="top">

XML Modifier

</td>
<td valign="top">

Modifies the content of an inbound message by removing external DTDs and/or removing XML declarations.

</td>
</tr>
<tr>
<td valign="top">

Converter

</td>
<td valign="top">

Transforms an input message into another format.

The following converters are available:

-   *XML to JSON*: Transforms messages in XML format to JSON format.

    You can specify streaming \(with either the whole XML document or only specified XML elements presented by JSON arrays\).

-   *JSON to XML*: Transforms messages in JSON format to XML format.

-   *XML to CSV*: Transforms messages in XML format to CSV format.

-   *CSV to XML*: Transforms messages in CSV format to XML format.

-   *XML to EDI*: Transforms a message in XML format to Electronic Data Interchange \(EDI\) format.

-   *EDI to XML*: Transforms a message in EDI format \(EDIFACT or ASC-X12 format\) to XML format.


Certain constraints apply with regard to the supported data formats \(as described in the product documentation\).

</td>
</tr>
<tr>
<td valign="top">

Decoder

</td>
<td valign="top">

Decodes the incoming message to retrieve the original data \(for example, if a base64-encoded message has been received\).

-   *Base64 Decode*: Decodes base64-encoded message content.

-   *GZIP Decompress*: Decompresses the message content using GNU zip \(GZIP\).

-   *ZIP Decompress*: Decompresses the message content using zip \(only zip archives with a single entry supported\).

-   *MIME Multipart Decode*: Transforms a MIME multipart message into a message with attachments.




</td>
</tr>
<tr>
<td valign="top">

Encoder

</td>
<td valign="top">

Encodes the message using an encoding scheme to secure any sensitive message content during transfer over the network.




</td>
</tr>
<tr>
<td valign="top">

Filter

</td>
<td valign="top">

Filters information by extracting a specific node from the incoming message by using an XPath expression.

</td>
</tr>
<tr>
<td valign="top">

Message Digest

</td>
<td valign="top">

Calculates a digest of the payload or parts of it and stores the result in a message header.

</td>
</tr>
<tr>
<td valign="top">

Script

</td>
<td valign="top">

Executes custom Java script or Groovy script for message processing.

</td>
</tr>
</table>

**Calling External Systems or Subprocesses**


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Request-Reply

</td>
<td valign="top">

Calls an external receiver system in a synchronous step and gets back a response.

</td>
</tr>
<tr>
<td valign="top">

Send

</td>
<td valign="top">

Calls an external receiver system for use cases where no reply is expected.

</td>
</tr>
<tr>
<td valign="top">

Content Enricher

</td>
<td valign="top">

Calls an external system, accesses resources of this system, and merges the returned content with the original message.

</td>
</tr>
<tr>
<td valign="top">

Poll Enrich Step

</td>
<td valign="top">

Polls content from an external component, and enriches the original message with it.

</td>
</tr>
<tr>
<td valign="top">

Process Call

</td>
<td valign="top">

Calls a local integration process.

A local integration process defines a container for a separate subprocess to be called from the main process. Using local integration processes, a complex message processing sequence can be fragmented and decomposed into smaller parts.

</td>
</tr>
<tr>
<td valign="top">

Looping Process Call

</td>
<td valign="top">

Calls a local integration process in a loop.

</td>
</tr>
<tr>
<td valign="top">

Idempotent Process Call

</td>
<td valign="top">

Detects if a message ID has already been successfully processed and stores the status of the successful process in the idempotent repository. If there's duplicate execution with the same message ID \(for example if there’s a retry by the sender system\), the called subprocess can either be skipped or the message is marked as a duplicate. You can then decide how to handle the duplicate in the subprocess.

</td>
</tr>
</table>

**Routing**


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Router

</td>
<td valign="top">

Routes a message to one or more receivers.

SAP Cloud Integration also supports routing that depends on the content of the message \(content-based routing\). For example, the tenant detects that a message has a particular field value, and forwards it to the specific receiver participant that handles requests from the sender participant.

</td>
</tr>
<tr>
<td valign="top">

Multicast

</td>
<td valign="top">

Sends the same message to more than one receiver.

-   Parallel multicast: Initiates message transfer to all the receiver nodes in parallel

-   Sequential multicast: defines the sequence in which the message transfer to the receivers is initiated.




</td>
</tr>
<tr>
<td valign="top">

Splitter

</td>
<td valign="top">

Decomposes a composite message into a series of individual messages and sends them to a receiver.

Supported splitters:

-   General splitter: Breaks down a composite message containing ‘n’ messages into ‘n’ individual messages. Each individual message is enveloped by the same elements that enveloped the composite message.

-   Iterating splitter: Splits a composite message into a series of smaller messages without copying the enveloping elements of the composite message

-   PKCS\#7/CMS splitter: Splits a PKCS7 Signed Data message that contains a signature and content \(and breaks down the signature and content into separate files\)

-   IDoc splitter: Splits a composite IDoc messages into a series of individual IDoc messages with the enveloping elements of the composite IDoc message

-   EDI splitter: Splits a bulk EDI message into a series of individual messages and validates and acknowledges the inbound message.

    A bulk EDI message can contain one or more EDI formats, such as EDIFACT, EANCOM, or ASC-X12. The EDI splitter can process different EDI formats depending on the business requirements of the trading partners.

-   Zip splitter: Splits an inbound archive file \(.zip\) into individual files.

-   Tar splitter: Splits an archive \(.tar\) file into individual files.


Certain constraints apply with regard to the supported data formats \(as described in the product documentation\).

</td>
</tr>
<tr>
<td valign="top">

Join

</td>
<td valign="top">

Merges messages from different routes and combines them into a single message.

This feature is used in combination with the Gather feature. Join simply brings together the messages from different routes; it doesn't affect the content of the messages.

Certain constraints apply with regard to the usage of this feature \(as described in the product documentation\).

</td>
</tr>
<tr>
<td valign="top">

Gather

</td>
<td valign="top">

Merges messages from different routes \(into a single message\) with the option to define certain strategies how to combine the initial messages.

</td>
</tr>
</table>

**Storing Data During Processing**


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Persist Message

</td>
<td valign="top">

Stores a message payload so that you can access the stored message and analyze it at a later point in time.

</td>
</tr>
<tr>
<td valign="top">

Data Store Operations

</td>
<td valign="top">

Stores messages temporarily for later processing.

The following operations are supported:

-   SELECT

-   GET

-   WRITE

-   DELETE




</td>
</tr>
<tr>
<td valign="top">

Write Variables

</td>
<td valign="top">

Specifies values for variables required during message processing.

</td>
</tr>
</table>

**Protecting Messages**


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Encryptor

</td>
<td valign="top">

Encrypts the content of a message.

Supported standards:

-   PGP

-   PKCS\#7/CMS Enveloped Data and Signed Data




</td>
</tr>
<tr>
<td valign="top">

Decryptor

</td>
<td valign="top">

Decrypts the content of a message.

Supported standards:

-   PGP

-   PKCS\#7/CMS Enveloped Data and Signed Data




</td>
</tr>
<tr>
<td valign="top">

Signer

</td>
<td valign="top">

Signs a message.

Supported standards:

-   PKCS\#7/CMS Enveloped Data and Signed Data

-   XML Digital Signature




</td>
</tr>
<tr>
<td valign="top">

Verifier

</td>
<td valign="top">

Verifies a message.

Supported standards:

-   PKCS\#7/CMS Enveloped Data and Signed Data

-   XML Digital Signature




</td>
</tr>
</table>



## Mapping

Mapping transforms \(maps\) sender into receiver data structures.

In scenarios spanning different application systems or different organizations and enterprises, it is very likely that the structure of the data exchanged between two participants will differ on both sides of a connection due to business-related reasons. To enable a seamless exchange of data, the data structures on both sides of a connection have to be transformed \(or: mapped\) into each other. There is the option to apply structural mapping of XML documents.

You can re-use existing on-premise content \(service interfaces / message mappings / operation mappings / XSLT based mappings\) from an SAP Enterprise Services Repository.

Value mappings allow you to map different representations of an object to each other.

Value mappings are useful when performing a dynamic value lookup of an object that has different representations in different contexts. In value mappings, you map these different representations of an object to each other by setting mapping rules in a value mapping table.

> ### Note:  
> For example: You can use a value mapping to map a Merchant ID to a Customer ID, where Merchant ID is an external application representation of a customer, while Customer ID is an internal SAP representation.

