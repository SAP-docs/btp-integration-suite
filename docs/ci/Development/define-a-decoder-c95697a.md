<!-- loioc95697a0c3914ef6be9c014761363e86 -->

# Define a Decoder

You use this task to decode the message received over the network to retrieve original data.



<a name="loioc95697a0c3914ef6be9c014761363e86__steps_ns4_trq_35"/>

## Procedure

1.  Open the integration flow in the editor.

2.  From the palette, choose *Transformation* \> *Decoder*.

3.  Select one of the following decoding schemes:

    -   *Base64 Decode*: Decodes base64-encoded message content.

    -   *GZIP Decompress*: Decompresses the message content using GNU zip \(GZIP\).

    -   *ZIP Decompress*: Decompresses the message content using zip.


4.  Save the changes.




## Example

Let us suppose that an input message to the decoder is a message encoded in Base64 that looks like this:

`PG1lc3NhZ2U+DQoJSW5wdXQgZm9yIGVuY29kZXINCjwvbWVzc2FnZT4NCg==`

The output message of the decoder would be as follows:

```
<message>
	Input for encoder
</message>

```

**Related Information**  


[Blog: Cloud Integration – ZIP and Compress Capabilities: Encoder, Decoder, Splitter, Aggregate](https://blogs.sap.com/2020/05/05/cloud-integration-zip-and-compress-capabilities-encoder-decoder-splitter-aggregate/)

