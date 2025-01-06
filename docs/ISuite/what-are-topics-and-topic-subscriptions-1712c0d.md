<!-- loio1712c0dc5e8f4bd6a779f3d8484628c8 -->

# What Are Topics and Topic Subscriptions?

To understand how messages flow from publishers to subscribers, you must understand the role played by topics.



<a name="loio1712c0dc5e8f4bd6a779f3d8484628c8__section_tlp_vft_gbc"/>

## Topics and Topic Subscriptions



### Topics

In an event-driven architecture \(EDA\), topics are a means of classifying the information contained in the event message. Events are published to a topic and queues can subscribe to one or more topics to attract events from publishers. In practice, topics are simply strings composed of one or more levels added to a message header.

Topics have the format `a/b/c/.../n`

where `a`, `b`, `c` and so on to `n` are identifiers in a hierarchical scheme you've devised that allows you to classify your information.

For example, if you're publishing information on sports events, you might create topics like `sports/football/scores`, `sports/football/results`, `sports/basketball/scores`, and `sports/basketball/results` to organize the content you're sending out.



### Topic Subscriptions

A topic subscription is a string used to attract published events. Topic subscriptions can contain wildcards to match with multiple topics. The `*` character can be used as a wildcard in topic subscriptions.

When `*` appears at a level within a topic subscription, it indicates a wildcard match at that level. For example, `sports/*/scores` matches the topics `sports/football/scores` and `sports/basketball/scores`.



<a name="loio1712c0dc5e8f4bd6a779f3d8484628c8__section_y4f_xft_gbc"/>

## How Event Mesh Uses Topics

If we think of topics as destinations, then Event Mesh can be thought of as the post office that directs events from the publisher to the subscribers' post boxes.

-   **Endpoints** are objects created on the broker to persist messages.

    -   **Queues** are both a destination that clients can publish messages to and an endpoint that clients can consume messages from. For more information, see [Queues](queues-99b7501.md).


-   Consumers are consuming applications that connect to Event Mesh. Any of the consumers that have been configured with topic subscriptions receive messages with matching topics.


**Related Information**  


[Topic Naming Syntax](topic-naming-syntax-62460b8.md "Rules to be followed while naming a topic.")

[Create A Topic Subscription](50-Development/create-a-topic-subscription-6fe6358.md "Understand how to create a topic subsciption from a queue.")

