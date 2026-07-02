<!-- loiofe8c67d4c5c64bf2a007ee2efa0842b9 -->

# Alerting

Edge Integration Cell includes alert rules for selected components. You can use these in addition to default alert rules provided by Edge Lifecycle Management. For more information, see [Alerting with SAP Alert Notification Service for SAP BTP](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/48c168304ed84622ba90d9a88d3698d4.html).

**Message Service Alerts**

These alert rules are related to the most important events that affect the Message Service.


<table>
<tr>
<th valign="top">

Alert Subject

</th>
<th valign="top">

Description

</th>
<th valign="top">

Technical Name of the Alert

</th>
<th valign="top">

Severity

</th>
</tr>
<tr>
<td valign="top">

Message Service StatefulSet not ready

</td>
<td valign="top">

Message Service StatefulSet is not ready

Primary Broker might not be able to startup or Backup Broker is down \(in HA setup\)

</td>
<td valign="top">

SOLACE\_STS\_NOT\_READY

</td>
<td valign="top">

WARNING

</td>
</tr>
<tr>
<td valign="top">

Message Service not available

</td>
<td valign="top">

Message Service is not available

There is no Active Broker pod available, messaging clients will not be able to connect

</td>
<td valign="top">

SOLACE\_NOT\_AVAILABLE

</td>
<td valign="top">

ERROR

</td>
</tr>
<tr>
<td valign="top">

Message Service is not operational

</td>
<td valign="top">

Operational status is not Active

The Message Service is started but is not operational, messaging clients will not be able to connect

</td>
<td valign="top">

SOLACE\_NOT\_OPERATIONAL

</td>
<td valign="top">

ERROR

</td>
</tr>
<tr>
<td valign="top">

Message Service Config-Sync not operational

</td>
<td valign="top">

Config-Sync status is not operational

