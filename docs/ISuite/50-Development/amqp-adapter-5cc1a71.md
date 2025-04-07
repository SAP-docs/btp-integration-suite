<!-- loio5cc1a71231cb4cbfbfedb0cdc63e1488 -->

# AMQP Adapter

In many integration scenarios, messages or events have to be exchanged between applications or systems via message brokers. With the Advanced Message Queuing Protocol \(AMQP\) adapter, SAP Cloud Integration can be used as a provider or a consumer of such messages or events. SAP Cloud Integration can connect to external message brokers using the AMQP protocol, consume messages or events using the AMQP sender adapter, or store messages or events in the message broker using the AMQP receiver adapter.

> ### Note:  
> Note that customer-specific headers with prefix JMS aren’t allowed. These headers aren’t forwarded by the message brokers.

> ### Note:  
> Queues, topics, and messages can only be created and monitored by using tools provided by the message broker provider. Those monitors aren’t integrated into SAP Cloud Integration. In SAP Cloud Integration, the integration flows using the AMQP adapter are monitored and the messages are sent to or consumed from the message broker.

**Related Information**  


[Configure the AMQP Sender Adapter](configure-the-amqp-sender-adapter-99ce674.md "You use the Advanced Message Queuing Protocol (AMQP) sender adapter to consume messages in SAP Integration Suite from queues in an external message broker.")

[Configure the AMQP Receiver Adapter](configure-the-amqp-receiver-adapter-d5660c1.md "You use the Advanced Message Queuing Protocol (AMQP) receiver adapter to send messages from SAP Integration Suite to queues or topics in an external message broker.")

