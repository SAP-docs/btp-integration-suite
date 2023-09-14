<!-- loioeaf929e1e9ac4185b18b545df104f50f -->

# Guidelines to Implement Specific Integration Patterns

Cloud Integration supports the implementation of enterprise integration patterns that are also referred to as *integration patterns* or *messaging patterns*.

For more information about enterprise integration patterns, see [https://www.enterpriseintegrationpatterns.com/patterns/messaging/toc.html](https://www.enterpriseintegrationpatterns.com/patterns/messaging/toc.html)

An example of an enterprise integration pattern is the content-based router. As an example, assume that a sender is connected to multiple receiver systems. The business process requires that a message from the sender is forwarded to a particular receiver system depending on the content of the message \(for example, a customer ID\). The content-based router makes such forwarding possible.

Another example is the splitter, which defines that a single message is split into multiple partial messages that can be processed individually.

This section provides simple example integration flows to show how to implement enterprise integration patterns.

You can find the integration flows in the following integration package published on SAP Business Accelerator Hub:

> ### Note:  
> You can find the example integration flows that illustrate the guidelines explained in this section in the following integration package published on SAP Business Accelerator Hub:
> 
> [Integration Flow Design Guidelines - Enterprise Integration Patterns](https://api.sap.com/package/DesignGuidelinesPatterns?section=Overview) 
> 
> For more information, see [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md).

> ### Note:  
> It can be the case that you've applied the integration flow design guidelines described in this section to your best knowledge, but you still face issues during the operation of the scenario. For example, you have applied all design rules with regard to performance but still the performance isn't good enough at runtime. In such cases, you can check out the following page to search for a service that helps you to optimize the implementation of your scenario: [SAP Services and Support](https://www.sap.com/services-support.html).

**Related Information**  


[Aggregator](aggregator-5f5e01b.md "You want to combine related individual messages so that they can be processed in bulk. Using an Aggregator pattern, you can collect and store individual messages until a complete set of related messages has been received. The aggregated message is then sent to the actual receiver.")

[Composed Message Processor](composed-message-processor-353a119.md "You want to handle a message with multiple elements, and each element requires different processing. You use a Composed Message Processor pattern to split the message into multiple sub messages, route the split messages to different destinations, and then reaggregate the responses back into one single message.")

[Content-Based Routing](content-based-routing-90f35f3.md "Let's assume that you've an order process where the order can be handled by a specific inventory system depending on the shipping address. Content-based routing forwards the message to the right recipient, depending on the content of a message.")

[Content Enricher](content-enricher-0e7ba7f.md "You want to send an order to a supplier but you can't provide all the information that the receiver system requires to process the order. For instance, the items only contain a product category code but the main category name is missing. The Content Enricher reads data synchronously from an external system, and appends the additional information to the original message before routing to the actual receiver.")

[Content Filter](content-filter-6fd4a86.md "Assume that you get an order from a partner in a standard format that you've agreed upon. The message contains numerous fields that are required for communicating with your partner, however your backend system only needs a small fraction of the fields.")

[Message Filter](message-filter-bd52346.md "You can use the Message Filter pattern to remove any data from a channel that you aren't interested in.")

[Recipient List](recipient-list-06594b9.md "")

[Resequencer](resequencer-068cfc7.md "If you want to reorder individual messages that have been received by Cloud Integration in a wrong order, you can use an Aggregator pattern which allows you to collect individual messages in bulks, sorted by sequence number. To revert the message bulks into multiple individual messages again, use the Splitter pattern and send the individual messages to the receiver.")

[Scatter-Gather](scatter-gather-987eef2.md "You want to send a message to multiple recipients and each of them sends a reply that needs to be collected. With the Scatter-Gather pattern, you can broadcast a message to multiple recipients and reaggregate the responses back into a single message.")

[Splitter](splitter-4b475ea.md "If a message contains multiple elements but each element needs to be processed in a different way, you can use the Splitter pattern to break up the message into multiple individual messages according to the number of elements.")

[Quality of Service Exactly Once](quality-of-service-exactly-once-f96cf27.md "")

