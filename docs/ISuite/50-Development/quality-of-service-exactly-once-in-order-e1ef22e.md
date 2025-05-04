<!-- loioe1ef22e3f5d84cbea7dc30400352e942 -->

# Quality of Service Exactly Once In Order



You want to ensure that messages aren't only delivered and processed at the receiver exactly once, but also in the sequence in which they were sent from the sender system, by that preserving the order of message processing.

For ensuring Exactly Once delivery, you can apply the same measures as described in [Quality of Service Exactly Once](quality-of-service-exactly-once-f96cf27.md).

In the following, we assume that the receiver is idempotent and hence only focus on preserving the order of message processing. To do so, you can asynchronously decouple your message processing using the JMS adapter with exclusive access type. This setting guarantees that messages are processed in the exact order that they're received by allowing only one consumer access to the queue at any time.

See [Configure the JMS Sender Adapter](configure-the-jms-sender-adapter-161791b.md) and [Configure the JMS Receiver Adapter](configure-the-jms-receiver-adapter-79edc04.md).

Additionally, you can use SAP Integration Suite, advanced event mesh for implementing Exactly Once In Order delivery. Here, you can either use exclusive queues or partitioned queues. For connecting to SAP Integration Suite, advanced event mesh you can leverage the Advanced Event Mesh adapter.

See [Configure the Advanced Event Mesh Sender Adapter](configure-the-advanced-event-mesh-sender-adapter-abd2efc.md) and [Configure the Advanced Event Mesh Receiver Adapter](configure-the-advanced-event-mesh-receiver-adapter-881f656.md).



<a name="loioe1ef22e3f5d84cbea7dc30400352e942__section_jft_kfb_y2c"/>

## Scenarios

The scenarios provided in this section show how to guarantee Exactly Once In Order delivery between systems integrated using SAP Integration Suite. Whether Exactly Once In Order is guaranteed end-to-end depends on the particular use case and the message protocol used. The prerequisite for end-to-end Exactly Once In Order delivery is that the sender ensures that a message is only sent when the predecessor message has been acknowledged by a technical success response, such as an HTTP return code 200 or 202.

The following scenarios exist:

-   Generic use case using an exclusive JMS queue \(see [Generic Use Case](generic-use-case-70c7774.md)\)
-   Scenario with XI sender and SAP RM receiver using an exclusive JMS queue \(see [Sender with XI Protocol and Receiver with SAP RM Protocol](sender-with-xi-protocol-and-receiver-with-sap-rm-protocol-090abf3.md)\)
-   Scenario with SAP RM sender and XI receiver using an exclusive JMS queue \(see [Sender with SAP RM Protocol and Receiver with XI Protocol](sender-with-sap-rm-protocol-and-receiver-with-xi-protocol-5f35b5c.md)\)
-   Scenario with SFTP sender adapter using an exclusive JMS queue \(see [SFTP Sender Scenario](sftp-sender-scenario-3d7fd37.md)\)
-   Scenario using either an exclusive or a partitioned queue on SAP Integration Suite, advance event mesh \(see [Decoupling Using SAP Integration Suite, Advanced Event Mesh](decoupling-using-sap-integration-suite-advanced-event-mesh-df7b472.md)\)

