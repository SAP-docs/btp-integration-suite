<!-- loio718309ae651b452ea750b3abe2297a7b -->

# Message Processing Log – Text View

The message processing log displays structured information on the processing of a message.

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

The message processing log comprises a log header and log steps. In the log header you find more general information . The log steps show specific processing events and steps as well as further information, depending on the messages logged. This could be an `EscalationEvent` for example, which will trigger an alert showing up in the message processing log.

The log header shows the following properties:

**MPL Header**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

StartTime

</td>
<td valign="top">

Start of message processing.

</td>
</tr>
<tr>
<td valign="top">

StopTime

</td>
<td valign="top">

End of message processing.

</td>
</tr>
<tr>
<td valign="top">

OverallStatus

</td>
<td valign="top">

Specifies the end-to-end status of message processing and corresponds to the *Status* attribute in the Message Monitoring editor.

For more information on statuses see **Message Status** in the **Related Information** section.

.

</td>
</tr>
<tr>
<td valign="top">

ChildCount

</td>
<td valign="top">

Indicates the serial number of the current processing step.

</td>
</tr>
<tr>
<td valign="top">

ChildrenCounter

</td>
<td valign="top">

Specifies the total number of message processing steps.

</td>
</tr>
<tr>
<td valign="top">

ContextName

</td>
<td valign="top">

Integration flow name.

</td>
</tr>
<tr>
<td valign="top">

CorrelationId

</td>
<td valign="top">

ID that identifies correlated messages. Messages can be correlated, for example, when different integration flows on the same tenant communicate with each other. A correlation ID is a base64-encoded ID that is generated in this case by the first integration flow and stored in the message header. As part of the message header, the CorrelationId is then propagated across all related integration flows \(that are in charge of processing the correlated messages\).

</td>
</tr>
<tr>
<td valign="top">

CustomHeaderProperties

</td>
<td valign="top">

Can only be added by defining a script in the script API and the properties are displayed in the message processing log header. For more information see **Define Scripts** in the **Related Information** section.

</td>
</tr>
<tr>
<td valign="top">

ExecutedMapping

</td>
<td valign="top">

Indicates the name of the message mapping artifact that was executed. Useful when you use the dynamic message mapping feature to understand which message mapping artifact was executed by the integration flow.

</td>
</tr>
<tr>
<td valign="top">

Id

</td>
<td valign="top">

Is displayed in the MPL header if the ID has been previously defined as header property. For more information see**Headers and Exchange Properties** in the **Related Information** section.

</td>
</tr>
<tr>
<td valign="top">

IntermediateError

</td>
<td valign="top">

True if an error occurred \(even temporarily\) during message processing, or message processing took more than 1 minute. The header then contains an additional property: LastError showing the error type.

</td>
</tr>
<tr>
<td valign="top">

MessageGuid

</td>
<td valign="top">

Key that identifies the message uniquely in the database.

</td>
</tr>
<tr>
<td valign="top">

MessageType

</td>
<td valign="top">

Is displayed in the MPL header if the message type has been previously defined as header property. For more information see**Headers and Exchange Properties** in the **Related Information** section.

</td>
</tr>
<tr>
<td valign="top">

Node

</td>
<td valign="top">

Host name of the node that processed the message.

</td>
</tr>
<tr>
<td valign="top">

ReceiverId

</td>
<td valign="top">

Is displayed in the MPL header if the receiver ID has been previously defined as header property. For more information see**Headers and Exchange Properties** in the **Related Information** section.

</td>
</tr>
<tr>
<td valign="top">

SenderId

</td>
<td valign="top">

Is displayed in the MPL header if the sender ID has been previously defined as header property. For more information see**Headers and Exchange Properties** in the**Related Information**section.

</td>
</tr>
<tr>
<td valign="top">

LocalSuccessor Id

</td>
<td valign="top">

Is set during aggregation and incoming message process processing logs get the aggregated MPL as a successor.

</td>
</tr>
<tr>
<td valign="top">

LocalPredecessor Id

</td>
<td valign="top">

Is set during creation of a new MPL, if the message header SAP\_MessageProcessingLogID is present or the message header SapPredecessorMessageProcessingLogId is set.

</td>
</tr>
</table>

The log steps show the following properties:

![](images/MLPSteps2_691f0e8.png)

**MPL Steps**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Branch

</td>
<td valign="top">

Indicates that the following steps have been processed in the same branch. If a **Split** or **Multicast Step** is used, the steps belonging to one sub-message are grouped together within one **Branch**.

</td>
</tr>
<tr>
<td valign="top">

ModelStepId

</td>
<td valign="top">

This ID is used to specify relation between modeled step \(in integration flow\) and MPL entry. The integration flow model steps are fragmented in the Camel runtime environment into several processing steps.

For more information see **Error Classification** in the **Related Information** section.

</td>
</tr>
<tr>
<td valign="top">

StepId

</td>
<td valign="top">

ID of the related integration flow step. It is assigned by the Camel framework.

</td>
</tr>
</table>

> ### Note:  
> -   The content of the message processing log varies according to the log level you have set.
> 
> -   The step properties displayed may vary from step to step, according to the message processing.
> -   The payload is displayed with header and content. You can also download it by clicking on the *Download* button on top right corner. This povides a zip file containing one header and one payload file.

> ### Remember:  
> -   All string values are limited to 1000 characters. Any string value longer than 1000 characters is cut off after 1000 characters.
> 
> -   The MPL property names are limited to 100 characters. Any property name longer than 100 characters is cut off after 100 characters.

You can create attachments to the message processing log by using the `Script API`.

> ### Note:  
> The amount of MPL attachments which can be written is limited to 1 GB per 24 hours. If the limit is reached, MPL attachments will no longer be stored until the amount of MPL attachments written in the last 24 hours is again below 1 GB.

**Related Information**  


[Setting Log Levels](setting-log-levels-4e6d3fc.md "The log level for the message processing log specifies the granularity of information collected by the message processing log")

[Monitor Message Processing](monitor-message-processing-314df3f.md "The message monitor provides an overview of the messages processed on a tenant and allows you to display the details for individual messages.")

[Define a Local Script Step](define-a-local-script-step-03b32eb.md "Learn how to use a script step that’s specific to an integration artifact to create custom scripts (JavaScript or Groovy Script).")

[Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md "")

[Error Classification](error-classification-3eada96.md "")

[Message Status](message-status-733a57b.md "The message processing status indicates how a messages has been processed at runtime.")

