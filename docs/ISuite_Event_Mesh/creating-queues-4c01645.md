<!-- loio4c0164579949408ba08a0848679abb21 -->

# Creating Queues

Queues are messaging resources that hold messages sent via AMQP 1.0 or MQTT 3.1.1 over WebSocket, or via HTTP until they're consumed.

A queue is a messaging resource used to store and deliver messages between publishers and consumers. When a message is sent via AMQP 1.0 or MQTT 3.1.1 over WebSocket, or via HTTP, it can be published to a queue or a topic. Messages held in a queue remain there until they're consumed, expire based on the configured time-to-live, or exceed re-delivery limits.

Each queue is defined by a set of configuration parameters — such as name, access type, queue size, message size, re-delivery behavior, and time-to-live — that determine how messages are stored, delivered, and retained.



## Queue Naming Syntax

Queue names must follow this naming syntax:

-   The queue name must be limited to 164 characters.
-   The queue name can include alphanumeric characters, underscore \( \_ \), period \( . \), and hyphen \( - \).
-   The queue name can contain a forward slash \( / \) only as a segment separator.

