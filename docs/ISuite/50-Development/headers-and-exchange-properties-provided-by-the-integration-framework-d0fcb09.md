<!-- loiod0fcb0988f034e889f611c6e36d43ad5 -->

# Headers and Exchange Properties Provided by the Integration Framework



**Headers and Exchange Properties**


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Type \(Property or Header\)

</th>
<th valign="top">

Related Component

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Archived-At

</td>
<td valign="top">

Header

</td>
<td valign="top">

Mail adapter

</td>
<td valign="top">

Specifies a link to the archived form of an e-mail.

</td>
</tr>
<tr>
<td valign="top">

CamelAggregatedCompletedBy

</td>
<td valign="top">

Header

</td>
<td valign="top">

Aggregator

</td>
<td valign="top">

Is relevant for use cases with message aggregation.

The header attribute can only have one of the following values:

-   timeout

    Processing of the aggregate has been stopped because the configured Completion Timeout has been reached.

-   predicate

    Processing of the aggregate has finished because the Completion Condition has been met.




</td>
</tr>
<tr>
<td valign="top">

CamelCharsetName

</td>
<td valign="top">

Property

</td>
<td valign="top">

Encoder

Content Modifier

</td>
<td valign="top">

Specifies the character encoding to be applied for message processing. You can override the character encoding and avoid encoding issues when you use special characters.

</td>
</tr>
<tr>
<td valign="top">

CamelFileName

</td>
<td valign="top">

Header

</td>
<td valign="top">

SFTP Receiver adapter

</td>
<td valign="top">

Overrides the existing file and directory name that is set directly in the endpoint.

You can use this header to dynamically change the name of the file and directory to be called.

If you do not enter a file name in the SFTP receiver adapter, the content of the `CamelFileName` header \(if set\) is used as file name. If this header is not specified, the Exchange ID is used as file name.

</td>
</tr>
<tr>
<td valign="top">

CamelFileNameOnly

</td>
<td valign="top">

Header

</td>
<td valign="top">

SFTP Sender adapter

</td>
<td valign="top">

Defines that only the file name \(the name with no leading paths\) is consumed.

</td>
</tr>
<tr>
<td valign="top">

CamelFileParent

</td>
<td valign="top">

Header

</td>
<td valign="top">

SFTP Sender adapter

</td>
<td valign="top">

Technical header required to support proper archiving in post-processing used by the SFTP Sender adapter.

</td>
</tr>
<tr>
<td valign="top">

CamelHttpMethod

</td>
<td valign="top">

Header

</td>
<td valign="top">

HTTPS Sender adapter

</td>
<td valign="top">

Refers to the HTTP method name of the incoming request \(*GET*, *POST*, *PUT*, *DELETE*, and so on\).

The HTTPS sender adapter sets this header.

</td>
</tr>
<tr>
<td valign="top">

CamelHttpPath

</td>
<td valign="top">

Header

</td>
<td valign="top">

HTTPS Sender adapter

</td>
<td valign="top">

Refers to the dynamic part of the URL path of the integration flow endpoint.

As an example, assume that you specify the endpoint address \(in the sender adapter\) as `/myEndpoint/*`.

A sender system calls this integration flow using the address `/myEndpoint/abc/def`.

In this case, header `CamelHttpPath` gets the value `abc/def`.

</td>
</tr>
<tr>
<td valign="top">

CamelHttpQuery

</td>
<td valign="top">

Header

</td>
<td valign="top">

HTTPS Sender adapter

HTTP Receiver adapter

</td>
<td valign="top">

Refers to the query string that is contained in the request URL \(for example, `CamelHttpQuery=abcd=1234`\).

The HTTPS sender adapter sets this header.

In the context of a receiver adapter, this header can be used to dynamically change the URI to be called.

</td>
</tr>
<tr>
<td valign="top">

CamelHttpResponseCode

</td>
<td valign="top">

Header

</td>
<td valign="top">

HTTPS Sender adapter

</td>
<td valign="top">

You can use this header to manually set the HTTP response status code.

</td>
</tr>
<tr>
<td valign="top">

CamelHttpUri

</td>
<td valign="top">

Header

</td>
<td valign="top">

HTTPS Sender adapter

HTTP Receiver adapter

</td>
<td valign="top">

Overrides the existing URI set directly in the endpoint.

You can use this header to dynamically change the URI to be called.

</td>
</tr>
<tr>
<td valign="top">

CamelHttpUrl

</td>
<td valign="top">

Header

</td>
<td valign="top">

HTTPS Sender adapter

HTTP Receiver adapter

</td>
<td valign="top">

Refers to the complete URL called, without query parameters.

For example, `CamelHttpUrl=https://test.bsn.neo.ondemand.com/http/hello`.

</td>
</tr>
<tr>
<td valign="top">

CamelRemoteFileInputStream

</td>
<td valign="top">

Header

</td>
<td valign="top">

SFTP Sender adapter

</td>
<td valign="top">

Technical header required to support streaming used by the SFTP sender adapter.

</td>
</tr>
<tr>
<td valign="top">

CamelServletContextPath

</td>
<td valign="top">

Header

</td>
<td valign="top">

HTTPS Sender adapter

</td>
<td valign="top">

Refers to the path specified in the address field of the channel.

For example, if the address in the channel is */abcd/1234*, then *CamelServletContextPath* is */abcd/1234*.

The HTTPS sender adapter sets this header.

</td>
</tr>
<tr>
<td valign="top">

CamelSplitComplete

</td>
<td valign="top">

Property

</td>
<td valign="top">

Splitter

</td>
<td valign="top">

Indicates whether an Exchange is the last split.

</td>
</tr>
<tr>
<td valign="top">

CamelSplitIndex

</td>
<td valign="top">

Property

</td>
<td valign="top">

Splitter

</td>
<td valign="top">

Provides a counter for split items that increases for each Exchange that is split \(starts from 0\).

</td>
</tr>
<tr>
<td valign="top">

CamelSplitSize

</td>
<td valign="top">

Property

</td>
<td valign="top">

Splitter

</td>
<td valign="top">

Provides the total number of split items \(if you are using stream-based splitting, this header is only provided for the last item, in other words, for the completed Exchange\).

