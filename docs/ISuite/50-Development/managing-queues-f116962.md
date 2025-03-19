<!-- loiof1169625222f432aad390e7d3336950c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing Queues

Monitor and manage the active queues.



<a name="loiof1169625222f432aad390e7d3336950c__section_jcw_sxd_wjb"/>

## Manage Message Queues

All message queues that are active for the tenant are displayed in a table. For each queue, the following information is displayed:

**Message Queue Overview**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name* 

</td>
<td valign="top">

Name of JMS queue.

</td>
</tr>
<tr>
<td valign="top">

*Access Type* 

</td>
<td valign="top">

Type of access to the JMS queue which can be exclusive or non-exclusive.

</td>
</tr>
<tr>
<td valign="top">

*Entries* 

</td>
<td valign="top">

Number of messages stored in queue.

</td>
</tr>
</table>

To sort and filter the content of the table, choose *Table Settings* \(:gear:\). On the subsequent screen, you can define how the table entries are to be sorted \(by specifying an attribute and whether the entries are to be sorted for that attribute in ascending or descending order\). You can also filter the table entries for certain attributes.

The search allows you to filter specific queues by providing parts of their name.



<a name="loiof1169625222f432aad390e7d3336950c__section_ufq_vjm_2yb"/>

## Actions to Perform on Single Queue

For a dedicated queue, choose <span class="SAP-icons-V5"></span> Actions to perform the following actions:

**Actions**


<table>
<tr>
<th valign="top">

Action

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Retry* \(only for non-exclusive queues\)

</td>
<td valign="top">

Triggers a retry of all messages in the selected queue.

> ### Note:  
> You can't retry stopped queues.



</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

Displays the data volume \(in MB\) already used compared to the maximum data volume available \(per sub queue\).

There are the following sub queues:

-   *Processing Queue* 

    Processes the messages \(as, for example, are stored by a JMS receiver and consumed by a JMS sender adapter\).

-   *Error Queue* \(only for non-exclusive queues\)

    Temporarily stores messages in an error state until the next configured retry. No messages are consumed from this queue. Instead of this, the messages are taken back to the processing queue when the configured retry interval has been reached.

-   *Chunking Queue* 

    Messages with a size larger than 5 MB are split into one parent message of 5-MB size and multiple chunks. The parent message is stored in the processing queue while the multiple chunks are stored in the chunking queue \(see also [JMS Resource Limits and Optimizing their Usage](jms-resource-limits-and-optimizing-their-usage-4857054.md)\).


This screen provides the following functions:

-   *Configure Size*

    Allows you to configure the maximum size of the selected queue.

    For more information and examples how to configure queue sizes, check out the SAP Community blog [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/).

-   *Stop* \(only available for started queues\)

    Use this function to take out a queue from processing. That way, you can avoid that the queue runs at full capacity.

-   *Start* \(only available for stopped queues\)

    Use this function to start a queue manually.




</td>
</tr>
<tr>
<td valign="top">

*Configure Size*

</td>
<td valign="top">

Change the maximum size of the sub queues.

For more information and examples how to configure queue sizes, check out the SAP Community blog [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/).

</td>
</tr>
<tr>
<td valign="top">

*Where-Used*

</td>
<td valign="top">

Displays the integration flows in which a queue is used, and specifies whether the integration flows write to or consume a queue, or both. If you select the link to the integration flow, it opens in read-only mode and you can check the scenario that is using the queue.

During the operation of your scenarios, you may find that messages are piling up in one queue, and you want to get more details so that you can analyze why the messages aren't being processed.

</td>
</tr>
<tr>
<td valign="top">

*Move* \(only for non-exclusive queues\)

</td>
<td valign="top">

Use to manually trigger the process of moving all messages from the source queue to another target queue.

> ### Caution:  
> If new messages are written to the source queue during the moving process, these new messages will also be moved to the selected target queue – even if they weren't part of the queue when the move process was triggered manually. This function can lead to an endless loop in which the messages are constantly moved to the target queue.
> 
> Once triggered, the move process is only stopped if no new messages are written to the queue for a certain amount of time.



</td>
</tr>
<tr>
<td valign="top">

*Delete*

</td>
<td valign="top">

Deletes the selected queue and all messages stored in the queue.

> ### Note:  
> You can't delete any queues that are \(still\) in use by one or more integration flows. Undeploy the integration flow first and then continue with deleting the queue.
> 
> You can't delete stopped queues.



</td>
</tr>
</table>

