<!-- loio2b9acb2790f64310adcb7db741af4c1f -->

# Quality of Service

The quality of service defines how a system guarantees the message delivery from a sender to a receiver.

There are the following types:


<table>
<tr>
<th valign="top">

Quality of Service

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Best Effort \(BE\)

</td>
<td valign="top">

Doesn't provide any guarantee if or how often the message is delivered.

</td>
</tr>
<tr>
<td valign="top">

At Least Once \(ALO\)

</td>
<td valign="top">

Guarantees that a message is delivered at least one time; duplicate delivery of the same message is possible.

</td>
</tr>
<tr>
<td valign="top">

At Most Once \(AMO\)

</td>
<td valign="top">

Guarantees that the same message isn't sent multiple times; however, in certain cases the message isn't delivered at all.

</td>
</tr>
<tr>
<td valign="top">

Exactly Once \(EO\)

</td>
<td valign="top">

Guarantees that a message is delivered only once. Therefore, this quality of service is a combination of ALO and AMO.

See: [Quality of Service Exactly Once](quality-of-service-exactly-once-f96cf27.md)

</td>
</tr>
<tr>
<td valign="top">

Exactly Once In Order \(EOIO\)

</td>
<td valign="top">

Guarantees that messages are delivered only once and in the same sequence in which they were sent from the sender system.

See: [Quality of Service Exactly Once In Order](quality-of-service-exactly-once-in-order-e1ef22e.md)

</td>
</tr>
<tr>
<td valign="top">

Handled by Integration Flow

</td>
<td valign="top">

Quality of service is managed within the integration flow itself, and the adapter doesn't add any quality of service handling \(such as retry storage or duplicate checks\).

</td>
</tr>
</table>

When designing integration flows, consider that any component in the communication path can fail. Communication lines may be interrupted, and applications \(including Cloud Integration\) may crash while processing messages. If your business scenario requires a specific quality of service for message delivery, ensure that potential failure scenarios are accounted for in your flow design.

> ### Note:  
> Some adapters provide a quality-of-service setting. This setting applies only to processing within the adapter and does not extend to the entire integration flow.

The integration flow developer is responsible for the quality of service realized by the end-to-end message flow. This includes, but is not limited to:

-   Handling non-delivery to the BTP platform by implementing retry mechanisms in the sender application to address intermittent processing failures in the Cloud Integration runtime.
-   Designing for resilience during platform updates, such as rolling software upgrades in the BTP platform, which may terminate running integration flows or cause errors in dependent network components such as Cloud Connector.
-   Preventing side effects from duplicate messages at the receiver application by implementing idempotency on the same.

For example, an XI sender adapter configured with the quality of service "Exactly Once" stores the message and retries delivery until it succeeds. The XI protocol also handles duplicate messages. However, this setting does not protect against message loss that occurs before the message reaches the adapter.

Quality of service for the end-to-end flow can be complex and depends on the protocols used and the capabilities of the participating sender and receiver systems. While Cloud Integration provides building blocks to design resilient integration flows, it remains the responsibility of the integration flow designer to ensure that the flow meets the required business quality-of-service requirements.

The [Integration Flow Design Guidelines](integration-flow-design-guidelines-6803389.md) provide some recommendations on how to achieve this.

References:

-   [Retry](https://help.sap.com/docs/btp/developing-resilient-apps-on-sap-btp/retry)
-   [Resilience Recommendations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/resilience-recommendations?version=Cloud)
-   [Apply the Retry Pattern in the Sender Applications](apply-the-retry-pattern-in-the-sender-applications-0e27ac9.md)
-   [Resilient Protocols](https://help.sap.com/docs/btp/developing-resilient-apps-on-sap-btp/message-driven#loio79f49eb49cdd4d0bb8de44cbc9a6a7ec)

