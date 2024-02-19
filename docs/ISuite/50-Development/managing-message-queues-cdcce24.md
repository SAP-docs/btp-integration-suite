<!-- loiocdcce24f484a41c08ab46d12ab666451 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing Message Queues

You can monitor queues that are active for a tenant.

The following adapters can store messages temporarily in queues or read messages from there:

-   AS2 sender adapter temporarily stores messages during runtime processing in JMS queues.

    See:

    [Configure the AS2 Sender Adapter](configure-the-as2-sender-adapter-5d7ee17.md)

-   JMS receiver adapter writes messages to JMS queues and the JMS sender adapter reads messages from JMS queues.

    See:

    [Configure the JMS Sender Adapter](configure-the-jms-sender-adapter-161791b.md)

    [Configure the JMS Receiver Adapter](configure-the-jms-receiver-adapter-79edc04.md)

-   XI sender and receiver adapter can temporarily store messages for exactly-once \(EO\) scenarios \(if *JMS Queue* is selected as *Temporary Storage* option\).

    See:

    [Configure the XI Sender Adapter](configure-the-xi-sender-adapter-41a1a57.md)

    [Configure the XI Receiver Adapter](configure-the-xi-receiver-adapter-5d2670f.md)


To open the *Manage Message Queues* screen, perform the following steps:

1.  Go to *Monitor* \> *Integrations and APIs*.

2.  If you have activated Edge Integration Cell, select the target runtime \(*Runtime* parameter\). For more information on how to manage stores for Edge Integration Cell, see [Manage Stores for Edge Integration Cell](../manage-stores-for-edge-integration-cell-ced47da.md) 

3.  Choose the *Message Queues* tile under *Manage Stores*.




<a name="loiocdcce24f484a41c08ab46d12ab666451__section_jjd_hbl_2yb"/>

## Manage Message Queues Screen

The *Manage Message Queues* screen has a header and two main areas: an overview table on the left and a detailed content table on the right right.


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Header of the screen

In the *JMS Resources* information box below the header, you can see the status of the current JMS resource usage.

> ### Note:  
> Storage capacities of a queue have a limit.



</td>
<td valign="top">

[Checking JMS Resources](checking-jms-resources-6a9c030.md).

</td>
</tr>
<tr>
<td valign="top">

*Queues*

Active queues are displayed in the master table on the left side of the screen.

</td>
<td valign="top">

[Managing Queues](managing-queues-f116962.md).

</td>
</tr>
<tr>
<td valign="top">

*Messages*

Clicking a queue shows the messages stored in that queue on the right side of the screen.

</td>
<td valign="top">

[Managing Messages Stored in Queues](managing-messages-stored-in-queues-6733197.md).

</td>
</tr>
</table>



<a name="loiocdcce24f484a41c08ab46d12ab666451__section_b4m_fbl_2yb"/>

## General Actions

You can perform the following general actions that affect all queues:

**General Actions**


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

*Check*\(<span class="SAP-icons-V5"></span>\)

</td>
<td valign="top">

Show unused and missing queues.

The check results show the following:

-   Queues that aren't used in any deployed integration flow.
-   Queues that are referenced by integration flows but don't exist because they have been deleted by mistake.

You can delete queues that aren't needed and generate missing queues by redeploying the integration flow.

</td>
</tr>
<tr>
<td valign="top">

*Reload*\(<span class="SAP-icons-V5"></span>\)

</td>
<td valign="top">

Reload the table.

</td>
</tr>
<tr>
<td valign="top">

*Sort*\(<span class="SAP-icons-V5"></span>\)

</td>
<td valign="top">

Sort the table entries according to the displayed sorting criteria.

</td>
</tr>
</table>

**Related Information**  


[Cloud Integration – Checks in JMS Message Queue Monitor](https://blogs.sap.com/2017/10/04/cloud-integration-checks-in-jms-message-queue-monitor/)

[Cloud Integration – Configure Dead Letter Handling in JMS Adapter](https://blogs.sap.com/2017/07/17/cloud-integration-configure-dead-letter-handling-in-jms-adapter/)

[AS2 Adapter](as2-adapter-d3af635.md "")

[JMS Adapter](jms-adapter-0993f2a.md "You configure the JMS adapter to enable asynchronous messaging using message queues.")