</td>
</tr>
<tr>
<td valign="top">

CamelXmlSignatureTransformMethods

</td>
<td valign="top">

Header

</td>
<td valign="top">

XML signer

</td>
<td valign="top">

Specifies transformation methods in a comma-separated list.

You can use this header to specify transformation methods in a comma-separated list. This header will overwrite the value of the option *Transform Method for Payload*.

> ### Example:  

> ### Sample Code:  
> Example of this use case: The XML signature verifier of the receiving system expects an XML signature as shown in the following code snippet.
> 
> The signature is a detached signature, because the signature element is a sibling of the signed element B. However, the receiving system requires the enveloped-signature transform method to be specified in the Transforms list. To ensure this, you have to configure a detached signature in the XML Signer step, then add a Content Modifier step before the XML Signer step, where you specify the header "CamelXmlSignatureTransformMethods" with the constant value “http://www.w3.org/2000/09/xmldsig\#enveloped-signature,http://www.w3.org/TR/2001/REC-xml-c14n-20010315".
> 
> ```
> 
> <?xml version="1.0" encoding="UTF-8" ?>
> 
> <root> 
> 
>             <B ID="IDforB">
> 
>                 ...
> 
>             </B>
> 
>             <ds:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#"
> 
>                 Id="_6bf13099-0568-4d76-8649-faf5dcb313c0">
> 
>                 <ds:SignedInfo>
> 
>                     ...
> 
>                     <ds:Reference URI="#IDforB">
> 
>                         <ds:Transforms>
> 
>                             <ds:Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature" />
> 
>                             <ds:Transform Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315" />
> 
>                         </ds:Transforms>
> 
>                         ...
> 
>                     </ds:Reference>
> 
>                 </ds:SignedInfo>
> 
>                 <ds:SignatureValue>aUDFmiG71</ds:SignatureValue>
> 
>             </ds:Signature>
> 
> <root>
> 
> ```



</td>
</tr>
<tr>
<td valign="top">

CamelXmlSignatureXAdESQualifyingPropertiesId

</td>
<td valign="top">

Header

</td>
<td valign="top">

XML Signer

</td>
<td valign="top">

Specifies the `Id` attribute value of the QualifyingProperties element.

</td>
</tr>
<tr>
<td valign="top">

CamelXmlSignatureXAdESSignedDataObjectPropertiesId

</td>
<td valign="top">

Header

</td>
<td valign="top">

XML Signer

</td>
<td valign="top">

Specifies the `Id` attribute value of the SignedDataObjectProperties element.

</td>
</tr>
<tr>
<td valign="top">

CamelXmlSignatureXAdESSignedSignaturePropertiesId

</td>
<td valign="top">

Header

</td>
<td valign="top">

XML Signer

</td>
<td valign="top">

Specifies the `Id` attribute value of the SignedSignatureProperties element.

</td>
</tr>
<tr>
<td valign="top">

CamelXmlSignatureXAdESDataObjectFormatEncoding

</td>
<td valign="top">

Header

</td>
<td valign="top">

XML Signer

</td>
<td valign="top">

Specifies the value of the `Encoding` element of the DataObjectFormat element.

</td>
</tr>
<tr>
<td valign="top">

CamelXmlSignatureXAdESNamespace

</td>
<td valign="top">

Header

</td>
<td valign="top">

XML Signer

</td>
<td valign="top">

Overwrites the `namespace` parameter value.

</td>
</tr>
<tr>
<td valign="top">

CamelXmlSignatureXAdESPrefix

</td>
<td valign="top">

Header

</td>
<td valign="top">

XML Signer

</td>
<td valign="top">

Overwrites the `prefix` parameter value.

</td>
</tr>
<tr>
<td valign="top">

Cc

</td>
<td valign="top">

Header

</td>
<td valign="top">

Mail Receiver adapter

</td>
<td valign="top">

Additional e-mail address that the message is sent to.

</td>
</tr>
<tr>
<td valign="top">

Content-Encoding

</td>
<td valign="top">

Header

</td>
<td valign="top">

HTTP Receiver adapter

</td>
<td valign="top">

The encoding used during message transport \(for example, `gzip` for GZIP file compression\).

This information is used by the receiver to retrieve the media type that is referenced by the `content-type` header.

If this header is not specified, the default value `identity` \(no compression\) is used.

