<!-- loio5d2c32fb336340bcb060d8d15997888d -->

# Use Case for JMS

Using message queues \(JMS queues\), you can implement asynchronous decoupling of messages in an improved was as compared with using the data store \(see [Use Cases for Data Store and Variables](use-cases-for-data-store-and-variables-853d4dd.md)\).

 ![](images/Guidelines_JMS_asynchronous_decoupling_b9dc499.png) 

To connect to the JMS queue, you use the JMS sender and receiver adapter like shown in the following process flow.

1.  Integration flow 1 stores the message \(received from the sender\) in the JMS queue using the JMS receiver adapter.

2.  The message broker pushes the message to integration flow 2 \(through the JMS sender adapter\).

3.  Integration flow 2 sends the message to the receiver.


If there's a transfer failure, the message is retried automatically from the message broker.

Integration flow 2 can process multiple messages in parallel. That way, the performance in high volume scenarios is improved.

> ### Tip:  
> If you like to set up a simple example scenario using JMS queues, check out [Apply the Retry Pattern with JMS Queue](apply-the-retry-pattern-with-jms-queue-da17d2d.md).

For more information on JMS sender and receiver adapter, see [JMS Adapter](https://help.sap.com/viewer/987273656c2f47d2aca4e0bfce26c594/IAT/en-US/0993f2aa14124376a4adc7c5ba95d3f8.html "You configure the JMS adapter to enable asynchronous messaging using message queues.") :arrow_upper_right:.

