<!-- loiof9223443fb8b43abb602332d9be94cce -->

# Specific Data Assets

Different kinds of data are stored in the SAP Cloud Integration infrastructure during the lifecycle of an integration project.

The following table lists the different kinds and attributes such like storage location and retention time, for example.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

**Data Assets**


<table>
<tr>
<th valign="top">

Data



</th>
<th valign="top">

Description



</th>
<th valign="top">

Logical `Storage` 



</th>
<th valign="top">

Classification



</th>
<th valign="top">

Retention Time



</th>
<th valign="top">

Backup Available



</th>
</tr>
<tr>
<td valign="top">

Message processing log



</td>
<td valign="top">

Structured information on the processing of a message



</td>
<td valign="top">



</td>
<td valign="top">

Log data



</td>
<td valign="top">

30 days



</td>
<td valign="top">

14 days



</td>
</tr>
<tr>
<td valign="top">

Message processing log attachments



</td>
<td valign="top">

Data attached to a message processing log during runtime



</td>
<td valign="top">

Message store



</td>
<td valign="top">

Log data

Business data



</td>
<td valign="top">

30 days



</td>
<td valign="top">

14 days



</td>
</tr>
<tr>
<td valign="top">

Audit log



</td>
<td valign="top">

Information on events such as data read accesses or system configuration changes



</td>
<td valign="top">



</td>
<td valign="top">

Log data



</td>
<td valign="top">

30 days



</td>
<td valign="top">

14 days



</td>
</tr>
<tr>
<td valign="top">

System log



</td>
<td valign="top">

Information about errors that occurred during HTTP inbound processing



</td>
<td valign="top">



</td>
<td valign="top">

Log data



</td>
<td valign="top">

7 days



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Integration flow tracing data



</td>
<td valign="top">

Information on the message flow \(including the message payload\) and on errors that occurred during message processing



</td>
<td valign="top">

Trace store



</td>
<td valign="top">

Log data

Business data



</td>
<td valign="top">

60 minutes



</td>
<td valign="top">

14 days



</td>
</tr>
<tr>
<td valign="top">

Integration content \(design time\)



</td>
<td valign="top">

Integration flow models and value mappings created or edited by an integration developer



</td>
<td valign="top">

Workspace



</td>
<td valign="top">

Configuration data



</td>
<td valign="top">

Unlimited



</td>
<td valign="top">

14 days



</td>
</tr>
<tr>
<td valign="top">

Integration content \(runtime\)



</td>
<td valign="top">

Camel XML representation of integration flows and other design time entities \(as deployed on a runtime node\)



</td>
<td valign="top">



</td>
<td valign="top">

Configuration data



</td>
<td valign="top">

Unlimited



</td>
<td valign="top">

14 days



</td>
</tr>
<tr>
<td valign="top">

Data stored by Data Store operations step



</td>
<td valign="top">

Message content stored in dedicated steps in an integration flow \(contains information such as message GUID, message processing log GUID, tenant ID, time stamp, and payload\).

Is used for further message processing in subsequent steps in an integration flow.



</td>
<td valign="top">

Data store



</td>
<td valign="top">

Business data



</td>
<td valign="top">

Can be defined by integration developer \(default value: 30 days\)



</td>
<td valign="top">

14 days



</td>
</tr>
<tr>
<td valign="top">

Data stored by Persist step



</td>
<td valign="top">

Message content stored in dedicated steps in an integration flow \(contains information such as message GUID, message processing log GUID, tenant ID, time stamp, and payload\)

Can be accessed and analyzed after message processing.



</td>
<td valign="top">

Message store



</td>
<td valign="top">

Business data



</td>
<td valign="top">

90 days



</td>
<td valign="top">

14 days



</td>
</tr>
<tr>
<td valign="top">

Message content stored by JMS adapter



</td>
<td valign="top">

Message content stored in JMS message queues



</td>
<td valign="top">

JMS queue



</td>
<td valign="top">

Business data



</td>
<td valign="top">

Can be defined by integration developer \(default value: 90 days\)



</td>
<td valign="top">

Not supported



</td>
</tr>
<tr>
<td valign="top">

Lock entries



</td>
<td valign="top">

Lock entries that are created \(in the in-progress repository\) to avoid the same message being processed several times in parallel \(for example, by different runtime nodes\)



</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">



</td>
<td valign="top">

14 days



</td>
</tr>
</table>

Limited retention times make sure that data is stored in the system only for a limited time period.

**Related Information**  






[Define Data Store Operations](../Development/define-data-store-operations-79f63a4.md "You can use the data store to temporarily store messages.")



[Managing Security Material](../Operations/managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

[Message Locks](../Operations/message-locks-bce9ae0.md "This section allows you to display and manage lock entries that are created (in the in-progress repository) to avoid the same message being processed several times in parallel (for example, by different runtime nodes).")

