<!-- loiof96cf276c37d424f9a5b3e63778cf0ae -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Quality of Service Exactly Once

You want to ensure that a message is delivered and processed at the receiver exactly once. This requirement is a combination of the following 2 enterprise integration patterns:

-   Guaranteed Delivery

    This pattern ensures that a message is delivered even if the messaging system temporarily fails to deliver the message to a receiver.

    Therefore, *Guaranteed Delivery* can cause redeliveries and, because of this fact, even a message to be delivered multiple times.

-   Idempotent Receiver

    This pattern deals with duplicate message handling. It guarantees that even if a component receives a message multiple times, it processes it only once.




<a name="loiof96cf276c37d424f9a5b3e63778cf0ae__section_bvc_lmn_krb"/>

## Scenarios

The scenarios provided in this section show how to guarantee end-to-end *Exactly Once* delivery between systems integrated via SAP Integration Suite .

The way how to achieve the quality of service Exactly Once depends on the actual scenario. The following scenarios show how to ensure guaranteed delivery:

The scenarios are grouped along the requirements met by the following components: sender, middleware \(SAP Integration Suite \), and receiver.


<table>
<tr>
<th valign="top">

Sender handles retry

</th>
<th valign="top">

SAP Integration Suite handles retry

</th>
<th valign="top">

SAP Integration Suite idempotent

</th>
<th valign="top">

SAP Integration Suite - ID mapping required

</th>
<th valign="top">

Receiver idempotent

</th>
<th valign="top">

Side effects and constraints

</th>
<th valign="top">

Scenario

</th>
</tr>
<tr>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

The sender supports message retry, and the receiver is idempotent. This means that the receiver is able to detect and ignore duplicate messages.

For a scenario using SAP RM receiver, see: [Sender and Receiver with SAP RM Protocol](sender-and-receiver-with-sap-rm-protocol-9f3e2b6.md)

For a scenario using IDoc receiver adapter, see: [IDoc Receiver Handles Duplicates](idoc-receiver-handles-duplicates-8f8feea.md)

For a scenario using XI receiver adapter, see: [XI Receiver Handles Duplicates](xi-receiver-handles-duplicates-fcf026b.md)

</td>
</tr>
<tr>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

:heavy_check_mark:

