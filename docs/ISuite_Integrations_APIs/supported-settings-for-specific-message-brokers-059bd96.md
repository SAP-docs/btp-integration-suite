<!-- loio059bd967ca5146fd9e4e12978289ab8b -->

# Supported Settings for Specific Message Brokers

Learn how to connect external message brokers using the AMQP adapter.

You can use the AMQP sender and receiver adapter to connect SAP Cloud Integration with various message brokers.

For more information on how to connect SAP Cloud Integration with SAP message brokers, see:

-   [AMQP Sender for SAP Event Mesh](amqp-sender-for-sap-event-mesh-7d8a83f.md)

-   [AMQP Receiver for SAP Event Mesh](amqp-receiver-for-sap-event-mesh-0b7cc2f.md)

-   [Supported Settings for Specific Message Brokers](supported-settings-for-specific-message-brokers-059bd96.md)

-   [AMQP Receiver for SAP Integration Suite, advanced event mesh](amqp-receiver-for-sap-integration-suite-advanced-event-mesh-5f229c0.md)


You can also connect the non-SAP message brokers as listed in the table below. The following settings are supported.

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

> ### Tip:  
> For more information, check out the following SAP Community blog: [Cloud Integration – Connecting to Messaging Systems using the AMQP Adapter](https://community.sap.com/t5/technology-blogs-by-sap/cloud-integration-connecting-to-messaging-systems-using-the-amqp-adapter/ba-p/13419906).


<table>
<tr>
<th valign="top">

 

</th>
<th valign="top">

Microsoft Azure Service Bus

</th>
<th valign="top">

Solace PubSub+

</th>
<th valign="top">

Apache Qpid Broker-J

</th>
<th valign="top">

Apache ActiveMQ 5 / Apache ActiveMQ Artemis

</th>
<th valign="top">

IBM MQ

</th>
</tr>
<tr>
<td valign="top">

Transport Protocol

</td>
<td valign="top">

TLS over TCP

</td>
<td valign="top">

TCP

TLS over TCP

</td>
<td valign="top">

TCP

TLS over TCP

WebSocket

WebSocket over TLS

</td>
<td valign="top">

TCP

TLS over TCP

</td>
<td valign="top">

TCP

TLS over TCP

</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

SASL

</td>
<td valign="top">

SASL

</td>
<td valign="top">

SASL

</td>
<td valign="top">

SASL

</td>
<td valign="top">

SASL

</td>
</tr>
<tr>
<td valign="top">

Dead letter queue handling based on *Delivery Status* 

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

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

JMSRedelivered header

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes \(version \>= 9.2\)

</td>
</tr>
<tr>
<td valign="top">

JMSXDeliveryCount header

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes \(version \>= 9.2\)

</td>
</tr>
<tr>
<td valign="top">

Exclusive queues

</td>
<td valign="top">

No

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
<td valign="top">

Yes \(version \>= 9.2\)

</td>
</tr>
<tr>
<td valign="top">

Message groups

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
<td valign="top">

Yes

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

Queues

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes \(version \>= 9.2\)

</td>
</tr>
<tr>
<td valign="top">

Topics

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

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

Topic subscriptions

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
</table>

