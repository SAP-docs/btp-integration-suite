<!-- loio89f8bddeb90b44bab0a7d2ef7e37ad1a -->

# Define an Encoder

You use this task to encode messages using an encoding scheme to secure any sensitive message content during transfer over the network.



<a name="loio89f8bddeb90b44bab0a7d2ef7e37ad1a__steps_zfj_2rq_35"/>

## Procedure

1.  Open the integration flow in the editor.

2.  From the palette, choose *Transformation* \> *Encoder*.

3.  Select one of the following encoding schemes:


4.  Save the changes.




## Example

A message with the header Content-Type "text/plain" is sent to a MIME multipart encoder. The add multipart headers inline functionality is activated.

> ### Sample Code:  
> ```
> from("...").marshal().mimeMultipart("related", true, true, "(included|x-.*)", true);
> ```
> 
> The resulting message body will be:
> 
> > ### Sample Code:  
> > ```
> > Message Body
> > 
> > 
> > Message-ID: <...>
> > MIME-Version: 1.0
> > Content-Type: multipart/related; 
> >     boundary="----=_Part_0_1134128170.1447659361365"
> > 
> > ------=_Part_0_1134128170.1447659361365
> > Content-Type: text/plain
> > Content-Transfer-Encoding: 8bit
> >  
> > Body text
> > ------=_Part_0_1134128170.1447659361365
> > Content-Type: application/binary
> > Content-Transfer-Encoding: binary
> > Content-Disposition: attachment; filename="Attachment File Name"
> >  
> > [binary content]
> > ------=_Part_0_1134128170.1447659361365
> > 
> > ```

Consider the input XML payload structure to the encoder:

```
<message>
	Input for encoder
</message>

```

If you select Base64 Encode, the output message would look like this:

***PG1lc3NhZ2U+DQoJSW5wdXQgZm9yIGVuY29kZXINCjwvbWVzc2FnZT4NCg==***

**Related Information**  


[MIME Multipart Messages](mime-multipart-messages-3816537.md "")

[MIME Multipart Encoder: Handling Message Headers \(Examples\)](mime-multipart-encoder-handling-message-headers-examples-b446281.md "")

[Cloud Integration – ZIP and Compress Capabilities: Encoder, Decoder, Splitter, Aggregate](https://blogs.sap.com/2020/05/05/cloud-integration-zip-and-compress-capabilities-encoder-decoder-splitter-aggregate/)