\(Message protocol doesn't contain unique ID\)

</td>
<td valign="top">

The sender supports message retry, and the receiver is idempotent. However, the message protocol **doesn't** contain a unique ID.

Therefore, the integration developer needs to design the scenario in such a way that SAP Integration Suite derives a unique ID from the payload.

For a scenario using SOAP receiver, see: [Sender and Receiver with SOAP Protocol](sender-and-receiver-with-soap-protocol-cd4c6e0.md)

For a scenario using IDoc receiver adapter, see: [IDoc Receiver Handles Duplicates \(based on unique ID in payload\)](idoc-receiver-handles-duplicates-based-on-unique-id-in-payload-bb441a9.md)

For a scenario using XI receiver adapter, see: [XI Receiver Handles Duplicates \(based on unique ID in payload\)](xi-receiver-handles-duplicates-based-on-unique-id-in-payload-3add2bf.md)

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

The sender doesn't retry messages, but the receiver is idempotent.

Therefore, the middleware \(SAP Integration Suite \) needs to carry out the retry of the message delivery if there's an error.

For a scenario using JMS queues, see: [Decoupling via JMS Queue](decoupling-via-jms-queue-ecbde19.md)

For a scenario using IDoc receiver adapter with decoupling via JMS queues, see: [IDoc Receiver Handles Duplicates \(with decoupling via JMS Queue\)](idoc-receiver-handles-duplicates-with-decoupling-via-jms-queue-776b640.md)

For a scenario using XI receiver adapter with decoupling via JMS queues, see: [XI Receiver Handles Duplicates \(with decoupling via JMS Queue\)](xi-receiver-handles-duplicates-with-decoupling-via-jms-queue-bd19abf.md)

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

The sender doesn't retry messages, but the receiver is idempotent.

Therefore, the middleware \(Cloud Integration\) needs to carry out the retry of the message delivery if there's an error.

For a scenario using a data store, see: [Decoupling via Data Store](decoupling-via-data-store-d115669.md)

</td>
</tr>
<tr>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

:heavy_check_mark:

\(Sender and receiver require different ID formats \(for example, ID format supported by AS2 adapter versus XI adapter\)\)

</td>
<td valign="top">

Sender and receiver require different ID formats, for example, ID format supported by AS2 adapter versus XI adapter.

The system needs to generate a unique ID in the format dictated by the receiver system. The ID is based on the ID of the sender system. Furthermore, the generated ID must be repeatable. This means: Resending a message with the same sender ID must result in the same generated receiver ID.

For an example with the AS2 sender adapter, see: [ID Mapping \(with AS2 Sender Adapter\)](id-mapping-with-as2-sender-adapter-fe142b3.md)

</td>
</tr>
<tr>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

Multicast or splitter with open branches.

Cloud Integration transforms 1 message \(received from the sender\) into multiple messages \(sent to one or multiple receivers\). If there are multiple receivers, an ID mapping isn't mandatory in any case. The reason is that the sender message ID is unique within the context of each receiver. If there's only 1 receiver, there's no guarantee anymore that the sender message ID is unique in the context of the receiver system. Therefore, SAP Integration Suite needs to generate different unique IDs.

For an example with the splitter pattern, see: [ID Mapping \(with Splitter\)](id-mapping-with-splitter-441e51d.md)

For an example with the multicast pattern. see: [ID Mapping \(with Multicast\)](id-mapping-with-multicast-55f2d4a.md)

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

:heavy_check_mark:

\(Sender adapter\)

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

The sender adapter can handle duplicates.

For example, the XI adapter provides the following features:

-   It has an in-built retry mechanism.

-   It also stores the incoming XI message ID in an idempotent repository. If another message with the same XI message ID arrives at the XI endpoint, the message is discarded.


See: [XI Sender Adapter Handles Duplicates](xi-sender-adapter-handles-duplicates-7c9a0fd.md)

</td>
</tr>
<tr>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

\(Idempotent process call\)

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

The sender adapter isn't able to remove duplicates. However, the integration flow contains an idempotent process call that detects and removes the duplicates.

See: [Idempotent Process Call Handles Duplicates](idempotent-process-call-handles-duplicates-da18f73.md)

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

:heavy_check_mark:

\(Idempotent process call\)

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

\(Side effects lead to non-deterministic behavior\)

</td>
<td valign="top">

A JMS queue is used to handle the retry of the message delivery if an error occurs. A data store operation within the integration flow requires transactional processing to ensure data consistency. However, SAP Integration Suite doesn't support distributed transactions including both a JMS and a database transaction. Therefore, an idempotent process call is needed to ensure data consistency.

See: [Idempotent Process Call Handles Duplicates \(with JMS and Data Store Operations\)](idempotent-process-call-handles-duplicates-with-jms-and-data-store-operations-727724f.md)

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

\(Idempotent process call\)

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

\(Side effects lead to non-deterministic behavior\)

</td>
<td valign="top">

The sender expects a response. If the same request is called again, the message must not be sent to the receiver system. Instead of this, an alternative response is to be created.

See: [Idempotent Process Call Handles Duplicates \(With Alternative Response\)](idempotent-process-call-handles-duplicates-with-alternative-response-a870621.md)

</td>
</tr>
<tr>
<td valign="top">

:heavy_check_mark:

</td>
<td valign="top">

 

</td>
<td valign="top">

:heavy_check_mark:

\(Idempotent process call\)

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

This scenario combines the aggregator pattern with the quality of service Exactly Once.

See: [Aggregator](aggregator-86f97fd.md)

</td>
</tr>
</table>



<a name="loiof96cf276c37d424f9a5b3e63778cf0ae__InteractionOfIntegrationFlows"/>

## Involved Integration Flows

To simulate the communication of sender and receiver systems through SAP Integration Suite for the different scenarios, the integration package comes with multiple integration flows. To learn more about how these integration flows interact with each other during the processing of a scenario, see [Interaction of the Involved Integration Flows](interaction-of-the-involved-integration-flows-44be68d.md).

**Related Information**  


[Quality of Service](quality-of-service-2b9acb2.md "The quality of service defines how a system guarantees the message delivery from a sender to a receiver.")

[Features that Support Quality of Service Exactly Once](features-that-support-quality-of-service-exactly-once-7e7c236.md "")

[Interaction of the Involved Integration Flows](interaction-of-the-involved-integration-flows-44be68d.md "")

[Sender Handles Retry](sender-handles-retry-48b120a.md "The sender supports message retry.")

[SAP Integration Suite Handles Retry](sap-integration-suite-handles-retry-035a1c9.md "")

