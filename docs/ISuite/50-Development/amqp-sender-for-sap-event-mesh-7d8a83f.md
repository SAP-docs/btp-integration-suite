<!-- loio7d8a83f8501c4b23b967f060cd1d7eac -->

# AMQP Sender for SAP Event Mesh

Enables SAP Integration Suite to consume messages from queues in SAP Event Mesh.



> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> Queues, topics, and messages can only be monitored by using tools provided by the message broker provider. Those monitors are not integrated into SAP Integration Suite . Using SAP Integration Suite , you can only monitor the integration flows using the AMQP adapter and the messages that are sent to or consumed from the message broker.

> ### Note:  
> To be able to connect to queues, you have to create queues and/or topics in the message broker. This needs to be done in the message broker, with the configuration tools provided by the message broker. In some messaging systems, you need to configure a *Lock Duration* to make sure that the message is not consumed more than once. This timeout must be longer than the expected processing time of the message, otherwise this would lead to duplicate messages.

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



To connect Cloud Integration to SAP Event Mesh, make sure to specify the following parameters in the described way:

When creating the channel \(see [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md)\), select adapter type *AMQP* \> *WebSocket*.



The following values are displayed in the *General* tab after a channel has been established. If you want to change the configurations, you need to configure a new channel.

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

*Name/Adapter Type* 

</td>
<td valign="top">

*AMQP* 

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol* 

</td>
<td valign="top">

The protocol that the message broker supports:

*WebSocket*

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol* 

</td>
<td valign="top">

*AMQP 1.0* 

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows:

**Connection**


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

*Host* 

</td>
<td valign="top">

Specify the hostname of the message broker.

</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Specify the port of the message broker.

Enter `443`.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

The type of proxy that you’re using to connect to the target system.

Select *Internet* if you’re connecting directly to the message broker.

Select *On-Premise* if you’re connecting to an on-premise message broker.

For more information, see [Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md).

</td>
</tr>
<tr>
<td valign="top">

*Path* 

</td>
<td valign="top">

Specify the access path of the message broker.

Enter `/protocols/amqp10ws`.

</td>
</tr>
<tr>
<td valign="top">

*Connect with TLS* 

</td>
<td valign="top">

Select this option.

</td>
</tr>
<tr>
<td valign="top">

*Location ID* \(only if *On-Premise* is selected for *Proxy Type*\)

</td>
<td valign="top">

To connect to an SAP Cloud Connector instance associated with your account, enter the location ID that you defined for this instance in the destination configuration on the cloud side.

</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Select *OAuth2 Client Credentials*.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

</td>
<td valign="top">

Specify the name of the *OAuth2 Client Credentials* artifact.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

**Processing**


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

*Queue Name* 

</td>
<td valign="top">

Specify the name of the queue or topic subscription to consume from.

> ### Note:  
> Use the following expression to define the queue name:
> 
> `queue:<queue name>`

> ### Note:  
> Topics are not supported in the sender adapter, only queues and topic subscriptions.
> 
> Technically, the AMQP sender adapter allows you to consume from queues only. The adapter doesn’t allow you to directly subscribe to a topic. If you like to work with topic subscriptions, subscribe a queue to a topic and consume from this queue.



</td>
</tr>
<tr>
<td valign="top">

*Number of Current Processes* 

</td>
<td valign="top">

Specify the number of processes used for parallel message processing. Note, that these processes are started from each worker node.

> ### Note:  
> The maximum number of parallel processes cannot exceed 99. The default is set to 1.



</td>
</tr>
<tr>
<td valign="top">

*Max. Number of Prefechted Messages*

</td>
<td valign="top">

Enter the max. number of messages that may be prefechted by one worker. The allowed value range is 1 to 100.

The prefetch value is the number of messages that the sender adapter fetches in advance from the broker, and then gradually processes. The prefetch reduces the communication overhead and ensures that when a message has been processed, another is already there and is ready for processing.

If the integration flows that are triggered by the AMQP sender adapter run for longer than a few seconds, it makes sense to set a lower prefetch value. In particular, if the integration flow runs for more than a minute, you should consider setting the value to 1. You can expect then a performance deterioration in the two-digit millisecond range, per message. On the other hand, load balancing between several nodes works better even with short backlogs.

If you need to process a large number of messages with the integration flow, and the processing of the individual message only runs for a few milliseconds, it can be useful to increase the prefetch value.

