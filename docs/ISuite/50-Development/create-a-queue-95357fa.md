<!-- loio95357fa3b6a04328ad933f8df0ab7e8d -->

# Create A Queue

Understand how to create queues.



<a name="loio95357fa3b6a04328ad933f8df0ab7e8d__context_akk_h2f_4bc"/>

## Context

When you send a message via AMQP 1.0 over WebSocket, it can be published to a queue or topic. To send messages to a queue, create a queue with the correct naming syntax as follows:

-   The queue name must be limited to 164 characters.

-   The queue name can include these characters: alphanumeric, underscore \( \_ \), period \( . \), and hyphen \( - \).

-   The queue name can contain forward slash \( / \) only as segment separator.




## Procedure

1.  Choose *Configure* \> *Event Mesh*. Navigate to the *Queues* tab.

2.  Choose *Create*.

    The *Create Queue* wizard comes up.

3.  Provide a name for the queue.

4.  Select an access type:

    -   *NON EXCLUSIVE* – any number of consumers can receive messages at any time from the queue in a round-robin schedule.

    -   *EXCLUSIVE* – only one consumer can receive messages at any time from the queue.


5.  Define the *Queue Size* in bytes. The default and maximum supported queue size are 1.5 GB \(in bytes\).

6.  Define the *Message Size* in bytes. The message size is the maximum amount of data per message that can be spooled in the queue. The default and maximum supported size are 1 MB \(in bytes\).

7.  Define the *Max Unacknowledged Messages Per Consumer* which is the threshold for the number of unacknowledged messages. If there are more unacknowledged messages than the threshold, all subsequent messages are not delivered.

8.  Define the *Max Redelivery Count* which is the maximum number of times the queue attempts redelivery of a message before purging \(removing\) it. If you define a dead message queue, then the queue moves the undelivered messages to it. By default, the value is set to zero. The maximum value that you can define is 255.

9.  Select a *Dead Message Queue*. Unacknowledged messages that have either reached maximum redelivery count or maximum time-to-live in the queue are moved to the dead message queue.

    > ### Note:  
    > You must first create a queue to use it as a dead message queue.

10. Define the *Max Time-to-live* in seconds which is the duration that a message can stay in the queue without being consumed. The default and maximum supported duration are 7 days \(in seconds\). After the defined duration, the queue purges the message. If you like to persist the message even after the duration, define a dead message queue.

11. Choose *Create*.


