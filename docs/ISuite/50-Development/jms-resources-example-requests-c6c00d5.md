<!-- loioc6c00d53b64d4f6dbee059338fd966f0 -->

# JMS Resources Example Requests

Get information about JMS message queues.




<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
<th valign="top">

Purpose

</th>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

`​/JmsBrokers('Broker1')?$expand=QueueStates` 

</td>
<td valign="top">

Get the queue status of each message queue \(0 OK, 1 warning, 2 critical\).

</td>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

`​/JmsBrokers('Broker1')?$expand=InactiveQueues` 

</td>
<td valign="top">

Get stopped queues.

</td>
</tr>
</table>

You can use this API in an integration flow to set up notifications for critical resource situations. For more information, see the following SAP Community blog:

[Cloud Integration – Automated Notification for Critical or Exhausted JMS Resources](https://blogs.sap.com/2018/06/04/cloud-integration-automated-notification-for-critical-or-exhausted-jms-resources/)