More information: [https://tools.ietf.org/html/rfc2616](https://tools.ietf.org/html/rfc2616) \(section 14.11\)

The list of available content types is maintained by the Internet Assigned Numbers Authority \(IANA\). For more information, see:[http://www.iana.org/assignments/http-parameters/http-parameters.xhtml\#content-coding](http://www.iana.org/assignments/http-parameters/http-parameters.xhtml#content-coding).

</td>
</tr>
<tr>
<td valign="top">

Content-Type

</td>
<td valign="top">

Header

</td>
<td valign="top">

HTTP Receiver adapter

Mail Receiver adapter

</td>
<td valign="top">

HTTP content type that fits to the body of the request.

The content type is composed of two parts: a type and a subtype.For example, `image/jpeg` \(where `image` is the type and `jpeg` is the subtype\).

Examples:

-   `text/plain` for unformatted text

-   `text/html` for text formatted with HTML syntax

-   `image/jpeg` for a jpeg image file

-   `application/json` for data in JSON format to be processed by an application that requires this format


More information on the available types: [https://www.w3.org/Protocols/rfc1341/4\_Content-Type.html](https://www.w3.org/Protocols/rfc1341/4_Content-Type.html)

The list of available content types is maintained by the Internet Assigned Numbers Authority \(IANA\). For more information, see [http://www.iana.org/assignments/media-types/media-types.xhtml](http://www.iana.org/assignments/media-types/media-types.xhtml).

> ### Note:  
> If transferring `text/*` content types, you can also specify the character encoding in the HTTP header using the `charset` parameter.
> 
> Here is an example of such a header:
> 
> `Content-Type: text/html; charset=utf-8`
> 
> The default character encoding that will be applied for `text/*` content types depends on the HTTP version: `us-ascii` for HTTP 1.0 and `iso-8859-1` for HTTP 1.1.
> 
> Text data in string format is converted using UTF-8 by default during message processing. If you want to override this behavior, you can use the Content Modifier step and specify the `CamelCharsetName` Exchange property. To avoid encoding issues when using this feature together with the HTTP adapter, consider the following example configuration:
> 
> If you use a Content Modifier step and you want to send `iso-8859-1`-encoded data to a receiver, make sure that you specify the `CamelCharsetName` Exchange property \(either header or property\) as `iso-8859-1`. For the Content-Type HTTP header, use `text/plain; charset=iso-8859-1`.



</td>
</tr>
<tr>
<td valign="top">

Date

</td>
<td valign="top">

Header

</td>
<td valign="top">

Mail adapter

</td>
<td valign="top">

The date and time when the e-mail was sent.

</td>
</tr>
<tr>
<td valign="top">

From

</td>
<td valign="top">

Header

</td>
<td valign="top">

Mail adapter

</td>
<td valign="top">

Email address that the message comes from.

</td>
</tr>
<tr>
<td valign="top">

JMSCorrelationID

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Specifies the application correlation identifier. This header corresponds to the AMQP header correlation-id.

</td>
</tr>
<tr>
<td valign="top">

JMSDeliveryMode

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Specifies durability requirements. This header corresponds to the AMQP header durable.

</td>
</tr>
<tr>
<td valign="top">

JMSDeliveryTime

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Specifies the time at which a message is to be delivered at the earliest. This header corresponds to the AMQP header x-opt-delivery-time.

</td>
</tr>
<tr>
<td valign="top">

JMSDestination

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Specifies the address of node that acts as message destination. This header corresponds to the AMQP header to.

</td>
</tr>
<tr>
<td valign="top">

JMSExpiration

</td>
<td valign="top">

Header

</td>
<td valign="top">

JMS Consumer

</td>
<td valign="top">

Sets an expiration date for messages that are only relevant for a certain amount of time in milliseconds. This header corresponds to the AMQP header absolute-expiry-time.

</td>
</tr>
<tr>
<td valign="top">

JMSTimestamp

</td>
<td valign="top">

Header

</td>
<td valign="top">

JMS Consumer

</td>
<td valign="top">

Time when a JMS message was created.

</td>
</tr>
<tr>
<td valign="top">

JMSMessageID

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Uniquely identifies a message.

</td>
</tr>
<tr>
<td valign="top">

JMSPriority

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Specifies the relative message priority. This header corresponds to the AMQP header priority.

</td>
</tr>
<tr>
<td valign="top">

JMSRedelivered

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Specifies, if the message was redelivered. Value ‘false’ means that this message was delivered for the first time, value ‘true’ tells you that this message was already tried to be delivered before.

</td>
</tr>
<tr>
<td valign="top">

JMSReplyTo

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Specifies the node that the message consumer replies to. This header corresponds to the AMQP header reply-to.

</td>
</tr>
<tr>
<td valign="top">

JMSType

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Identifies the message structure and type of payload. This header corresponds to the AMQP header subject.

</td>
</tr>
<tr>
<td valign="top">

JMSXDeliveryCount

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Specifies the number of processings for this message. Value 1 means that it is the first attempt to process this message, value 2 means that it is the second attempt, meaning it is the first retry.

</td>
</tr>
<tr>
<td valign="top">

JMSXGroupID

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Defines which message group the message belongs to. This header corresponds to the AMQP header group-id.

</td>
</tr>
<tr>
<td valign="top">

JMSXGroupSeq

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Defines which message group the message belongs to and contains the sequence of the message within the group starting with 1.

</td>
</tr>
<tr>
<td valign="top">

JMSXUserID

</td>
<td valign="top">

Header

</td>
<td valign="top">

AMQP adapter

</td>
<td valign="top">

Specifies the ID of the user creating the message. This header corresponds to the AMQP header user-id.

</td>
</tr>
<tr>
<td valign="top">

Message-ID

</td>
<td valign="top">

Header

</td>
<td valign="top">

Mail adapter

</td>
<td valign="top">

ID that the mail system assigned to the e-mail when it was first created.

</td>
</tr>
<tr>
<td valign="top">

Reply-to

</td>
<td valign="top">

Header

</td>
<td valign="top">

Mail adapter

</td>
<td valign="top">

Message ID of the message that this e-mail is a reply to.

</td>
</tr>
<tr>
<td valign="top">

SAP\_ApplicationID

</td>
<td valign="top">

Header

</td>
<td valign="top">



</td>
<td valign="top">

When you monitor the messages at runtime, you can search for all messages whose defined `SAP_ApplicationID` has a specific value \(displayed as the *Application Message ID* attribute in the Message Monitoring editor\).

> ### Note:  
> Only the first 120 characters are displayed.

As *Type*, select the XPath expression that points to the message element that is to be used as the application ID.

</td>
</tr>
<tr>
<td valign="top">

SapAuthenticatedUserName

</td>
<td valign="top">

Header

</td>
<td valign="top">

SOAP Sender adapter

XI Sender adapter

</td>
<td valign="top">

User name of the client that calls the integration flow.

If the sender channel is configured to use client certificate authentication, no such header is set \(as it is not available in this case\).

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Authentication\_Type

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to dynamically set the value of authentication method.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Content\_Transfer\_Encoding

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to dynamically set the value of the AS2 message encoding type.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Proxy\_Type

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to dynamically set the type of proxy you want to use for connecting to receiver system.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Compress\_Message

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to ensure that the outgoing message is compressed.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Content\_Type

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to dynamically set the value of the content type of an outgoing message.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Encrypt\_Message

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to ensure that the outbound message is encrypted.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Encryption\_Key\_Length

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it specify the public key length.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Encryption\_Algorithm

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to set the relevant AS2 message encryption algorithm, such as:

-   3DES

-   AES128

-   AES192

-   AES256

-   RC2




</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Encryption\_Public\_Key

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to specify the public key alias to encrypt the AS2 message.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Async\_Mdn\_Url

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to specify partner's AS2 URL.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Mdn\_Request\_Mic

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to request an integrity check on MDN.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Mdn\_Request\_Signing

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to request the partner to sign AS2 MDN.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Mdn\_Signing\_Algorithm

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to set the relevant AS2 MDN signing algorithm, such as:

-   SHA1

-   SHA224

-   SHA256

-   SHA384

-   SHA512

-   MD5




</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Mdn\_Type

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to request the partner to send a Message Integrity Check \(MIC\) for an AS2 MDN.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Mdn\_Verify\_Mic

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to verify the MIC of AS2 MDN for synchronous MDN type.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Mdn\_Verify\_Signature

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to verify the signature of AS2 MDN for synchronous MDN type.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Sign\_Message

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to ensure that the outgoing AS2 message is signed.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Signing\_Algorithm

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to set the relevant AS2 message signing algorithm, such as:

-   SHA1

-   SHA224

-   SHA256

-   SHA384

-   SHA512

-   MD5




</td>
</tr>
<tr>
<td valign="top">

SAP\_AS2\_Outbound\_Signing\_Private\_Key\_Alias

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS2 Receiver adapter

</td>
<td valign="top">

Use it to specify the private key alias to sign the AS2 message.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Authentication\_Type

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Push\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically assign values for *Authentication Type* field and choose the authentication type to process the outbound message. The valid values are:

-   saml
-   basic
-   clientCert
-   none



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Username\_Token

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Push\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically assign values for *Username Token* field to specify the relevant password type to be used when a username token is generated from credentials. The valid values are:

-   none
-   hashedPasswordWithTimestamp
-   plainTextPassword
-   plainTextPasswordWithTimestamp



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Security\_Type

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Push\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically assign values for *Sign and Encrypt Message* field and choose whether to sign and encrypt the payload. The valid values are:

-   sign
-   signAndEncrypt
-   none



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Sign\_Message

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Push\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically assign values for *Sign Message* field to ensure that outgoing AS4 message is signed. The valid values are:

-   true
-   false



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Signing\_Algorithm

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Push\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically assign values for*Signature Algorithm* field and set the relevant algorithm to sign the AS4 message. The valid values are:

-   SHA256/RSA
-   SHA384/RSA
-   SHA512/RSA



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Encryption\_Cert

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Push\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically specify an alias for the public key that is to be used to encrypt the message.

</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Encryption\_Algorithm

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Push\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically set values for *Encryption Algorithm* field and specify an encryption algorithm to be applied when encrypting the message. The valid values are:

-   *3DES*

-   *AES128*

-   *AES256*




</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Save\_Receipt

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Push\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically set values for *Save Incoming Receipt* to save incoming receipt in the Message Store for 90 days. The valid values are:

-   true
-   false



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Verify\_Receipt\_Username\_Token

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Push\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically set values for *Verify Username Token* field and set the relevant option for username token verification. The valid values are:

-   notRequired
-   required



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Verify\_Receipt

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Push\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically set values for *Verify Receipt Signature* field and choose whether to verify the incoming receipt signature against the public key alias. The valid values are:

-   true
-   false



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Pull\_Username\_Token

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Pull\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically assign values for *Username Token* field to specify the relevant password type to be used when a username token is generated from credentials. The valid values are:

-   none
-   hashedPasswordWithTimestamp
-   plainTextPassword
-   plainTextPasswordWithTimestamp



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Inbound\_Sign\_Message

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Pull\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically assign values for *Sign Message* field to ensure that outgoing AS4 message is signed. The valid values are:

-   true
-   false



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Inbound\_Signing\_Algorithm

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Pull\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically assign values for*Signature Algorithm* field and set the relevant algorithm to sign the AS4 message. The valid values are:

-   SHA256/RSA
-   SHA384/RSA
-   SHA512/RSA



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Inbound\_Verify\_Sign

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Pull\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically set values for *Verify Signature* field and choose whether to verify the incoming signature. The valid values are:

-   true
-   false



</td>
</tr>
<tr>
<td valign="top">

SAP\_AS4\_Outbound\_Verify\_Response\_Username\_Token

</td>
<td valign="top">

Header

</td>
<td valign="top">

AS4 \(ebMS3 Pull\) Receiver adapter

</td>
<td valign="top">

Use it to dynamically set values for *Verify Username Token* field and set the relevant option for username token verification. The valid values are:

-   notRequired
-   required



</td>
</tr>
<tr>
<td valign="top">

SAP\_BatchLineSeparator

</td>
<td valign="top">

Property

</td>
<td valign="top">

 

</td>
<td valign="top">

Distinguish between win/linux systems.

</td>
</tr>
<tr>
<td valign="top">

SAP\_CorrelateMPLs

</td>
<td valign="top">

Property

</td>
<td valign="top">



</td>
<td valign="top">

Specifies whether message processing logs \(MPLs\) are to be correlated with each other using a correlation ID.

By default, MPL correlation is switched on. To specify this property, select `Constant` as *Type* and enter `True` or `False` as *Value*.

</td>
</tr>
<tr>
<td valign="top">

SAP\_DataStoreCreatedAt

</td>
<td valign="top">

Header

</td>
<td valign="top">

Data Store

</td>
<td valign="top">

The Data Store Get operation adds the timestamp information *Created At* of the data story entry \(in milliseconds since 01 Jan 1970 00:00:00 UTC\).

</td>
</tr>
<tr>
<td valign="top">

SAP\_DataStoreRetries

</td>
<td valign="top">

Header

</td>
<td valign="top">

XI Sender adapter

XI Receiver adapter

</td>
<td valign="top">

Number of retries of a message.

The XI adapter sets this header \(when as *Quality of Service* you have selected*Exactly Once* and as *Temporary Storage* you have chosen the option *Data Store*\).

You can use this header to specify that the behavior of the integration flow changes depending on the number of retries that are actually performed. For example, you can use this header to define that after a certain number of retries the message is routed to a specific receiver \(for example, to send an alert message to a recipient\).

You can use this header in case you configure the XI adapter with Data Store as temporary storage.

You can use this header to capture the number of retries performed by the data store consumer. Allows you to do certain actions based on the number of retries already performed.

</td>
</tr>
<tr>
<td valign="top">

SAP\_DataStoreRetries

</td>
<td valign="top">

Header

</td>
<td valign="top">

Data Store

</td>
<td valign="top">

Indicates the number of retry attempts made by the message. Created by `DataStore` consumers, with a value of 0 on the initial attempt to process the message.

</td>
</tr>
<tr>
<td valign="top">

SAP\_DataStoreExpiresAt

</td>
<td valign="top">

Header

</td>
<td valign="top">

Data Store

</td>
<td valign="top">

The Data Store Get operation adds the timestamp information *Retain Until* of the data story entry \(in milliseconds since 01 Jan 1970 00:00:00 UTC\).

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDI\_Document\_Number

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Includes the document number for the single incoming EDI file.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_DECIMAL\_CHARACTER

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to set the decimal character to be used during message validation. Possible values are 'dot' or 'fromIncomingPayload'.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_CONTRL\_MSG\_VERSION

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to determine the appropriate EDIFACT CONTRL message version to be transmitted to the trading partner.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_CREATE\_ACK

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to process the functional acknowledgement.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_INCLUDE\_UNA

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to include special characters in the UNA segment of a CONTRL message.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_INTERCHANGE\_NUMBER

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Allows the splitter to read the interchange number either from the EDI message or from an assigned set of number ranges.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_UNIQUE\_INTERCHANGE\_NUMBER

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to generate a unique interchange number while generating a acknowledgment message. Possible values are 'required' or 'notRequired'.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_NUMBER\_RANGE

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to define the number range assigned to an interchange number in the functional acknowledgement.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_SCHEMA\_SOURCE

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to validate an EDI interchange against the XSD schema for conversion. The values for the headers can be one of the following:

-   Header

-   IntegrationProject




</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_SOURCE\_ENCODING

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to set the appropriate encoding format of the inbound EDIFACT interchange, such as:

-   UTF-8

-   ISO-8859-1




</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_TRANSACTION\_MODE

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

This feature is available only in Envelope and Message validation mode. The following two options are available:

-   Interchange

-   Message: Allows the splitter to validate the entire EDI interchange as independent individual entities




</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_VALIDATE\_MESSAGE

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Initiates the validation of the split EDI messages.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_EDIFACT\_VALIDATION\_METHOD

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Triggers a validation of either Envelope or Envelope and Message for the EDI content.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_X12\_CREATE\_ACK

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Sets the relevant value for processing functional acknowledgement.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_X12\_EXCLUDE\_AK3\_AK4

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Notifies the splitter to exclude the AK3 and AK4 segments from the functional acknowledgement message.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_X12\_INTERCHANGE\_NUMBER

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Allows the splitter to read the interchange number either from the EDI message or from an assigned set of number ranges.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_X12\_UNIQUE\_INTERCHANGE\_NUMBER

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to generate a unique interchange number while generating a acknowledgment message. Possible values are 'required' or 'notRequired'.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_X12\_NUMBER\_RANGE

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Defines the number range assigned to an interchange number in the functional acknowledgement.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_X12\_SCHEMA\_SOURCE

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Validates an EDI interchange against the XSD schema for conversion.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_X12\_SOURCE\_ENCODING

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Includes the appropriate encoding format of the inbound X12 interchange.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_X12\_TRANSACTION\_MODE

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Validates the transaction.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_X12\_VALIDATE\_MESSAGE\_OPTION

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Performs validation on incoming ASC X12 message against the XSD scheme.

</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_997\_GROUP\_CONTROL\_NUMBER

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to set the group segmnet number in the fucntional acknowledgement message. The values for the headers can be:

-   numberRange
-   useFromEDIMessage
-   predefined



</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_997\_UNIQUE\_GROUP\_CONTROL\_NUMBER

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to generate a group segment set number while generating an acknowledgment message:

-   required
-   notrequired



</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_997\_TRANSACTION\_SET\_NUMBER

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to set the transaction set number in the fucntional acknowledgement message. The values for the headers can be:

-   numberRange
-   predefined



</td>
</tr>
<tr>
<td valign="top">

SAP\_EDISPLITTER\_997\_UNIQUE\_TRANSACTION\_SET\_NUMBER

</td>
<td valign="top">

Header

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Use it to generate a unique transaction set number while generating an acknowledgment message:

-   required
-   notrequired



</td>
</tr>
<tr>
<td valign="top">

SAP\_ERiCResponse

</td>
<td valign="top">

Header

</td>
<td valign="top">

ELSTER Receiver adapter

</td>
<td valign="top">

The ELSTER receiver adapter sets this header. It contains a technical status created by the ERiC \(*ELSTER Rich Client*\) library.

</td>
</tr>
<tr>
<td valign="top">

SAP\_ErrorModelStepID

</td>
<td valign="top">

Property

</td>
<td valign="top">

 

</td>
<td valign="top">

You can use this property to set a Model Step ID for an integration flow step. This identifier is required to relate to an integration flow step in error handling.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpAfterProc

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Handling for Existing Files* parameter.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpAuthMethod

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Authentication* parameter.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpBufferSize

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP adapter

FTP adapter

</td>
<td valign="top">

Dynamic setting of adapter's configuration

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpCreateDir

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

FTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Create Directories* parameter.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpDisconnect

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

FTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Automatically Disconnect* parameter.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpDoneFileName

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

FTP Receiver adapter

</td>
<td valign="top">

Dynamic setting of adapter's configuration.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpEncryption

</td>
<td valign="top">

Property

</td>
<td valign="top">

FTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Encryption* parameter.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpFastExistsCheck

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Use Fast Exists Check* parameter.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpFlattenFileName

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

FTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Flatten File Name* parameter.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpMaxReconnect

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

FTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Maximum Reconnect Attempts* parameter.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpMaxReconDelay

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

FTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Reconnect Delay* parameter.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpMove

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP adapter

FTP adapter

</td>
<td valign="top">

Dynamic setting of adapter's configuration.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpPdUri

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically retrieve a known\_hosts file from the Partner Directory.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpProxyType

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

FTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Proxy Type* parameter.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpStepwise

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

FTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Change Directories Stepwise* parameter.

</td>
</tr>
<tr>
<td valign="top">

SAP\_FtpTimeout

</td>
<td valign="top">

Property

</td>
<td valign="top">

SFTP Receiver adapter

FTP Receiver adapter

</td>
<td valign="top">

You can use this property to dynamically specify the *Timeout* parameter.

</td>
</tr>
<tr>
<td valign="top">

SapIDocType

</td>
<td valign="top">

Header

</td>
<td valign="top">

IDoc Sender adapter

IDoc Receiver adapter

</td>
<td valign="top">

This header contains the IDoc type from the sending system \(for example, `WPDTAX01`\).

</td>
</tr>
<tr>
<td valign="top">

SapIDocTransferId

</td>
<td valign="top">

Header

</td>
<td valign="top">

IDoc Sender adapter

IDoc Receiver adapter

</td>
<td valign="top">

This header contains the incoming IDoc number from the sending system \(for example, `0000000000166099`\).

It corresponds to the field DOCNUM in the IDoc Adapter.

</td>
</tr>
<tr>
<td valign="top">

SapIDocDbId

</td>
<td valign="top">

Header

</td>
<td valign="top">

IDoc Sender adapter

IDoc Receiver adapter

</td>
<td valign="top">

The IDoc receiver adapter sends a request and gets an XML response.

The adapter parses the XML response and generates this header from it. The header contains the IDoc number from the receiver system \(for example, `0000000000160816`\).

</td>
</tr>
<tr>
<td valign="top">

SAP\_IntegrationFlowID

</td>
<td valign="top">

Property

</td>
<td valign="top">

JMS Sender adapter

</td>
<td valign="top">

Contains the ID of the integration flow that sent a message to the JMS queue from which the JMS sender adapter reads it. The property value is set by the JMS receiver adapter that sent the message to the JMS queue. The JMS consumer can use this property to define further steps that depend on the integration flow ID.

</td>
</tr>
<tr>
<td valign="top">

SapQualityOfService

</td>
<td valign="top">

Header

</td>
<td valign="top">

XI Sender adapter

</td>
<td valign="top">

Indicates the quality of service from the sender system \(possible values: `BestEffort`, `ExactlyOnce`\).

</td>
</tr>
<tr>
<td valign="top">

SapPlainSoapQueueId

</td>
<td valign="top">

Header

</td>
<td valign="top">

IDoc Sender adapter

</td>
<td valign="top">

Only relevant if the receiver channel is SAPRM. The header contains the QueueID from the receiver system.

</td>
</tr>
<tr>
<td valign="top">

SAP\_MAIL\_ENCRYPTION\_DETAILS\_DECRYPTION\_ALIAS \(String\)

</td>
<td valign="top">

Property

</td>
<td valign="top">

Mail Sender adapter

</td>
<td valign="top">

The alias used for decryption of an encrypted mail.

</td>
</tr>
<tr>
<td valign="top">

SAP\_MAIL\_ENCRYPTION\_DETAILS\_DECRYPTION\_OK \(boolean\)

</td>
<td valign="top">

Property

</td>
<td valign="top">

Mail Sender adapter

</td>
<td valign="top">

The received mail was successfully decrypted \(not set, true, false\).

</td>
</tr>
<tr>
<td valign="top">

SAP\_MAIL\_ENCRYPTION\_DETAILS\_ENCRYPTED \(boolean\)

</td>
<td valign="top">

Property

</td>
<td valign="top">

Mail Sender adapter

</td>
<td valign="top">

The received mail was encrypted.

</td>
</tr>
<tr>
<td valign="top">

SAP\_MAIL\_ENCRYPTION\_DETAILS\_ERROR\_MESSAGES \(String\)

</td>
<td valign="top">

Property

</td>
<td valign="top">

Mail Sender adapter

</td>
<td valign="top">

There is an error message if the mail could not be decrypted.

</td>
</tr>
<tr>
<td valign="top">

SAP\_MAIL\_ORIGINAL\_MESSAGE

</td>
<td valign="top">

Property

</td>
<td valign="top">

Mail Sender adapter

</td>
<td valign="top">

Provides a ByteArrayOutputStream that contains the original e-mail.

</td>
</tr>
<tr>
<td valign="top">

SAP\_MAIL\_SIGNATURE\_OVERALL\_VERIFICATION\_OK \(boolean\)

</td>
<td valign="top">

Property

</td>
<td valign="top">

Mail Sender adapter

</td>
<td valign="top">

Is true if all signatures could be validated.

</td>
</tr>
<tr>
<td valign="top">

SAP\_MAIL\_SIGNATURE\_DETAILS\_CERTIFICATES \(Array of java.security.cert.X509Certificate\)

</td>
<td valign="top">

Property

</td>
<td valign="top">

Mail Sender adapter

</td>
<td valign="top">

The signer certificate.

</td>
</tr>
<tr>
<td valign="top">

SAP\_MAIL\_SIGNATURE\_DETAILS\_VERIFICATION\_OK \(Array of boolean\)

</td>
<td valign="top">

Property

</td>
<td valign="top">

Mail Sender adapter

</td>
<td valign="top">

The result of the verification.

</td>
</tr>
<tr>
<td valign="top">

SAP\_MAIL\_SIGNATURE\_DETAILS\_ERROR\_MESSAGES \(Array of String\)

</td>
<td valign="top">

Property

</td>
<td valign="top">

Mail Sender adapter

</td>
<td valign="top">

The error message for a failed verification.

</td>
</tr>
<tr>
<td valign="top">

SAP\_MessageType

</td>
<td valign="top">

Header

</td>
<td valign="top">



</td>
<td valign="top">

Makes an application-specific Message Type available for monitoring. When set in the integration flow, this header will be stored in the message processing log. Only the first 100 characters are displayed.

</td>
</tr>
<tr>
<td valign="top">

SAP\_MessageProcessingLogID

</td>
<td valign="top">

Header

</td>
<td valign="top">



</td>
<td valign="top">

Contains the ID of the message processing log.

You can use this property to read the ID of the message processing log \(no write access supported\).

</td>
</tr>
<tr>
<td valign="top">

SAP\_MessageProcessingLogID

</td>
<td valign="top">

Property

</td>
<td valign="top">



</td>
<td valign="top">

Points to the message processing log for the respective Exchange.

You can use this property to read the ID of the message processing log \(no write access supported\).

</td>
</tr>
<tr>
<td valign="top">

SAP\_MessageProcessingLogCustomStatus

</td>
<td valign="top">

Property

</td>
<td valign="top">



</td>
<td valign="top">

You can use this property to set an at most 40 characters alphanumeric custom status for the current message processing log. The value is transferred as `CustomStatus` attribute to the root part of the message processing log and then stored in the message processing log header table.

</td>
</tr>
<tr>
<td valign="top">

SAP\_MessageProcessingLogLevel

</td>
<td valign="top">

Header

</td>
<td valign="top">



</td>
<td valign="top">

If this message header is present for an incoming message, the processing of this message exchange is written with the specified log level. Allowed values are INFO, NONE, DEBUG, ERROR \(case-insensitive\). The header does not get filled by the runtime, so it cannot be used to retrieve the currently set log level.

</td>
</tr>
<tr>
<td valign="top">

SAP\_ODataV2\_RefreshCacheOnExpiry

</td>
<td valign="top">

Property

</td>
<td valign="top">

OData V2 Receiver Adapter

</td>
<td valign="top">

The adapter stores the metadata cache for 1 hour after which it gets invalidated. The adapter looks out for the metadata again that can cause dips in performance every hour. If you face such dips every hour, you can use the message property and set the value to `false`.

</td>
</tr>
<tr>
<td valign="top">

SAP-PASSPORT

</td>
<td valign="top">

Header

</td>
<td valign="top">

 

</td>
<td valign="top">

Stores the encoded SAP-Passport value from which an instance of DSRPassport can be created. This header and the passport format is specified for all SAP solutions.

</td>
</tr>
<tr>
<td valign="top">

SAP\_PollEnrichMessageFound

</td>
<td valign="top">

Property

</td>
<td valign="top">

PollEnrich

</td>
<td valign="top">

The property contains the information if an adapter used in poll enrich has polled any message \(boolean\).

</td>
</tr>
<tr>
<td valign="top">

SAP\_PregeneratedMplId

</td>
<td valign="top">

Header

</td>
<td valign="top">

 

</td>
<td valign="top">

If an exchange is created whose IN-message is carrying this header, the specified ID is used as message processing log ID. In this case, the message processing logs of all retry attempts are grouped together under one header. The header, if used, has to be a Base64-encoded UUID.

</td>
</tr>
<tr>
<td valign="top">

SAP\_ReceiverOverwrite

</td>
<td valign="top">

Property

</td>
<td valign="top">



</td>
<td valign="top">

Defines the handling of the message header `SAP_Receiver` . If set to `true`, the header `SAP_Receiver` will be overwritten with the new value in case a value is assigned to the `SAP_Receiver` header. If set to `false`, the new value is added to the already existent header content. The content is stored as a comma-separated list,

Default value: `java.lang.Boolean.FALSE`

This behavior is helpful in scenarios like,the multicast pattern, for example, where a message is sent to several receivers and all receivers are to be collected in the MPL \(not just the last added header\).

> ### Note:  
> Example configuration:
> 
> *Name*: `SAP_ReceiverOverwrite`
> 
> *Type*: `Constant`
> 
> *Value*: `True`



</td>
</tr>
<tr>
<td valign="top">

SAP\_Receiver

</td>
<td valign="top">

Header

</td>
<td valign="top">



</td>
<td valign="top">

Makes available the name of the receiver to monitoring.

If you have specified `SAP_Sender` or `SAP_Receiver`, the corresponding values are displayed in the message processing log. If you change the `SAP_Receiver` value during message processing, all values are added to the receiver field in the message processing log as a comma-separated list. If you don't want this behavior, you can specify the exchange property `SAP_ReceiverOverwrite` \(see below\).

</td>
</tr>
<tr>
<td valign="top">

SAP\_Sender

</td>
<td valign="top">

Header

</td>
<td valign="top">



</td>
<td valign="top">

Makes available the name of the sender to monitoring.

If you have specified `SAP_Sender` or `SAP_Receiver`, the corresponding values are displayed in the message processing log. If you change the `SAP_Receiver` value during message processing, all values are added to the receiver field in the message processing log as a comma-separated list. If you don't want this behavior, you can specify the exchange property `SAP_ReceiverOverwrite` \(see below\).

</td>
</tr>
<tr>
<td valign="top">

SAP\_SuccessFactorsHasMoreRecords.<channelName\>

</td>
<td valign="top">

Property

</td>
<td valign="top">

SuccessFactors adapter

Soap adapter

</td>
<td valign="top">

Used looping process call modelling.

</td>
</tr>
<tr>
<td valign="top">

SAP\_XadesSigningTimeZone

</td>
<td valign="top">

Property

</td>
<td valign="top">

XML Signer

</td>
<td valign="top">

If this exchange property is set, the XML Signer step transforms the value of the XAdES `SigningTime` element into the time zone specified by the property value.

The property shall contain a value of the format `GMT+HH:mm` or `GMT-HH:mm`, where HH are the hours and mm are the minutes after or before Greenwich Mean Time \(GMT\). The GMT zone is used if the given string property value can't be interpreted. If the property contains a non-string value, an exception is thrown. If the property is not set, the time zone GMT is used.

For example, if you set the property value to `GMT+3:00`, the time zone 3 hours ahead Greenwich Mean Time is used.

</td>
</tr>
<tr>
<td valign="top">

SAP\_XmlValidationResult

</td>
<td valign="top">

Header

</td>
<td valign="top">

XML Validator

</td>
<td valign="top">

Adds the error payload.

</td>
</tr>
<tr>
<td valign="top">

SAP.DisableAttachments.HTTP

</td>
<td valign="top">

Header

</td>
<td valign="top">

HTTP Adapter

</td>
<td valign="top">

Enables the creation of attachments for request header, response headers, and response body when the message processing fails.

</td>
</tr>
<tr>
<td valign="top">

SAP.DisableAttachments.ODataV2

</td>
<td valign="top">

Header

</td>
<td valign="top">

OData V2 Receiver Adapter

</td>
<td valign="top">

Enables the creation of attachments for request header, response headers, and response body when the message processing fails.

</td>
</tr>
<tr>
<td valign="top">

SAP.DisableAttachments.ODataV4

</td>
<td valign="top">

Header

</td>
<td valign="top">

OData V4 Receiver Adapter

</td>
<td valign="top">

Enables the creation of attachments for request header, response headers, and response body when the message processing fails.

</td>
</tr>
<tr>
<td valign="top">

SapDataStoreId

</td>
<td valign="top">

Header

</td>
<td valign="top">

Data Store

</td>
<td valign="top">

Entry ID used/set by the Data Store component.

</td>
</tr>
<tr>
<td valign="top">

SapDataStoreMaxResults

</td>
<td valign="top">

Header

</td>
<td valign="top">

Data Store

</td>
<td valign="top">

Used dynamically overwrite the configured number of polled messages in case of Data Store `SELECT` operation.

</td>
</tr>
<tr>
<td valign="top">

SapInterfaceName

</td>
<td valign="top">

Header

</td>
<td valign="top">

XI adapter

</td>
<td valign="top">

XI protocol header

</td>
</tr>
<tr>
<td valign="top">

SapInterfaceNamespace

</td>
<td valign="top">

Header

</td>
<td valign="top">

XI adapter

</td>
<td valign="top">

XI protocol header

</td>
</tr>
<tr>
<td valign="top">

SAPJMSAlerttime

</td>
<td valign="top">

Header

</td>
<td valign="top">

JMS Consumer

</td>
<td valign="top">

Specifies the time when an alert needs to be sent.

> ### Note:  
> This header is only set for non-exclusive queues.



</td>
</tr>
<tr>
<td valign="top">

SAPJMSRetries

</td>
<td valign="top">

Header

</td>
<td valign="top">

JMS Consumer

</td>
<td valign="top">

Number of retries of a JMS message.

The JMS sender adapter sets this header.

> ### Note:  
> This is only the case if the *Non-Exclusive* access type is selected.

You can use this header to specify that the behavior of the integration flow changes depending on the number of retries that are actually performed. For example, you can configure a scenario where a mail is sent to an administrator with the message as an attachment and the integration flow is terminated successfully after a specified number of retries.

You can use this header in case you configure the XI adapter with JMS Queue as temporary storage.

</td>
</tr>
<tr>
<td valign="top">

SAPJMSRetryAt

</td>
<td valign="top">

Header

</td>
<td valign="top">

JMS Consumer

</td>
<td valign="top">

This header is set for queues with non-exclusive access type.

</td>
</tr>
<tr>
<td valign="top">

SapMessageId

</td>
<td valign="top">

Header

</td>
<td valign="top">

SOAP \(SAP RM\) Sender adapter

XI adapter

IDoc Receiver adapter

</td>
<td valign="top">

SAPRM, IDoc, and XI protocol header for the message identifier

</td>
</tr>
<tr>
<td valign="top">

SapMessageIdEx

</td>
<td valign="top">

Header

</td>
<td valign="top">

SOAP \(SAP RM\) Sender adapter

XI adapter

</td>
<td valign="top">

SAPRM and XI protocol header for the message identifier.

</td>
</tr>
<tr>
<td valign="top">

SapPlainSoapQoS

</td>
<td valign="top">

Header

</td>
<td valign="top">

SOAP \(SAP RM\) adapter

</td>
<td valign="top">

Header for SoD scenario. Is generated in SAP-RM adapter.

</td>
</tr>
<tr>
<td valign="top">

SapReceiverParty

</td>
<td valign="top">

Header

</td>
<td valign="top">

XI adapter

</td>
<td valign="top">

XI protocol header

</td>
</tr>
<tr>
<td valign="top">

SapReceiverService

</td>
<td valign="top">

Header

</td>
<td valign="top">

XI adapter

</td>
<td valign="top">

XI protocol header

</td>
</tr>
<tr>
<td valign="top">

SapRefToMessageId

</td>
<td valign="top">

Header

</td>
<td valign="top">

XI adapter

</td>
<td valign="top">

XI protocol header

</td>
</tr>
<tr>
<td valign="top">

SapRefToMessageIdEx

</td>
<td valign="top">

Header

</td>
<td valign="top">

XI adapter

</td>
<td valign="top">

XI protocol header

</td>
</tr>
<tr>
<td valign="top">

SapSenderParty

</td>
<td valign="top">

Header

</td>
<td valign="top">

XI adapter

</td>
<td valign="top">

XI protocol header

</td>
</tr>
<tr>
<td valign="top">

SapSenderService

</td>
<td valign="top">

Header

</td>
<td valign="top">

XI adapter

</td>
<td valign="top">

XI protocol header

</td>
</tr>
<tr>
<td valign="top">

Sender

</td>
<td valign="top">

Header

</td>
<td valign="top">

Mail adapter

</td>
<td valign="top">

Specifies the actual sender \(acting on behalf of the e-mail address stated in the From header\).

</td>
</tr>
<tr>
<td valign="top">

SOAPAction

</td>
<td valign="top">

Header

</td>
<td valign="top">

SOAP adapter

</td>
<td valign="top">

This header is part of the Web service specification.

</td>
</tr>
<tr>
<td valign="top">

Subject

</td>
<td valign="top">

Header

</td>
<td valign="top">

Mail adapter

</td>
<td valign="top">

Specifies the subject of the e-mail message.

</td>
</tr>
<tr>
<td valign="top">

To

</td>
<td valign="top">

Header

</td>
<td valign="top">

Mail adapter

</td>
<td valign="top">

Specifies the e-mail address that the message is sent to.

</td>
</tr>
<tr>
<td valign="top">

CamelLoopIndex

</td>
<td valign="top">

Property

</td>
<td valign="top">

Looping Process Call

</td>
<td valign="top">

Provides the index of the currently processed loop \(starting with 0\).

</td>
</tr>
</table>

**Related Information**  


[Dynamic Parameters \(Example\)](dynamic-parameters-example-5705f2b.md)

[About Headers and Exchange Properties](about-headers-and-exchange-properties-0974c4f.md "")

