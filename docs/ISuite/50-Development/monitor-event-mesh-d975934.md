<!-- loiod9759347ca4b4f0d9ecb67dfdb47a3aa -->

# Monitor Event Mesh

Observe the usage of Event Mesh resources.

The monitoring page gives an overview of the Event Mesh resources like spool size, queues, connection, and consumers. You also see the number of messages that are handled by the broker.

To access the monitoring page, from the left navigation panel navigate to *Monitor* \> *Event Mesh*.

The tabs available here are:





### Overview

On the *Overview* tab you can find the following:

-   Message Rate:

    The chart show the number of messages that were handled by the message broker over a period of time. Published messages \(ingress\) and consumed messages \(egress\) are differentiated using different colors. You can change the time of measure to understand the volume of messages handled by the message broker.

-   Resource Usage:

    Observe the usage of the resources like spool size, queues, connection, and consumers with the help of easy-to-use cards.




### Queues

For queues, the following usage information can be viewed for each queue:

-   Name: The name of the queue.
-   Messages Queued: Number of messages in the queue.
-   Unacknowledged Messages: Number of unacknowledged messages in the queue.
-   Queue Size: The queue size in bytes.
-   Maximum Queue Size: The maximum size possible for the queue.

Choosing a particular queue will enable you to see the following usage information for the messages in the queue:

-   Message ID: The unique identifier of the message.
-   Correlation ID: An identifier to trace the request journey.
-   Time Sent: Time the message was sent.
-   Message size: The size of the message content, in bytes.
-   Redelivered: Indicates if the message was redelivered or not.
-   Delivery Count: The number of times a message has been delivered. Each time the message remains unacknowledged or unprocessed, the broker retries delivery. This count reflects the number of delivery attempts.
-   Spool Time: The timestamp marking when the message was first stored in the queue. This indicates when the message began waiting in the spool before being consumed.
-   Expiration: The timestamp marking when the message will expire in the queue. After this time, the message is no longer eligible for delivery and may be purged or sent to a DMQ.
-   Destination: Destination of the message
-   DMQ Eligible: Indicates whether the message is eligible for the Dead Message Queue \(DMQ\).

Select a message to see the following:

Under *Headers* you see:

-   Identifiers: There are two identifiers for the message:
    -   Message ID and Correlation ID

-   Delivery Information:
    -   Time Sent: Time the message was sent
    -   Redelivered: Indicates if redelivery of the message was ever attempted.
    -   Undelivered: Indicates if the message was never delivered.
    -   Delivery Count: The number of times the message has been redelivered.
    -   Delivery Mode: The mode which is used for message delivery.

-   Routing Information:
    -   Destination: The destination of the message
    -   Reply To: The address or topic to which the recipient should send the response, when a message that requires a reply or acknowledgment, is published.
    -   DMQ Elgible: Indicates whether the message is eligible for the Dead Message Queue \(DMQ\)

-   Additional Information: Message size in bytes.

Under *Properties* you can view the properties defined for the message. These are usually unique to the message and can be used to filter for the message from the several in the queue.

If you have the *EventMeshBusinessExpert* role assigned to you, you can view custom properties for the message, view and download the message payload from the *Payload* section before consuming the message, and delete the messages.

> ### Note:  
> -   The number of messages displayed for a a queue is a specific value that is recorded at a particular point in time, and can change rapidly depending on the consumers and producers accessing the system.
> -   The Message ID and Correlation ID could be empty depending on the message client behavior.



### Bridge

If an Event Mesh bridge has been created, you can monitor the message rate for all the topics in the bridge. You can also view the data for *Spool Size*, *Connections* and *Consumers*.

