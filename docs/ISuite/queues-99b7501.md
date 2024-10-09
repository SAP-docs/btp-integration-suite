<!-- loio99b7501e56984ab094affb7c144fb144 -->

# Queues

Events are stored in queues on the broker.

A queue is an endpoint configured with topic subscriptions that can publish messages to and consume messages from. Queues can subscribe to more than one topic and receive messages for all topics matching their subscriptions.

There are two types of queues:

-   **EXCLUSIVE** – only one consumer exclusively can access the queue at any point in time.

-   **NON-EXCLUSIVE** – multiple consumers can access the queue at any point in time.


Queues work like queues in all message queuing systems:

1.  Producers send guaranteed messages to Event Mesh.

2.  The messages are saved in the queue and delivered to consuming clients if they are online, or held in the queue until the consumer connects.

3.  The consumer acknowledges the message once it has completed processing it.

4.  Event Mesh removes the message from the queue.


**Related Information**  


[Create A Queue](50-Development/create-a-queue-95357fa.md "Understand how to create queues.")