Message Service is started but [Config-Sync](https://docs.solace.com/Features/Config-Sync/Config-Sync-Overview.htm) is not operational, messaging clients will not be able to connect

</td>
<td valign="top">

SOLACE\_CONFIG\_SYNC\_NOT\_OPERATIONAL

</td>
<td valign="top">

ERROR

</td>
</tr>
<tr>
<td valign="top">

Message Service Connections usage is above 80%

</td>
<td valign="top">

Connections usage is quite high

Connection limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_CONNECTIONS\_WARNING

</td>
<td valign="top">

WARNING

</td>
</tr>
<tr>
<td valign="top">

Message Service Connections usage is above 95%

</td>
<td valign="top">

Connections usage is very high

Connection limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_CONNECTIONS\_ERROR

</td>
<td valign="top">

ERROR

</td>
</tr>
<tr>
<td valign="top">

Message Service Queues and Topic Endpoints usage is above 80%

</td>
<td valign="top">

Queues and Topic Endpoints usage is quite high

Endpoints limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_QUEUES\_AND\_TOPICS\_WARNING

</td>
<td valign="top">

WARNING

</td>
</tr>
<tr>
<td valign="top">

Message Service Queues and Topic Endpoints usage is above 95%

</td>
<td valign="top">

Queues and Topic Endpoints usage is very high

Endpoints limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_QUEUES\_AND\_TOPICS\_ERROR

</td>
<td valign="top">

ERROR

</td>
</tr>
<tr>
<td valign="top">

Message Service Message Storage usage is above 80%

</td>
<td valign="top">

Message Storage usage is quite high

Message Storage \(Message Spool\) limit is defined by Message Service Tier

</td>
<td valign="top">

SOLACE\_MESSAGE\_STORAGE\_WARNING

</td>
<td valign="top">

WARNING

</td>
</tr>
<tr>
<td valign="top">

Message Service Message Storage usage is above 95%

</td>
<td valign="top">

Message Storage usage is very high

Message Storage \(Message Spool\) limit is defined by Message Service Tier

</td>
<td valign="top">

SOLACE\_MESSAGE\_STORAGE\_ERROR

</td>
<td valign="top">

ERROR

</td>
</tr>
<tr>
<td valign="top">

Message Service Producers usage is above 80%

</td>
<td valign="top">

Producers \(Ingress Flows\) usage is quite high

Producers limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_PRODUCERS\_WARNING

</td>
<td valign="top">

WARNING

</td>
</tr>
<tr>
<td valign="top">

Message Service Producers usage is above 95%

</td>
<td valign="top">

Producers \(Ingress Flows\) usage is very high

Producers limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_PRODUCERS\_ERROR

</td>
<td valign="top">

ERROR

</td>
</tr>
<tr>
<td valign="top">

Message Service Consumers usage is above 80%

</td>
<td valign="top">

Consumers \(Egress Flows\) usage is quite high

Consumers limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_CONSUMERS\_WARNING

</td>
<td valign="top">

WARNING

</td>
</tr>
<tr>
<td valign="top">

Message Service Consumers usage is above 95%

</td>
<td valign="top">

Consumers \(Egress Flows\) usage is very high

Consumers limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_CONSUMERS\_ERROR

</td>
<td valign="top">

ERROR

</td>
</tr>
<tr>
<td valign="top">

Message Service Transacted Sessions usage is above 80%

</td>
<td valign="top">

Transacted Sessions usage is quite high

Transacted Sessions limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_TRANSACTED\_SESSIONS\_WARNING

</td>
<td valign="top">

WARNING

</td>
</tr>
<tr>
<td valign="top">

Message Service Transacted Sessions usage is above 95%

</td>
<td valign="top">

Transacted Sessions usage is very high

Transacted Sessions limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_TRANSACTED\_SESSIONS\_ERROR

</td>
<td valign="top">

ERROR

</td>
</tr>
<tr>
<td valign="top">

Message Service Transactions usage is above 80%

</td>
<td valign="top">

Transactions usage is quite high

Transactions limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_TRANSACTIONS\_WARNING

</td>
<td valign="top">

WARNING

</td>
</tr>
<tr>
<td valign="top">

Message Service Transactions usage is above 95%

</td>
<td valign="top">

Transactions usage is very high

Transactions limit is defined by Message Service Tier or Message Service Operations runtime parameter

</td>
<td valign="top">

SOLACE\_TRANSACTIONS\_ERROR

</td>
<td valign="top">

ERROR

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
<th valign="top">

Technical Name of the Alert

</th>
<th valign="top">

Severity

</th>
</tr>
<tr>
<td valign="top">

CPU usage of the Worker Pod exceeds 95%

</td>
<td valign="top">

The CPU usage of the Worker Pod is significantly high.

The CPU limit is determined by the Worker's runtime parameter.

</td>
<td valign="top">

WORKER\_CPU\_USAGE\_WARNING

</td>
<td valign="top">

WARNING

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
<td valign="top">

WORKER\_BUSY\_THREADS\_WARNING

</td>
<td valign="top">

WARNING

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
<td valign="top">

WORKER\_BUSY\_THREADS\_ERROR

</td>
<td valign="top">

ERROR

</td>
</tr>
<tr>
<td valign="top">

Java Memory usage of the Worker Pod exceeds 95%

</td>
<td valign="top">

The Java Memory usage of the Worker Pod is significantly high.

The Java Memory limit is determined by the Worker's runtime parameter.

</td>
<td valign="top">

WORKER\_MEMORY\_USAGE\_WARNING

</td>
<td valign="top">

WARNING

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
<td valign="top">

WORKER\_STUCK\_ARTIFACTS\_WARNING

</td>
<td valign="top">

WARNING

</td>
</tr>
</table>

**Related Information**  


[Message Service Monitor](message-service-monitor-26a7894.md "Monitor Message Service metrics, keep track of resource utilization, and access information about message VPNs, queues, and clients.")

