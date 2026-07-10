<!-- loio0993f2aa14124376a4adc7c5ba95d3f8 -->

# JMS Adapter

You configure the JMS adapter to enable asynchronous messaging using message queues.

You configure the JMS receiver and sender adapters to enable asynchronous messaging using message queues. The incoming message is stored temporarily in a queue and scheduled for processing. The processing of messages from the queue isn't serialized unless the *Exclusive* access type is selected during configuration, which ensures ordered processing.

The JMS messaging instance that is used in asynchronous messaging scenarios with the JMS, AS2, AS4, or the XI adapter has limited resources. SAP Integration Suite Standard Edition or SAP BTP Event Mesh set a limit on the queues, storage, and connections that you can use in the messaging instance. For more information, see [JMS Resource Limits and Optimizing their Usage](jms-resource-limits-and-optimizing-their-usage-4857054.md).

**Related Information**  


[Configure the JMS Sender Adapter](configure-the-jms-sender-adapter-161791b.md "The JMS (Java Message Service) sender adapter enables asynchronous decoupling of inbound and outbound processing by using message queues. The sender adapter consumes messages from a JMS queue.")

[Configure the JMS Receiver Adapter](configure-the-jms-receiver-adapter-79edc04.md "The JMS (Java Message Service) receiver adapter enables asynchronous decoupling of inbound and outbound processing by using message queues. The receiver adapter stores messages and schedules them for processing in a queue.")

[JMS Resource Limits and Optimizing their Usage](jms-resource-limits-and-optimizing-their-usage-4857054.md "The JMS messaging instance has limited resources. You can increase the capacity of these resources to a certain extend.")

