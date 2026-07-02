<!-- loio0ef235f956704642b5b73ac5ee4ec153 -->

# What Is Messaging?

Understand how a message about an event is communicated.

Messaging lets computer systems share information without requiring direct connections or awareness of each other's location. Messaging is analogous to postal and shipping services. With messaging, your applications deliver information to a messaging system that routes it to whatever other applications it needs to get to.

At its most basic, messaging involves the following participants:

-   Publisher: The entity that sends or publishes a message \(also called a producer\).

-   Message: The information the publisher wants to send. Messages often contain event data, but can also carry queries, commands, and other information.

-   Messaging system: The infrastructure that transmits the message.

-   Subscriber: The ultimate receiver of the message \(also called a consumer\).


In an event-driven architecture \(EDA\), a message typically has a destination that separates the publisher from the subscriber. In SAP Integration Suite, a destination is generally a queue that is managed by the event brokers.

