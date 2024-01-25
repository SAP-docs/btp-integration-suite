<!-- loio97789c9d635e4a17b2ab4f369d48007f -->

# Apply the Retry Pattern

Apply the retry pattern for handling anticipated, temporary failures when connecting to an external component.

If an error occurs during the processing of an asynchronous scenario, the sender component usually gets an error and has to handle the reprocessing of the message at a later point in time. The sender system needs to contain a retry mechanism.

A better method is to trigger retries directly from SAP Integration Suite . The sender, in such a case, simply delivers the message and doesn't need to worry about retries if error occurs. Retry is handled by the SAP Integration Suite component.



<a name="loio97789c9d635e4a17b2ab4f369d48007f__section_btr_pqx_sjb"/>

## Implementation

SAP Cloud Integration provides various options for implementing such a retry pattern:

-   [Apply the Retry Pattern with JMS Queue](apply-the-retry-pattern-with-jms-queue-da17d2d.md)

    SAP Integration Suite offers storage to persist data in transit during message processing, namely the message queue storage used by the JMS adapter. Use this storage to persist the message at the beginning of the processing sequence. That way, processing is executed faster for the sender, who immediately receives a response with HTTP code 202 \(Accepted\), and the subsequent processing steps are executed asynchronously.

    With this storage option, a retry mechanism is also in place that works as follows: If message processing fails due to a temporary error when calling an external component, the storage can be used to persist the failed messages. The JMS adapter polls the storage regularly for content, and triggers the reprocessing of the respective messages.

-   You can also use the data store to store the messages if there's an error. You can use a looping process call to check the data store for content if there are errors. You can also use a 2nd integration flow with a Data Store sender adapter to regularly check the data store for content, and trigger the reprocessing of the respective messages.

    See: [Data Store Sender Adapter](data-store-sender-adapter-4f5ef3f.md)

-   In addition, some adapters that pull data from an external component, like the SFTP adapter, natively offer a capability to configure the number of retries for calls to external components.


