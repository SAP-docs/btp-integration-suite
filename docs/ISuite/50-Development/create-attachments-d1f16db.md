<!-- loiod1f16dbf415a449690bdc2452df7c3f4 -->

# Create Attachments

In this use case, multiple files with different content type are created and attached to a message.

The *Attachment Handling – Create Attachments* integration flow illustrates this guideline.

![](images/Attachment_Handling_Create_Attachment_6976def.png)

In this example, a SOAP sender adapter receives an XML message that contains product details.The integration flow uses the information from the request message in order to create attachments with different content type. That way, finally, the SOAP response contains a new XML message body and three attachments:

-   The original XML message

-   The product details as CSV file

-   A text file


For each attachment, Cloud Integration carries out the same Groovy script.

Cloud Integration passes on the content of the attachment to the script in the message body and reads the content type from the `Content-Type` header.

The *Create attachment* Groovy script performs the following steps:

1.  Defines the suffix of the to be attached file based on the `Content-Type` header.

2.  Reads the body of the message.

3.  Sets the MIME type accordingly.

4.  Adds the body as attachment to the message.


```
import com.sap.gateway.ip.core.customdev.util.Message
import org.apache.camel.impl.DefaultAttachment
import com.sap.gateway.ip.core.customdev.util.AttachmentWrapper
import javax.mail.util.ByteArrayDataSource

def Message processData(Message message) {

    // Get content type
    def headers = message.getHeaders()
    def contentType = headers.get("Content-Type")
    
    // Define suffix
    def suffix = contentType.substring(contentType.indexOf("/")+1)
    if(suffix == "plain"){
        suffix = 'txt'
    }

    // Get message payload as input stream
    def body = message.getBody(InputStream.class)

    // Set MIME type
    def dataSource = new ByteArrayDataSource(body, contentType)

    // Construct a DefaultAttachment object
    def attachment = new AttachmentWrapper(dataSource)

    // Add the attachment to the message
    message.addAttachmentObject('attachment.' + suffix, attachment)

    return message;
}
```

> ### Note:  
> SOAP supports multiple files attached to the message exchange. Alternatively, you can apply the script when using any other protocol supporting attachments such as when sending an email with attachments to a mail server.

To test the scenario, perform the following steps:

1.  Set up inbound *Basic* authentication for integration flow endpoints.

    See: [Basic Authentication with clientId and clientsecret for Integration Flow Processing](../40-RemoteSystems/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)

2.  Deploy the integration flow *Attachment Handling – Create Attachment*.

3.  In the Postman client, open the *HandlingAttachments* folder in the *ModelingBasics* collection, and run the*CreateAttachments* request. The sample message contains a SOAP message with two products..

4.  You should receive a multipart message as response containing three attachments.


> ### Note:  
> Optionally, you can use SoapUI to send the sample SOAP message to the integration flow end point.

