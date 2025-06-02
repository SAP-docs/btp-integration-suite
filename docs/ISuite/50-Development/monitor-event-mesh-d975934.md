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
-   Destination: Destination of the message
-   DMQ Eligible: Indicates whether the message is eligible for the Dead Message Queue \(DMQ\).

> ### Note:  
> -   The number of messages displayed for a a queue is a specific value that is recorded at a particular point in time, and can change rapidly depending on the consumers and producers accessing the system.
> -   The Message ID and Correlation ID could be empty depending on the message client behavior.



### Bridge

If an Event Mesh bridge has been created, you can monitor the message rate for all the topics in the bridge. You can also view the data for *Spool Size*, *Connections* and *Consumers*.

