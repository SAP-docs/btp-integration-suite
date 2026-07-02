<!-- loioa448605c3c5545a9970704778cf4236a -->

# AS4 Sender Adapter

You use AS4 message exchange protocol to securely process incoming business documents using Web services.

The SAP Applicability Statement4 \(AS4\) sender adapter is based on the ebMS specification that supports the ebMS handler conformance profile. For more information, see [AS4 Profile of ebMS 3.0 Version 1.0](http://docs.oasis-open.org/ebxml-msg/ebms/v3.0/profiles/200707/csd03/AS4-profile-csd03.html).

Let's look at how a message is processed: the incoming AS4 message consists of a SOAP body and the business payload as an attachment. During processing, the payload is extracted from the attachment and allocated to the related Camel routes. To get a more detailed understanding of the functionality of the AS4 adapter,explained with a scenario, read the blog on [Cloud Integration – Working with AS4 adapter](https://blogs.sap.com/2019/02/12/cloud-integration-working-with-as4-adapter/).

> ### Note:  
> It is expected that the incoming AS4 message has an empty SOAP body, otherwise processing-related errors can occur.

**Related Information**  


[Configure the Sender Channel with ebMS3 Pull](configure-the-sender-channel-with-ebms3-pull-4f5ddb3.md "Configure the sender channel with the AS4 adapter with ebMS3 Pull as a sending Message Service Handler (MSH).")

[Configure the Sender Channel with ebMS3 Push](configure-the-sender-channel-with-ebms3-push-3dc3907.md "Allows you configure the sender channel with the AS4 adapter with ebMS3 Push as a receiving Message Service Handler (MSH).")

[Configure the Sender Channel with ebMS3 Receipt](configure-the-sender-channel-with-ebms3-receipt-428ae65.md "Allows the sender channel to transmit the receipt for an incoming push message.")

