<!-- loiobf9d648cab6442a8894edce3b897c857 -->

# Create Topic Subscriptions

Topic subscriptions allow a queue to receive messages published to specific topics, enabling flexible message routing over AMQP 1.0 or MQTT 3.1.1 over WebSocket, or via HTTP .



## Prerequisites

-   The parent queue for the topic subscription must already exist before the subscription can be created.
-   The topic name or pattern must comply with the Topic Naming Syntax for the messaging protocol you're using, regardless of the creation method.



## Overview

A topic subscription binds a queue to one or more topics, so that messages published to those topics are delivered to the queue. When a message is sent via AMQP 1.0 or MQTT 3.1.1 over WebSocket, or via HTTP , it can be published to a queue directly or to a topic. Topic subscriptions provide a way for queues to selectively receive messages based on topic names or patterns.

Topics are organized in a logical, folder-like hierarchy, and each topic appears as a string composed of multiple segments separated by a defined delimiter. A topic subscription is defined by the topic name or pattern that it matches, along with its association to a parent queue.



## Topic naming syntax

Topic names or patterns used in a subscription must follow the correct Topic Naming Syntax defined by the messaging protocol you're using. The syntax specifies allowed characters, segment separators, and any wildcard conventions supported by the protocol.

For details on syntax rules for each protocol, see [Topic Naming Syntax](https://help.sap.com/docs/integration-suite/isuite-event-mesh/topic-naming-syntax?locale=en-US&state=PRODUCTION&version=CLOUD).



## Methods for creating topic subscriptions

-   Manual creation through the SAP Integration Suite UI: Navigate to *Configure* \> *Event Mesh* \> *Queues*, select the target queue, navigate to the *Subscriptions* tab, and use the *Create* option to define the subscription name or pattern. This method gives you direct, guided access to each configurable field.

