<!-- loio274de7ba389a4077b0cbfd077acb5473 -->

# Data Protection and Privacy for Event Mesh

Understand how Event Mesh handles data protection and privacy.

Event Mesh doesn't read, enrich, or process the events that are sent. As a plain infrastructure component, Event Mesh offers transport and storage of messages.

Message content and storage duration are customer's responsibility. Messages are stored until they’re received by subscribing applications. Event Mesh doesn’t access the content of the messages.

In case, messages are being sent that contain personal data, it’s recommended to:

-   Enable only trusted applications subscribe the messages

-   Ensure that proper access control is implemented within the publishing and subscribing applications.

-   Ensure that messages aren’t stored longer than necessary in queues. For example, by consuming the messages instantly or by specifying a "time to live" either for the message \(supported with AMQP 1.0\) or for the queue \(supported by Event Mesh\).


