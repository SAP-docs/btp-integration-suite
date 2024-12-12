<!-- loio981d7eb22a90451195f6422c3fe7021f -->

# Auditing and Logging Information for Event Mesh

Find a list of the security events that are logged by Event Mesh.


<table>
<tr>
<th valign="top">

Event Grouping

</th>
<th valign="top">

What Events are Logged

</th>
<th valign="top">

How to Identify Related Log Events

</th>
</tr>
<tr>
<td valign="top">

Activate capability

</td>
<td valign="top">

Activate or deactivate Event Mesh 

</td>
<td valign="top">

`emis-tenant-subscribed`: tracks activation of theEvent Mesh capability

`emis-tenant-unsubscribed`: tracks deactivation of Event Mesh capability

</td>
</tr>
<tr>
<td valign="top">

Upgrade SAP Integration Suite service plan

</td>
<td valign="top">

Change the service plan from a lower plan to higher plan

</td>
<td valign="top">

`emis-tenant-updated`: tracks the SAP Integration Suite plan upgrade.

</td>
</tr>
<tr>
<td valign="top">

Managing Event Mesh broker

</td>
<td valign="top">

Creating, updating, or deleting the message broker

</td>
<td valign="top">

`emis-messaging-domain-created`: tracks creation of a message broker

`emis-messaging-domain-updated`: tracks update of a message broker

`emis-messaging-domain-deleted`: tracks deletion of a message broker

</td>
</tr>
<tr>
<td valign="top">

Managing service instance for the message client

</td>
<td valign="top">

Creating, updating, or deleting service instances

</td>
<td valign="top">

`emis-service-instance-created`: tracks creation of a service instance

`emis-service-instance-updated`: tracks update of a service instance

`emis-service-instance-deleted`: tracks deletion of a service instance

`emis-service-binding-created`: tracks a binding creation with the service instance

`emis-service-binding-deleted`: tracks a binding deletion with the service instance

</td>
</tr>
<tr>
<td valign="top">

Managing queues and topic subscription

</td>
<td valign="top">

Creating, updating, or deleting queues and topic subscriptions

</td>
<td valign="top">

`emis-queue-upserted`: tracks creation or update of a queue

`emis-queue-deleted`: tracks deletion of a queue

`emis-topic-subscription-upserted`: tracks creation/update of a topic subscription for a queue

`emis-topic-subscription-deleted`: tracks deletion of a topic subscription for a queue

</td>
</tr>
</table>

