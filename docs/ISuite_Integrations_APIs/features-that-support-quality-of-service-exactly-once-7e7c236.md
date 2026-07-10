<!-- loio7e7c2364a6734329986031671a1bd94e -->

# Features that Support Quality of Service Exactly Once

Various capabilities help to ensure guaranteed delivery.


<table>
<tr>
<th valign="top">

Capability

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Unique identifier \(for example, a message ID\)

</td>
<td valign="top">

A unique identifier is a prerequisite to be able to identify duplicates. The ID can change during message processing. However, this change has to be done in a deterministic, reproducible way. That means: An ID of the sender system must always result in the same ID for the receiver system even when resending the message \(see the description of ID mapping\).

</td>
</tr>
<tr>
<td valign="top">

ID mapping

</td>
<td valign="top">

If sender and receiver support different message ID formats, an ID mapper is required that translates IDs in a repeatable manner \(see the description of unique identifier\). If the sender sends the same message again, the ID mapper must guarantee that the same source ID is mapped to the same target ID. An ID mapper is required in particular in a split scenario where one sender ID needs to be mapped to multiple IDs on the receiver side.

Assume that the receiver can't use the same message ID provided by the sender system to carry out the duplicate check.

There are the following 2 use cases:

-   Sender and receiver require different ID formats, for example, ID format supported by AS2 adapter versus XI adapter.

    The system needs to generate a unique ID in the format dictated by the receiver system. The ID is based on the ID of the sender system. Furthermore, the generated ID must be repeatable. This means: Resending a message with the same sender ID must result in the same generated receiver ID.

    For an example with the AS2 sender adapter, see: [ID Mapping \(with AS2 Sender Adapter\)](id-mapping-with-as2-sender-adapter-fe142b3.md)

-   Multicast or splitter with open branches.

    Cloud Integration transforms 1 message \(received from the sender\) into multiple messages \(sent to one or multiple receivers\). If there are multiple receivers, an ID mapping isn't mandatory in any case. The reason is that the sender message ID is unique within the context of each receiver. If there's only 1 receiver, there's no guarantee anymore that the sender message ID is unique in the context of the receiver system. Therefore, Cloud Integration needs to generate different unique IDs.

    For an example with the splitter pattern, see: [ID Mapping \(with Splitter\)](id-mapping-with-splitter-441e51d.md)


If the receiver adapter isn't offering the option to map an ID, use the *ID Mapping* integration flow step to map a source message ID to a target message ID. The ID mapping generates a unique ID for the combination of a source message ID and a context. When processing the ID mapping step with a dedicated combination of parameter settings the first time, Cloud Integration stores the generated ID temporarily in the tenant database. When executed with the same combination again, the ID mapping provides the same previously generated ID.

> ### Note:  
> To avoid database overflows, the ID mapping stores the generated ID with a limited lifetime. You can customize the corresponding parameter*Expiration Period* when designing the *ID Mapping* step. To be more specific: The expiration period, that is: the number of days after which the system deletes the stored ID mapping. The default setting is 30 days.
> 
> Make sure that the expiration period is longer than the expected maximal time period during which retries can happen.
> 
> See: [Define ID Mapping](define-id-mapping-2367101.md)



</td>
</tr>
<tr>
<td valign="top">

Acknowledgment:

</td>
<td valign="top">

When exchanging messages between systems, an acknowledgment verifies that the message was received successfully at the target system. On transport layer, an acknowledgment can be an HTTP status code, for example. In asynchronous messages, an acknowledgment can be a separate message \(for example, MDN in AS2 adapter\). The system handles messages where a positive acknowledgment is missing as failed messages that need to be resent.

</td>
</tr>
<tr>
<td valign="top">

Sender with retry

</td>
<td valign="top">

If message processing fails, the sender should be able to resend the message. In order to survive application crashes, such a retry is to be based on a persistent message storage.

</td>
</tr>
<tr>
<td valign="top">

Idempotent receiver

</td>
<td valign="top">

An idempotent receiver can safely retrieve and digest the same message multiple times without causing duplicate executions of the received changes.

There are the following use cases:

-   The sender supports message retry, and the receiver is idempotent. This means that the receiver is able to detect and ignore duplicate messages.

    Therefore, the integration flow doesn’t require any additional implementation steps to support EO.

    See: [Sender and Receiver with SAP RM Protocol](sender-and-receiver-with-sap-rm-protocol-9f3e2b6.md)

-   The sender supports message retry, and the receiver is idempotent. However, the message protocol **doesn't** contain a unique ID.

    Therefore, the integration developer needs to design the scenario in such a way that Cloud Integration derives a unique ID from the payload.

    See: [Sender and Receiver with SOAP Protocol](sender-and-receiver-with-soap-protocol-cd4c6e0.md)

-   The sender doesn't retry messages, but the receiver is idempotent.

    Therefore, the middleware \(Cloud Integration\) needs to carry out the retry of the message delivery if there's an error.

    See: [Decoupling via JMS Queue](decoupling-via-jms-queue-ecbde19.md)


> ### Note:  
> If the receiver system isn't able to identify and discard duplicate messages, the middleware needs to handle duplicate messages.
> 
> Usually, the duplicate check is done as close as possible to the application that uses the data. Ideally, the receiver handles duplicates. That means, the duplicate handling and the operation writing or updating data is done within the same transaction in the receiver system. This design ensures that if an application error occurs, the system rolls back persistence of the message ID in an idempotent repository. Therefore, a retry of the same message isn't considered as duplicate.
> 
> Let's assume that the receiver system isn't idempotent. That means: The receiver isn't able to identify and discard duplicate messages. In this case, the middleware \(Cloud Integration\) needs to handle duplicate messages. Although usually Exactly Once can be ensured, there's a marginal residual risk of error situations if this isn't the case. For instance, if the message has been successfully delivered to the receiver, however, the technical acknowledgment got lost in between due to network issues. In this case, the middleware treats the call as not successful, and a retry of the message isn't seen as duplicate. Finally, this behavior results in an At Least Once quality of service.
> 
> There are the following options to implement the duplicate check within the middleware \(Cloud Integration\):
> 
> -   The sender adapter can handle duplicates.
> 
>     See: [XI Sender Adapter Handles Duplicates](xi-sender-adapter-handles-duplicates-7c9a0fd.md)
> 
> -   The sender adapter isn't able to remove duplicates. In this case, duplicate handling needs to be implemented within the integration flow. This is currently not yet supported by Cloud Integration.



</td>
</tr>
</table>

