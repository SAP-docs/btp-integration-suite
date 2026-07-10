<!-- loio01de28e33a19497ebf32e0ea25defd1b -->

# Working with Message Transformer Flow Steps

Use message transformers in your API to convert request or response payloads from one format to another.



## Use

You use transformation steps in an API artifact to:

-   Modify message headers, body, or properties during message processing.
-   Convert message payloads between different formats \(for example, CSV, XML, JSON, EDI\).
-   Encode or decode message content using standard encoding formats \(Base64, MIME multipart\).
-   Compress or decompress message content using GZIP or ZIP formats to optimize data transfer.
-   Extract data from EDI documents \(flat file or XML format\) for further processing.
-   Filter specific data from an incoming message by removing unwanted content.
-   Calculate a message digest of the payload or parts of it and store the result in a message header.
-   Create custom scripts using Groovy Script or JavaScript to implement API-specific processing logic.
-   Modify XML content by removing External DTDs or XML declarations.



## Message Transformer Steps


<table>
<tr>
<th valign="top">

Policy

</th>
<th valign="top">

Sub Category

</th>
<th valign="top">

Policy Definition

</th>
<th valign="top">

Runtime Support

</th>
<th valign="top">

Important Notes/Links

</th>
</tr>
<tr>
<td valign="top">

Content Modifier

</td>
<td valign="top">

 

</td>
<td valign="top">

Allows you to modify a message by changing the content of the data containers that are involved in message processing \(message header, message body, or message exchange\).

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Content Modifier](define-content-modifier-8f04a70.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="6">

Converter

</td>
<td valign="top">

CSV to XML Converter

</td>
<td valign="top">

Transforms messages in CSV format to XML format.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Configure CSV to XML Converter](configure-csv-to-xml-converter-fe33888.md).

</td>
</tr>
<tr>
<td valign="top">

EDI to XML Converter

</td>
<td valign="top">

Transforms single incoming EDI message from EDI to XML format.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define EDI to XML Converter](define-edi-to-xml-converter-6a3d12b.md).

</td>
</tr>
<tr>
<td valign="top">

JSON to XML Converter

</td>
<td valign="top">

Transforms messages in JSON format to XML format.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define JSON to XML Converter](define-json-to-xml-converter-5a7c0cd.md).

</td>
</tr>
<tr>
<td valign="top">

XML to CSV Converter

</td>
<td valign="top">

Transforms content in XML format to CSV format.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Configure XML to CSV Converter](configure-xml-to-csv-converter-9025222.md).

</td>
</tr>
<tr>
<td valign="top">

XML to EDI Converter

</td>
<td valign="top">

Transforms a message in XML format to EDI format \(EDIFACT, ODETTE, TRADACOMS, or ASC-X12\).

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define XML to EDI Converter](define-xml-to-edi-converter-707973f.md).

</td>
</tr>
<tr>
<td valign="top">

XML to JSON Converter

</td>
<td valign="top">

Transforms messages in XML format to JSON format.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define XML to JSON Converter](define-xml-to-json-converter-a60a282.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Decoder

</td>
<td valign="top">

Base64 Decoder

</td>
<td valign="top">

Decodes base64-encoded message content.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top" rowspan="4">

For more information, see [Define a Decoder](define-a-decoder-c95697a.md).

</td>
</tr>
<tr>
<td valign="top">

GZIP Decompression

</td>
<td valign="top">

Decompresses the message content using GNU zip \(GZIP\).

</td>
<td valign="top">

-   Edge Integration Cell



</td>
</tr>
<tr>
<td valign="top">

MIME Mutlipart Decoder

</td>
<td valign="top">

Transforms a MIME multipart message into a message with attachments.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
</tr>
<tr>
<td valign="top">

ZIP Decompression

</td>
<td valign="top">

Decompresses the message content using zip format.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
</tr>
<tr>
<td valign="top">

EDI Extractor

</td>
<td valign="top">

EDI Extractor

</td>
<td valign="top">

Enables you to extract EDI headers and transfer to camel headers. This element extracts data from single incoming EDI document and adds it to the exchange such that this information can be used further in message processing. EDI extractor can read both flat file and XML format.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define EDI Extractor](define-edi-extractor-5fc2323.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Encoder

</td>
<td valign="top">

Base64 Encoder

</td>
<td valign="top">

Converts any binary data into text data. You can use an encoder if you need to transfer data over a medium that only supports the exchange of textual data.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top" rowspan="3">

For more information, see [Define an Encoder](define-an-encoder-89f8bdd.md).

</td>
</tr>
<tr>
<td valign="top">

GZIP Compression

</td>
<td valign="top">

Compresses the message content using GNU zip \(GZIP\).

</td>
<td valign="top">

-   Edge Integration Cell



</td>
</tr>
<tr>
<td valign="top">

ZIP Compression

</td>
<td valign="top">

Compresses the message content using zip format.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
</tr>
<tr>
<td valign="top">

MIME Mutlipart Encoder

</td>
<td valign="top">

Transforms the message content into a MIME multipart message.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define a MIME Multipart Encoder](define-a-mime-multipart-encoder-8c12a8e.md).

</td>
</tr>
<tr>
<td valign="top">

Filter

</td>
<td valign="top">



</td>
<td valign="top">

Extract specific data from an incoming message by removing unwanted content.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Filter](define-filter-733f8dc.md).

</td>
</tr>
<tr>
<td valign="top">

Message Digest

</td>
<td valign="top">



</td>
<td valign="top">

Calculate a digest of the payload or parts of it and store the result in a message header.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Message Digest](define-message-digest-e5d2867.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Script

</td>
<td valign="top">

Groovy Script

</td>
<td valign="top" rowspan="2">

Use a script step that’s specific to an integration artifact to create custom scripts \(Groovy Script or JavaScript\).

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top" rowspan="2">

For more information, see:

-   [Use Scripting Appropriately](use-scripting-appropriately-d4dc13c.md)
-   [Define a Local Script Step](define-a-local-script-step-03b32eb.md)



</td>
</tr>
<tr>
<td valign="top">

JavaScript

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
</tr>
<tr>
<td valign="top">

XML Modifier

</td>
<td valign="top">



</td>
<td valign="top">

Removes External DTDs and/or to remove XML Declarations.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define XML Modifier](define-xml-modifier-af16d64.md).

</td>
</tr>
</table>

