<!-- loio161791b8cb98485ba00d81efa4197a49 -->

# Configure the JMS Sender Adapter

The JMS \(Java Message Service\) sender adapter enables asynchronous decoupling of inbound and outbound processing by using message queues. The sender adapter consumes messages from a JMS queue.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> Note that this adapter works with a message broker provided by SAP \(based on the SAP Event Mesh capability\). It does not support connectivity to any other, customer-provided message brokers. The usage of this adapter is supported by all SAP Integration Suite editions, except the basic edition. See SAP Note [2903776](https://me.sap.com/notes/2903776).

To understand the concept of asynchronous decoupling, assume that a sender sends a message to SAP Integration Suite \(inbound processing\). If there's an error in outbound processing \(for example, a receiver can't be reached temporarily\), the middleware \(SAP Integration Suite\) retries message processing independently. There's no need that the sender triggers a reprocessing of the message as soon as the error situation has been solved. The sender relies on the middleware to do that. To support this scenario, the message received from the sender is stored in a queue \(using the JMS receiver adapter\). Outbound processing is modeled in an integration flow that initially consumes the message from the queue \(using the JMS sender adapter\). The outbound integration flow retries the message from the queue as long as the error situation lasts.

When using the JMS adapter, you can choose how messages are processed based on your integration needs.

-   With the *Non-Exclusive* access type, messages can be processed in parallel across multiple worker nodes, which is suitable for scenarios where message order is not essential. The JMS adapter will not serialize messages, which means that there is no guarantee of the order in which the messages are consumed by SAP Cloud Integration. For additional information, also check out the description of parameter *Number of Concurrent Processes*.
-   For cases where preserving the order of message processing is crucial, you can select the *Exclusive* access type. This setting guarantees that messages are processed in the exact order they are received by allowing only one consumer access to the queue at any time.

    > ### Note:  
    > When using exclusive access, note that it processes messages sequentially which may limit scalability and reduce throughput compared to non-exclusive access. Additionally, if a message encounters an error, it will block all subsequent messages in the queue.


The following figure shows the involved components.

![The tenant opens a connection with the Message Broker. Meanwhile, the message received from the tenant is stored in a queue. The queue is using the JMS receiver adapter. The outbound integration flow retries the message from the queue if the error situation lasts.](images/JMS_Sender_Adapter_6348733.png)

Assuming that you have designed an integration flow with a JMS sender adapter. On deployment of the integration flow, the JMS queue \(as specified in the adapter\) is created and the tenant opens a consumer connection to the message broker. The message broker pushes messages through this connection.

> ### Note:  
> When you define the queue name with the *Queue Name* parameter of the JMS receiver adapter, the queue is created automatically on deployment of the integration flow that uses the adapter. This is **not** the case when you define the queue name dynamically based on a header or a property.
> 
> Therefore, it is recommended to first deploy all integration flows with the JMS sender adapters that are related to your scenario. After this step, all required queues are in place when the JMS receiver adapter comes into play and dynamically determines the related queue names.

> ### Note:  
> Certain constraints apply with regard to the number and capacity of queues involved, as well as for the headers and exchange properties defined in the integration flow before the message is saved to the queue, see [JMS Resource Limits and Optimizing their Usage](jms-resource-limits-and-optimizing-their-usage-4857054.md).

Property `SAP_IntegrationFlowID` contains the ID of the integration flow that sent the message to the JMS queue.

Once you've created a sender channel and selected the JMS sender adapter, you can configure the following attributes, see [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

Select the *General* tab and provide values in the fields as follows.

**General**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Enter the name of the channel.

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows.

**Connection**


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Parameters

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

*Processing Details* 

</td>
<td valign="top">

*Queue Name*

</td>
<td valign="top">

Enter the name of the message queue \(aA-zZ, 0–9, \_\) without white spaces.

A maximum length of 80 characters is allowed.

</td>
</tr>
<tr>
<td valign="top">

*Access Type*

</td>
<td valign="top">

Select between the two types of access to the JMS queue:

-   *Non-Exclusive*: Allows multiple consumers/workers to process messages from the queue in parallel. This is suitable for scenarios where message order is not critical and parallel processing is beneficial.
-   *Exclusive*: Ensures that only one consumer/worker has access to the queue at a time. This is useful for scenarios requiring messages to be processed in the order they were received.

> ### Note:  
> The access type in the sender adapter must match the access type in the receiver adapter for the same queue.

