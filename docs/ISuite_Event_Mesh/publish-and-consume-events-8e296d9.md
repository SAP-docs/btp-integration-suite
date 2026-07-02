<!-- loio8e296d9e3e714505b9aa494343fa7cae -->

# Publish and Consume Events

Event Mesh capability supports the following messaging protocol:



<a name="loio8e296d9e3e714505b9aa494343fa7cae__section_v15_hn3_4bc"/>

## Advanced Message Queuing Protocol \(AMQP\) 1.0 over WebSocket

The Advanced Message Queuing Protocol \(AMQP\) is an open standard for passing business messages between applications or organizations. It connects systems, feeds business processes with the information they need, and reliably transmits onward the instructions that achieve their goals. Event Mesh supports the use of AMQP 1.0 over websocket for messaging between applications.

Refer to the [Specifications for AMQP 1.0 over Websocket](https://docs.oasis-open.org/amqp-bindmap/amqp-wsb/v1.0/amqp-wsb-v1.0.html) to publish and consume messages.

Also, refer to the [protocal implementation for AMQP 1.0](https://www.npmjs.com/package/@sap/xb-msg-amqp-v100) that SAP provides.



<a name="loio8e296d9e3e714505b9aa494343fa7cae__section_dl2_2jf_cfc"/>

## Message Queuing Telemetry Transport \(MQTT\) 3.1.1 over WebSocket

It’s a lightweight messaging protocol designed specifically for constrained devices, low bandwidth, high latency, or unreliable devices. We recommend that you use MQTT 3.1.1 over WebSocket for messaging to a service from applications not running on the Cloud, for example, SAP S/4HANA. For more information, see [Specification for MQTT 3.1.1 over WebSocket](https://help.sap.com/docs/link-disclaimer?site=http%3A%2F%2Fdocs.oasis-open.org%2Fmqtt%2Fmqtt%2Fv3.1.1%2Fcsprd02%2Fmqtt-v3.1.1-csprd02.html).

> ### Note:  
> Quality of Service \(QoS\) is a feature of MQTT, where the protocol handles retransmission and guarantees that the message is delivered regardless of network reliability. MQTT 3.1.1 over WebSocket supports only QoS 0, and QoS 1. The supported QoS levels are:
> 
> -   At most once \(0\) - It guarantees best effort with delivery. A message isn't acknowledged by the receiver, stored or redelivered by the sender.
> -   At least once \(1\) - It guarantees that a message is delivered at least once to the receiver. The message can also be delivered more than once.



<a name="loio8e296d9e3e714505b9aa494343fa7cae__section_rwx_fyr_ldc"/>

## Hypertext Transfer Protocol \(HTTP\)

Hypertext Transfer Protocol \(HTTP\) is a fundamental protocol of the Internet, enabling the transfer of data between a client and a server. Event Mesh supports the use of HTTP for messaging between applications.

Use a REST client tool to leverage the supported REST APIs to publish and consume messages.

-   To know about the available REST APIs, see:[SAP Business Accelerator Hub](https://api.sap.com/api/RestGatewayAPI/overview).

-   The REST APIs are protected with an OAuth bearer token. You must first authenticate your applications to be able to publish and consume messages. See [Authenticate Your REST API Requests](authenticate-your-rest-api-requests-027e47a.md) to know more.




### Quality of Service For Consuming Messages

The quality of service defines how a system guarantees the message delivery from a sender to a receiver. The APIs for consuming messages require a mandatory header **`x-qos`** that supports the following types:

**Quality of Service**


<table>
<tr>
<th valign="top">

Quality of Service

</th>
<th valign="top">

Allowed Value Via APIs

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

At Most Once

</td>
<td valign="top">

0

</td>
<td valign="top">

Event Mesh attempts only once to deliver the messages. Event Mesh doesn't wait for acknowledgement from your application and deletes the messages from the queue after attempting to deliver, even if the messages are not successfully delivered.

</td>
</tr>
<tr>
<td valign="top">

At Least Once

</td>
<td valign="top">

1

</td>
<td valign="top">

Event Mesh attempts to deliver the messages to your to your application at least once, that is, waits for an acknowledgement from your application. If your application responds with a 2XX HTTP response code, the messages are deleted from the queue. If your application responds with other codes, Event Mesh keeps trying to redeliver the message until your application responds with a 2XX response code.

</td>
</tr>
</table>

