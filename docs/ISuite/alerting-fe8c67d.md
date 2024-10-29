<!-- loiofe8c67d4c5c64bf2a007ee2efa0842b9 -->

# Alerting

Edge Integration Cell includes alert rules for selected components. You can use these in addition to default alert rules provided by Edge Lifecycle Management. For more information, see [Alerting with SAP Alert Notification Service for SAP BTP](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/48c168304ed84622ba90d9a88d3698d4.html).

**Message Service \(Solace Broker\) Alerts**

These alert rules are related to the most important events that affect the Solace Broker.


<table>
<tr>
<th valign="top">

Alert Subject

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Solace StatefulSet not ready

</td>
<td valign="top">

Solace StatefulSet is not ready

Primary Broker might not be able to startup or Backup Broker is down \(in HA setup\)

</td>
</tr>
<tr>
<td valign="top">

Solace not available

</td>
<td valign="top">

Solace is not available

There is no Active Broker pod available, messaging clients will not be able to connect

</td>
</tr>
<tr>
<td valign="top">

Solace not operational

</td>
<td valign="top">

Operational status is not Active

The Broker is started but is not operational, messaging clients will not be able to connect

</td>
</tr>
<tr>
<td valign="top">

Solace Config-Sync not operational

</td>
<td valign="top">

Config-Sync status is not operational

Broker is started but [Config-Sync](https://docs.solace.com/Features/Config-Sync/Config-Sync-Overview.htm) is not operational, messaging clients will not be able to connect

</td>
</tr>
<tr>
<td valign="top">

Solace Connections usage is above 80%

</td>
<td valign="top">

Connections usage is quite high

Connection limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
<tr>
<td valign="top">

Solace Connections usage is above 95%

</td>
<td valign="top">

Connections usage is very high

Connection limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
<tr>
<td valign="top">

Solace Queues and Topic Endpoints usage is above 80%

</td>
<td valign="top">

Queues and Topic Endpoints usage is quite high

Endpoints limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
<tr>
<td valign="top">

Solace Queues and Topic Endpoints usage is above 95%

</td>
<td valign="top">

Queues and Topic Endpoints usage is very high

Endpoints limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
<tr>
<td valign="top">

Solace Message Storage usage is above 80%

</td>
<td valign="top">

Message Storage usage is quite high

Message Storage \(Message Spool\) limit is defined by Solace Tier

</td>
</tr>
<tr>
<td valign="top">

Solace Message Storage usage is above 95%

</td>
<td valign="top">

Message Storage usage is very high

Message Storage \(Message Spool\) limit is defined by Solace Tier

</td>
</tr>
<tr>
<td valign="top">

Solace Producers usage is above 80%

</td>
<td valign="top">

Producers \(Ingress Flows\) usage is quite high

Producers limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
<tr>
<td valign="top">

Solace Producers usage is above 95%

</td>
<td valign="top">

Producers \(Ingress Flows\) usage is very high

Producers limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
<tr>
<td valign="top">

Solace Consumers usage is above 80%

</td>
<td valign="top">

Consumers \(Egress Flows\) usage is quite high

Consumers limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
<tr>
<td valign="top">

Solace Consumers usage is above 95%

</td>
<td valign="top">

Consumers \(Egress Flows\) usage is very high

Consumers limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
<tr>
<td valign="top">

Solace Transacted Sessions usage is above 80%

</td>
<td valign="top">

Transacted Sessions usage is quite high

Transacted Sessions limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
<tr>
<td valign="top">

Solace Transacted Sessions usage is above 95%

</td>
<td valign="top">

Transacted Sessions usage is very high

Transacted Sessions limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
<tr>
<td valign="top">

Solace Transactions usage is above 80%

</td>
<td valign="top">

Transactions usage is quite high

Transactions limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
<tr>
<td valign="top">

Solace Transactions usage is above 95%

</td>
<td valign="top">

Transactions usage is very high

Transactions limit is defined by Solace Tier or Solops Runtime Parameter

</td>
</tr>
</table>



<a name="loiofe8c67d4c5c64bf2a007ee2efa0842b9__section_zxh_4jb_wbc"/>

## Worker Alerts

These alert rules are related to important events that affect the Worker.


<table>
<tr>
<th valign="top">

Alert Subject

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

CPU usage of the Worker Pod exceeds 95%

</td>
<td valign="top">

The CPU usage of the Worker Pod is significantly high.

The CPU limit is determined by the Worker's Runtime Parameter.

</td>
</tr>
<tr>
<td valign="top">

Busy thread count of the Worker Pod exceeds 80%

</td>
<td valign="top">

Busy thread count of the Worker Pod is significantly high.

A high number of HTTP threads are currently processing requests.

</td>
</tr>
<tr>
<td valign="top">

Busy thread count of the Worker Pod exceeds 95%

</td>
<td valign="top">

Busy thread count of the Worker Pod is extremely high.

A very high number of HTTP threads are currently processing requests.

</td>
</tr>
<tr>
<td valign="top">

Java Memory usage of the Worker Pod exceeds 95%

</td>
<td valign="top">

The Java Memory usage of the Worker Pod is significantly high.

The Java Memory limit is determined by the Worker's Runtime Parameter.

</td>
</tr>
<tr>
<td valign="top">

Worker has stuck artifacts

</td>
<td valign="top">

An artifact is considered stuck if it stays in a transition state for more than 60 minutes.

Integration Flow\(s\) cannot be started.

</td>
</tr>
</table>

**Related Information**  


[Solace Monitor](solace-monitor-26a7894.md "Monitor Solace Broker metrics, keep track of resource utilization, and access information about message VPNs, queues, and clients.")

