<!-- loio6bc21cb2644b49f7a79be8ff406696a4 -->

# Data Store, Variables, and JMS Queues: When to Use Which Option?

Cloud Integration supports various integration patterns. Certain integration patterns require a storage location to read and write the content of a message during the execution of a scenario. When the message content is needed for later processing steps or if the message content is evaluated in a later phase, storage steps are required. Storing data is also required in asynchronous message patterns. In this section, we discuss how to use the following storage options \(in the context of different use cases\):

-   Global data store

-   Global variable

-   Java Messaging Service \(JMS\) message queue


For an overview of the available storage options, see [Using Data Storage Features When Designing Integration Flows](using-data-storage-features-when-designing-integration-flows-a836b4e.md).

In this section, you find guidelines for the usage of the data store/variables compared with the usage of JMS queues.

These are the main characteristics of the data store and the JMS queues \(for more technical information like the storage size, for example, see [Using Data Storage Features When Designing Integration Flows](using-data-storage-features-when-designing-integration-flows-a836b4e.md)\).


<table>
<tr>
<th valign="top">

Option

</th>
<th valign="top">

Usage

</th>
</tr>
<tr>
<td valign="top">

Data store/variable

</td>
<td valign="top">

The data store is used to persist messages on the database of your SAP Integration Suite tenant. You can use the *Data Store Operations* integration flow steps \(*Write*, *Get*, *Select*, and *Delete*\) to do operations on the data store.

You can use the Data Store sender adapter to allow SAP Integration Suite to consume messages from a data store. This feature helps you to enable asynchronous decoupling of inbound and outbound processing by using the data store as temporary storage. When configuring the Data Store sender adapter, you can specify parameters such as the poll interval that determines the time to wait before consuming messages from the data store. You can also define the retry behavior.

This feature allows you to set up scenarios with reliable messaging using asynchronous decoupling.

</td>
</tr>
<tr>
<td valign="top">

JMS queue

</td>
<td valign="top">

You can use the JMS receiver adapter to store messages in a JMS queue. One important key characteristic of the Java Message Service \(JMS\) feature is the support of high-speed messaging with high throughput. This is why it offers the optimal solution for reliable messaging using asynchronous decoupling. JMS is a Java-based standard application programming interface \(API\) for sending and receiving messages. It enables efficient asynchronous communication based on a JMS message broker between different components. The JMS message broker is a separate runtime component that ensures that messages in JMS queues in the JMS message broker are treated separately. The JMS adapter is used to store messages in the JMS queue and to consume messages from the JMS queue in the JMS message broker.

The processing sequence used by the JMS adapter is first-in, first-out \(FIFO\). Regarding message processing order, the JMS adapter offers two main access types that influence message handling: *Non-Exclusive* and *Exclusive*. The non-exclusive access type allows for parallel processing, where messages may not be processed in a guaranteed order due to concurrent consumption and retry handling. Conversely, the exlusive access type ensures messages are handled sequentially as received.

</td>
</tr>
</table>

The following questions help you to decide which option to use.


<table>
<tr>
<th valign="top">

Question

</th>
<th valign="top">

Data Store

</th>
<th valign="top">

JMS Queue

</th>
</tr>
<tr>
<td valign="top">

Can data be consumed during integration flow processing?

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Can data initiate integration flow execution?

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

What is the frequency of consumption?

</td>
<td valign="top">

Whenever a message is initiated by a client's call, a timer \(scheduler\), or automatically consumed by the integration flow through the Data Store sender adapter

</td>
<td valign="top">

Broker pushes message to integration flow automatically \(if a listening thread is available\)

</td>
</tr>
<tr>
<td valign="top">

Is parallel consumption of different data possible?

</td>
<td valign="top">

Yes for parallel incoming messages

No for scheduler-initiated integration flows

</td>
<td valign="top">

Yes \(for non-exclusive queues\)

</td>
</tr>
<tr>
<td valign="top">

Can the same data be consumed multiple times?

</td>
<td valign="top">

Yes, the data is available until expired or explicitly removed.

</td>
<td valign="top">

No, once processed successfully, the data is gone.

</td>
</tr>
<tr>
<td valign="top">

Suitable for high volume message processing?

</td>
<td valign="top">

Not recommended

</td>
<td valign="top">

Yes

</td>
</tr>
</table>

**Related Information**  


[Use Cases for Data Store and Variables](use-cases-for-data-store-and-variables-853d4dd.md "")

[Data Store Sender Adapter](data-store-sender-adapter-4f5ef3f.md "This adapter enables Cloud Integration to consume messages from a data store. This feature helps you to enable asynchronous decoupling of inbound and outbound processing by using the data store as temporary storage.")

[Use Case for JMS](use-case-for-jms-5d2c32f.md "")