> ### Remember:  
> The access type cannot be changed after the queue is created. If you want to change the access type, undeploy the IFlows, delete the queue, and then redeploy with the new access type.



</td>
</tr>
<tr>
<td valign="top">

*Number of Concurrent Processes* \(only if *Non-Exclusive* is selected for *Access Type*\)

</td>
<td valign="top">

Enter the number of concurrent processes for each worker node. The recommended value depends on the number of worker nodes, the number of queues on the tenant, and the incoming load. Make sure to enter a value that is as small as possible \(1-5\) because JMS resources are limited, see: [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/) and [Cloud Integration – Configure Asynchronous Messaging with Retry Using JMS Adapter](https://blogs.sap.com/2017/06/19/cloud-integration-configure-asynchronous-messaging-with-retry-using-jms-adapter/).

> ### Note:  
> Default number of concurrent processes is `1`. Increase this number only if parallel processing is required for your scenario. However, be aware of the fact that, when processing large messages, a high number of concurrent processes can lead to out of memory problems.



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

*Retry Handling* 

</td>
<td valign="top">

*Retry Interval* 

</td>
<td valign="top">

Enter a value for the amount of time to wait before retrying message delivery.

> ### Note:  
> In the JMS sender channel, you can configure the time intervals between retries, but you cannot configure that processing will end after a specific number of retries. For non-exclusive queues, if required, you can configure this in an exception subprocess that calls a local process for retry handling using the header `SAPJMSRetries` set by the JMS sender adapter.
> 
> For more information about explicit retry configuration, see the SAP Community Blog [Cloud Integration – Configure Asynchronous Messaging with Retry Using JMS Adapter](https://blogs.sap.com/2017/06/19/cloud-integration-configure-asynchronous-messaging-with-retry-using-jms-adapter/)



</td>
</tr>
<tr>
<td valign="top">

*Exponential Backoff* 

</td>
<td valign="top">

Check the box to double the retry interval after each unsuccessful retry.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Retry Interval \(in m\)\**

\(only configurable when *Exponential Backoff* is selected\)

</td>
<td valign="top">

Enter a value for the maximum amount of time to wait before retrying message delivery. The minimum value is 10 minutes. The default value is set to 60 minutes.

</td>
</tr>
<tr>
<td valign="top">

*Dead-Letter Queue* \(only if *Non-Exclusive* is selected for *Access Type*\)

</td>
<td valign="top">

If selected, the message is taken out of processing and marked as *Blocked* in the queue in the following situation: Message processing has been stopped due to an out-of-memory error in the worker node. Later, the message has been retried twice by the JMS sender adapter \(and each retry has again lead to an out-of-memory error in the worker node\).

Processing large messages in scenarios with the JMS sender adapter can sometimes cause a worker node failure. Node failure can happen in such a scenario if the JMS adapter repeatedly tries to process a failed \(large\) message. To avoid such a situation, select this option \(switched on by default\).

In such cases, a lock entry is created, which you can view and release in the Monitoring application in the *Message Locks* tile under *Managing Locks*.

When you release the lock, the system starts retrying the message again.

For more information, check out the following blog: [Cloud Integration – Configure Dead Letter Handling in JMS Adapter](https://blogs.sap.com/2017/07/17/cloud-integration-configure-dead-letter-handling-in-jms-adapter/).

> ### Note:  
> For high-load scenarios, or if you're sure that only small messages are processed in your scenario, deselect the checkbox to improve the performance. Note that there's a risk of an outage, for example, if you run out of memory.



</td>
</tr>
</table>

**Related Information**  


[Message Locks](message-locks-bce9ae0.md "This section allows you to display and manage lock entries that are created (in the in-progress repository) to avoid the same message being processed several times in parallel (for example, by different runtime nodes).")

[JMS Resource Limits and Optimizing their Usage](jms-resource-limits-and-optimizing-their-usage-4857054.md "The JMS messaging instance has limited resources. You can increase the capacity of these resources to a certain extend.")

[Cloud Integration - Configure Dead Letter Handling in JMS Adapter](https://blogs.sap.com/2017/07/17/cloud-integration-configure-dead-letter-handling-in-jms-adapter/)

[Apply the Retry Pattern with JMS Queue](apply-the-retry-pattern-with-jms-queue-da17d2d.md "")

[Monitoring Scenarios that Include Message Queues](monitoring-scenarios-that-include-message-queues-35c4caf.md "Learn more about how to monitor scenarios that include message queues and possible error situations.")

