<!-- loio733a57b10f504ac9b2b5aa7fda664dc5 -->

# Message Status

The message processing status indicates how a messages has been processed at runtime.



**Message Status**


<table>
<tr>
<th valign="top">

Status

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

COMPLETED

</td>
<td valign="top">

Message has been delivered to receiver successfully.

</td>
</tr>
<tr>
<td valign="top">

PROCESSING

</td>
<td valign="top">

Message is currently being processed.

</td>
</tr>
<tr>
<td valign="top">

RETRY

</td>
<td valign="top">

Status retry is set if an error occurred during message processing, and a retry was automatically started.

</td>
</tr>
<tr>
<td valign="top">

ESCALATED

</td>
<td valign="top">

During message processing an error occurred, and no retry has been triggered. For synchronous messages, an error message is sent to the sender.

</td>
</tr>
<tr>
<td valign="top">

FAILED

</td>
<td valign="top">

Message processing failed, message hasn’t been delivered to receiver, and no retries are possible. In other words: FAILED is a final status, and message processing ultimately has failed.

</td>
</tr>
<tr>
<td valign="top">

CANCELLED

</td>
<td valign="top">

Manual cancellation of entries in the JMS queue - MPL is set to status cancelled.

> ### Note:  
> In general, the last final status is accepted, but if the message processing is still ongoing, and the status CANCELLED is set, it’s overwritten by another "final status" such as COMPLETED, after completion of the message processing.



</td>
</tr>
<tr>
<td valign="top">

DISCARDED

</td>
<td valign="top">

For scheduler triggered integration flows, the MPL is shown on the worker node where the message processing started first. For all subsequent message processing starts, the message status is set to DISCARDED.

For example, assume that an integration flow is initiated by a Timer event \(scheduler\) and a worker node goes into an out of memory state. The system starts the worker node again and synchronizes the integration flow as soon as the node is active. The message is restarted in that case, and a new message ID generated. The message with the original ID goes into status DISCARDED.

</td>
</tr>
<tr>
<td valign="top">

ABANDONED

</td>
<td valign="top">

Message processing was interrupted or log wasn't updated for an uncommonly long time. The status can change in case processing is resumed.

> ### Note:  
> When the message processing is interrupted because of a re- or undeployment of an integration flow, or a controlled worker node shutdown, the MPL is immediately set to ABANDONED. This status isn’t final and the processing can be resumed if retries are configured. If there are hard worker node crashes, the status is changed to ABANDONED by an asynchronous system job, after some time of inactivity



</td>
</tr>
</table>

An aggregated message processing log \(MPL\) can have the following status values:

**Status of Aggregated Messages**


<table>
<tr>
<th valign="top">

Status

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

PROCESSING

</td>
<td valign="top">

Is set as soon as the aggregation process is started and remains as long as the aggregate is still open for further messages. Note that this status can in many situations be shown for quite some time \(even days\) – depending on the applied aggregation use case.

</td>
</tr>
<tr>
<td valign="top">

FAILED

</td>
<td valign="top">

Is set when the aggregated message \(after aggregation process has successfully been finished\) fails.

</td>
</tr>
<tr>
<td valign="top">

RETRY

</td>
<td valign="top">

Is set when the aggregated message \(after aggregation process has successfully been finished\) runs into an error and sending it’s retried.

</td>
</tr>
</table>

**Related Information**  


[Define End Message Event](define-end-message-event-4774b5f.md "An End Message event ends a message processing sequence.")

