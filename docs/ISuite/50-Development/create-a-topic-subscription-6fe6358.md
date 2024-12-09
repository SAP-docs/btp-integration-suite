<!-- loio6fe6358f4bbd407c9fb67a2554787c61 -->

# Create A Topic Subscription

Understand how to create a topic subsciption from a queue.



## Context

When you send a message via AMQP 1.0 over WebSocket, it can be published to a queue or topic. Topics form a logical tree to organize messages in a folder-like hierarchy in a file system. Therefore, topics appear as strings, consisting of multiple segments, separated by one defined delimiter. A topic syntax depends on the protocol that is used. The topic syntax must follow the mechanisms defined by individual messaging protocols.

To send messages to a topic, create a topic with the correct naming syntax as follows:

-   A topic name must be limited to 150 characters.

-   A topic name must contain at least two segments separated by a forward slash \( / \) as a segment separator.

    The segment separator must not appear at the beginning or ending.

-   A topic name can contain forward slash \( / \) only as segment separator.

-   A topic name can include these characters: alphanumeric, underscore \( \_ \), period \( . \), and hyphen \( - \).

-   A maximum of 20 segments can be used.

-   Empty segments aren't allowed.

-   Use asterisk \( \* \) as a wildcard to represent a subtree of segments only at the end of the name.

-   Use plus \( + \) as a wildcard to represent a single segment with any content that is valid, but always the whole segment.




## Procedure

1.  Choose *Configure* \> *Event Mesh*. Navigate to the *Queues* tab.

2.  Choose the queue for which you want to create a topic subscription.

3.  Navigate to the *Subscriptions* tab.

4.  Choose *Create*.

5.  Provide a name or a pattern.

6.  Choose *Create*.


