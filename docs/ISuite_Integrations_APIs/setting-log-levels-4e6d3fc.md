<!-- loio4e6d3fc3f34544f6ac5289268b653ad1 -->

# Setting Log Levels

The log level for the message processing log specifies the granularity of information collected by the message processing log

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

You can set the log level for an integration flow scenario in the *Manage Integration Content* page of the *Web-based Monitor*.

Select your integration flow in the *Manage Integration Content* and set the log level for this integration flow in the *Log Configuration* section.

You can choose the following log levels:

****


<table>
<tr>
<th valign="top">

Log Level

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`None`

</td>
<td valign="top">

No data is recorded during message processing and no data is shown in data monitoring.

> ### Note:  
> In case data archiving is available on your tenant and configured for your integration flow, no data is archived for this specific integration flow.



</td>
</tr>
<tr>
<td valign="top">

`Info`

</td>
<td valign="top">

Basic information is recorded during message processing. The header is always displayed.

If there are failed messages, the message processing log retains and displays additional detailed information about the last 50 message steps.

</td>
</tr>
<tr>
<td valign="top">

`Error`

</td>
<td valign="top">

The message processing log records basic information for failed message executions only. The message processing log retains and displays detailed information about the last 50 message steps. Use this log level, if you've no interest in recording completed messages.

No message processing log attachments are recorded.

> ### Note:  
> In case data archiving is available on your tenant and configured for your integration flow, no data is archived for this specific integration flow.

Specifics for log level `Error`: If you've defined a retry-scenario in your integration flow and set log level `Error`, a final successful retry isn't recorded. In particular, the overall Message Processing Log Status stays in status `Retry` or `Failed` although the message is finally successfully delivered.

</td>
</tr>
<tr>
<td valign="top">

`Debug`

</td>
<td valign="top">

> ### Caution:  
> As the log level `Debug` is a high resource consuming feature, we recommend setting log level`Debug` only in a development or test environment!

The message processing log records detailed information for all steps during message processing. While all steps \(with headers and additional information\) are accessible in the graphical UI, only the last 100 are shown in the text view of the message processing log. The log level debug expires after a certain period of time. After expiry, the log level switches back to the log level set before.

The expiry time is fixed and set to 24 hours.

</td>
</tr>
<tr>
<td valign="top">

`Trace`

</td>
<td valign="top">

The message processing log records detailed information for all steps during message processing and additionally tracks the message content. The trace function expires after a certain period of time \(default value: 10 minutes\). After expiry, the log level switches back to the log level set before. The recorded message content is also only retained for a certain time \(default value: 1 hour\)

Specifics for log level `Trace`:

-   If the downloaded trace data, such as header value size and exchange properties exceed 10000 characters, they're truncated.



</td>
</tr>
</table>

> ### Note:  
> If you update an integration flow, that is, deploy an integration flow without deleting the predecessor version, the log level configuration is kept stable. If you undeploy an integration flow and then deploy a newer version, it's treated as a new integration flow, which is logged with log level `Info`.
> 
> Changes to the log level don't affect messages already in process and only apply to newly created messages after the time of modification.

> ### Note:  
> In order to conserve resources, you can use a Groovy script \(in a *Script* integration flow step\) that retrieves additional information associated with particular log levels. You can model the scenario in such a way that the information is only determined when it is really needed.
> 
> For instance, using the following script, you can limit the inclusion of the payload as an attachment by specifying that the attachment should only be saved if the log level is set to a specific value. For more information about scripts, see [Add Information to the Message Processing Log](add-information-to-the-message-processing-log-e8e9283.md).
> 
> > ### Sample Code:  
> > ```
> > import com.sap.it.api.msglog.MessageLogFactory;
> > import com.sap.gateway.ip.core.customdev.util.Message;
> > import java.util.HashMap;
> >         def Message processData(Message message){
> >             def logLevel = message.getProperty("SAP_MPL_LogLevel_Overall");
> >             def logLevelInternal = message.getProperty("SAP_MPL_LogLevel_Internal");
> >             def logLevelExternal = message.getProperty("SAP_MPL_LogLevel_External");
> > 
> >             def messageLog = messageLogFactory.getMessageLog(message);
> >             messageLog.addCustomHeaderProperty("Log Level", logLevel);
> >             messageLog.addCustomHeaderProperty("Internal Log Level", logLevelInternal);
> >             messageLog.addCustomHeaderProperty("External Log Level", logLevelExternal);
> > 
> >         if(logLevel.equals("DEBUG") || logLevel.equals("TRACE")) {
> >             def body = message.getBody();
> >             messageLog.addAttachmentAsString("Payload", body, "text/plain");
> >             messageLog.addAttachmentAsString("Debugging information", "data", "text/plain");
> >         }
> >         return message;
> > }
> > ```
> 
> The log level is represented in three different ways:
> 
> -   *Internal* log level \(from property `SAP_MPL_LogLevel_Internal`\) refers to the setting that is applicable to the monitoring data accessible through the SAP Integration Suite user interface and the public OData API.
> 
> -   *External* log level \(from property `SAP_MPL_LogLevel_External`\) refers to the log level selected for sending logging information to an external logging system. This is only relevant if you have activated the corresponding feature.
> 
> -   *Overall* log level \(from property `SAP_MPL_LogLevel_Overall`\) represents the highest log level between *Internal* and *External* log levels, following the order of `None`, `Error`, `Info`, `Debug`, `Trace`. If you are using both logging options, the *Overall* log level allows you to consider only one value for comparison. However, if you are not using external logging, then considering the *Internal* log level alone is sufficient.
> 
>     The *Overall* log level serves as a convenience level if you only want to focus on one value that is achieved by at least one of the two log levels.
> 
> 
> Examples:
> 
> -   Internal = ERROR, External = INFO =\> Overall = INFO
> 
> -   Internal = DEBUG, External = INFO =\> Overall = DEBUG
> -   Internal = INFO, External = NONE =\> Overall = INFO

**Related Information**  


[Message Processing Log – Text View](message-processing-log-text-view-718309a.md "The message processing log displays structured information on the processing of a message.")

[Monitor Message Processing](monitor-message-processing-314df3f.md "The message monitor provides an overview of the messages processed on a tenant and allows you to display the details for individual messages.")

[Message Processing Log - Adapter Tracing](message-processing-log-adapter-tracing-a9db4ea.md "The adapter tracing is part of the regular tracing feature and the payloads are recorded if you have set the log level to Trace.")