> ### Note:  
> If you increase the value, this can lead to lock timeouts and the load balancing between the nodes deteriorates. In return, you can expect performance gains in the three-digit microsecond range, per message. For example, with a prefetch value of 100, 10000 messages process approximately a second or two faster.



</td>
</tr>
<tr>
<td valign="top">

*Consume Expired Messages*

</td>
<td valign="top">

Select if the adapter is to consume already expired messages.

By default, this option is deactivated.

</td>
</tr>
<tr>
<td valign="top">

*Max. Number of Retries* 

</td>
<td valign="top">

Define the number of retries to be executed before a different delivery status is sent to the message broker.

> ### Note:  
> If this parameter is left empty, endless retries are executed. Ensure to specify a value to prevent this behavior.
> 
> If this parameter is set to \(`0`\), any message that is marked as a retried message is directly returning the outcome configured in *Delivery Status After Max. Retries* to the message broker and does not even start processing the message. Be aware of the fact that any delivery attempt by the message broker, even a failed one \(for example, due to network issues\), increases the delivery counter of the message sent by the message broker.
> 
> If the value is set to a number bigger than `0`, the AMQP adapter returns the outcome configured in *Delivery Status After Max. Retries* to the message broker if the delivery count of the message exceeds the configured value. Otherwise, it processes the message and returns a released outcome in case of an error and an accepted outcome in case of a successful message processing.
> 
> The consequences of the provided outcome depend on the message broker and the queue configuration on the message broker. An accepted outcome usually removes the message from the queue. A released outcome usually triggers a redelivery. A rejected outcome may trigger a redelivery or move the message to a dead letter queue \(maybe only if the message was rejected for a configured number of times\). The same applies to a modified outcome with the undeliverable flag set, which also might transit the message on the message broker to some undeliverable state.
> 
> If the message broker is not configured properly, this behavior can lead to unwanted side effects. For example, the messaging system constantly re-sends the message, no other messages are being processed, and no additional message processing logs are written. As a consequence, this can result in an unplanned high load of your tenant and message broker.



</td>
</tr>
<tr>
<td valign="top">

*Delivery Status After Max. Retries* 

</td>
<td valign="top">

Define one delivery status that is to be sent to the message broker after the maximum number of retries. Choose between the following options:

Select *REJECTED*.

Make sure to configure the dead letter queue and the maximum redeliveries in the message broker as well.

Don't select *MODIFIED\_FAILED\_UNDELIVERABLE*.

> ### Note:  
> See this [general information on AMQP](http://docs.oasis-open.org/amqp/core/v1.0/amqp-core-complete-v1.0.pdf) on delivery statuses and their meaning.
> 
> You can use the following headers to configure a delay in retry processing: `JMSRedelivered` and `JMSXDeliveryCount`. For more information, see the SAP Community blog [Cloud Integration – Connecting to Messaging Systems using the AMQP Adapter](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-connecting-to-messaging-systems-using-the-amqp-adapter/ba-p/13419906).
> 
> This blog also contains an overview of the recommended settings for different message brokers.



</td>
</tr>
</table>



<a name="loio7d8a83f8501c4b23b967f060cd1d7eac__section_qgb_ccj_wsb"/>

## Further Constraints

The following constraints and limitations apply when using the AMQP adapter to connect Cloud Integration to SAP Event Mesh:

-   You can configure retry by setting the header `JMSRedelivered`.

-   You can't use header `JMSXDeliveryCount`.


See also: [Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md)

Furthermore, consider the following restrictions:

-   The maximum number of connections supported per service instance is: 50.

-   The maximum number of connections combined for all service instances and subscription \(per subaccount\) is: 1000.


As a consequence from this restriction, it's recommended that you use 1 service instance per queue.

For more information, see:

-   For more information and an example scenario using this option, see the following SAP Community blog: [https://blogs.sap.com/2019/11/20/cloud-integration-connecting-to-external-messaging-systems-using-the-amqp-adapter/](https://blogs.sap.com/2019/11/20/cloud-integration-connecting-to-external-messaging-systems-using-the-amqp-adapter/).

-   For more information on the constraints of SAP Event Mesh, see [Scope and Limitations](https://help.sap.com/viewer/bf82e6b26456494cbdd197057c09979f/Cloud/en-US/ac83090b07684f8e908df40d024f8fe5.html) \(for SAP Event Mesh\).


