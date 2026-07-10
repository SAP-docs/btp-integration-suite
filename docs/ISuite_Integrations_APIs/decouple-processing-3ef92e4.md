<!-- loio3ef92e499e5b4a4499116e7934816d40 -->

# Decouple Processing

Learn how to decouple processing.

Decoupling processing \(also referred to as *asynchronous decoupling*\) means that the processing of the integration scenario is decoupled asynchronously between the sender and the integration flow.

Such a setup has the following advantage: It’s ensured that if there's a failure during processing \(after the call has been persisted\) a retry is done from the integration system rather than the sender system. The sender isn’t blocked while its service request is still being processed by Cloud Integration.

However, this setup comes also with the implication that the sender doesn’t get any information about the actual status of the message processing on the Cloud Integration tenant automatically. To fetch this information, additional measures are required, for example, an additional call from the sender or an API on the sender to push this information from Cloud Integration.

There are various options to implement asynchronous decoupling – either with or without persistence. Persistence refers to the option to store data temporarily on the Cloud Integration tenant.

> ### Note:  
> For more information, see [Copying the Integration Package and Deploying the Integration Flows](copying-the-integration-package-and-deploying-the-integration-flows-2cb1d31.md).

To apply this design guideline, consider the following rules:

[Decouple Sender and Flows Without Persistence](decouple-sender-and-flows-without-persistence-31d4dec.md)

[Decouple Sender and Flows Using Persistence](decouple-sender-and-flows-using-persistence-c5591df.md) \(using either the data store or JMS message queues\)

