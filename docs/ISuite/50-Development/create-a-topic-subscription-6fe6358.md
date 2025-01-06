<!-- loio6fe6358f4bbd407c9fb67a2554787c61 -->

# Create A Topic Subscription

Understand how to create a topic subsciption from a queue.



## Context

When you send a message via [AMQP 1.0 over WebSocket,](https://help.sap.com/docs/integration-suite/sap-integration-suite/publish-and-consume-events?version=CLOUD#advanced-message-queuing-protocol-amqp-1-0-over-websocket) it can be published to a queue or topic. Topics form a logical tree to organize messages in a folder-like hierarchy in a file system. Therefore, topics appear as strings, consisting of multiple segments, separated by one defined delimiter. A topic syntax depends on the protocol that is used. The topic syntax must follow the mechanisms defined by individual messaging protocols.

To send messages to a topic, create a topic with the correct [Topic Naming Syntax](../topic-naming-syntax-62460b8.md).



## Procedure

1.  Choose *Configure* \> *Event Mesh*. Navigate to the *Queues* tab.

2.  Choose the queue for which you want to create a topic subscription.

3.  Navigate to the *Subscriptions* tab.

4.  Choose *Create*.

5.  Provide a name or a pattern.

6.  Choose *Create*.


