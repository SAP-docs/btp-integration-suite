<!-- loiob9c2354da3bd4b029af109a0413c9be9 -->

# Read Multiple Attachments Based on Filter Criteria

In this use case, several attachments are sent to an integration flow, and only a subset of them are processed based on a particular filter criteria.

The *Attachment Handling - Read Multiple Attachments Based On Filter Criteria* integration flow illustrates this guideline.

![](images/Read_Multiple_Attachments_Based_On_Filter_Criteria_2cafdce.png)

In this example, a SOAP sender adapter is used to receive a message with several attachments.

To be able to test the filter criteria, the SOAP request expects the header `FileNameContains`.

The groovy script step *Store Attachment* gets all attachments and saves the list in a property that is to be accessed later. It also saves the attachment count for the following loop.

```
def Message saveAttachments(Message message) {

    // Store attachments in property
    def attachments = new HashMap<String, DataHandler>(message.getAttachments())
    message.setProperty('AttachmentsMap', attachments)
    message.setProperty('New_Body', '')
     
    // Store the number of attachments in property
    message.setProperty('AttachmentCount', attachments.size())
    // Clear the attachments
    message.getAttachments().clear()
    message.getAttachmentWrapperObjects().clear()

    return message
}

```

The looping process call step *Process Attachments* checks if the attachment count is greater than `0`. If that's the case, the script step *Process Next Attachment *gets the next attachment from the list.

The script checks each attachment, and if the filter criteria applies, they replace the body of the message with the content of the particular attachment and set property `Flag` to `true`. Then, the attachment is removed from the list and the attachment count is updated. The latter step is checked in the next iteration.

```
def Message getNextAttachment(Message message) {
    message.setProperty('Flag', false)
    def attachments = message.getProperty('AttachmentsMap')
    if (attachments.isEmpty()) {
        throw new AssertionError('No attachments found')
    }
    // Get next attachment to be processed
    def nextAttch = attachments.keySet().iterator().next()
    // Remove the attachment from the Map
    def attachment = attachments.remove(nextAttch)
    def headers = message.getHeaders();
    def filterValue = headers.get("FileNameContains")
    
    if(attachment.getName().contains(filterValue)){
        // Replace the message with attachment
        message.setBody(attachment.getContent())
        // message.setProperty('AttachmentCount', attachments.size())
        message.setHeader('receiver', attachment.getName())
        message.setProperty('New_Body',message.getProperty('New_Body') +  attachment.getContent())
        message.setProperty('Flag', true)
    }
   
    // Update the AttachmentCount
    message.setProperty('AttachmentCount', attachments.size())
    return message
}

```

In the next step, the router verifies if the `Flag` is set. If that's the case, the attachment is sent to the *Generic Receiver* flow.

To test the scenario, perform the following steps:

1.  Set up inbound *Basic* authentication for integration flow endpoints.

    See: [Basic Authentication with clientId and clientsecret for Integration Flow Processing](../40-RemoteSystems/basic-authentication-with-clientid-and-clientsecret-for-integration-flow-processing-647eeb3.md)

2.  Deploy the integration flow *Read Multiple Attachments Based On Filter Criteria*.

3.  In the Postman client, open the *HandlingAttachments* folder in the *ModelingBasics* collection, and run the *ReadMultipleAttachmentsBasedOnFilter*  request. The sample message contains a SOAP message with a list of product IDs and six attachments. By default, the the header `FileNameContains` is set to `HT-1080`.

4.  You'll see only the filtered attachments in the data store, in our case two entries with the IDs `ProductDetails-HT-1080.xml` and `SupplierDetails-HT-1080.txt`, respectively.

5.  Re-run the request with different values for the header `FileNameContains`, for example, try out `txt` or Details.

    > ### Note:  
    > Before re-running the request, clean up the data store.


