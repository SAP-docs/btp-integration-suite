<!-- loio689a9a126580475c9d0b810a813a60d6 -->

# System Monitoring

Access specific monitoring and logging dashboards for Edge Integration Cell.

You can access the monitoring and logging functions for Edge Integration Cell in Edge Lifecycle Management. Navigate to the *Edge Nodes* tab and select the *Edge Node* for which you want to view metrics and logs. In the *General Data* column, choose one of the monitoring and logging*Quick links*. For information about system monitoring and logging stacks, see [Monitoring and Logging](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/373e1688aff8462dbcdd7b28c830639e.html).

There are five preconfigured Grafana dashboards. One dashboard displays general system metrics, including CPU, memory, and disk usage. The other four dashboards focus on the following Edge Integration Cell components:



<a name="loio689a9a126580475c9d0b810a813a60d6__section_m4f_ns5_z2c"/>

## Worker


<table>
<tr>
<th valign="top">

**Metric**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

**Number of Stuck Artifacts**

</td>
<td valign="top">

The number of artifacts stuck in the deployment process. If any artifacts are stuck, it's recommended to restart the worker component.

</td>
</tr>
<tr>
<td valign="top">

**Current Heap Memory Usage**

</td>
<td valign="top">

The percentage of maximum heap memory currently in use.

</td>
</tr>
<tr>
<td valign="top">

**HTTP Threads Busy**

</td>
<td valign="top">

The number of busy and available threads.

</td>
</tr>
<tr>
<td valign="top">

**Connection Count**

</td>
<td valign="top">

The number of connections open to the worker component.

</td>
</tr>
<tr>
<td valign="top">

**Heap Memory**

</td>
<td valign="top">

The size of used, committed and maximum heap memory.

</td>
</tr>
<tr>
<td valign="top">

**Metaspace**

</td>
<td valign="top">

The size of used and committed metaspace.

</td>
</tr>
<tr>
<td valign="top">

**Direct Memory Used**

</td>
<td valign="top">

The size of used direct memory.

</td>
</tr>
<tr>
<td valign="top">

**Request Count**

</td>
<td valign="top">

The number of processed requests.

</td>
</tr>
<tr>
<td valign="top">

**Request Processing Time**

</td>
<td valign="top">

The time spent processing the requests.

</td>
</tr>
<tr>
<td valign="top">

**Bytes Received and Sent**

</td>
<td valign="top">

The volume of bytes sent and received.

</td>
</tr>
<tr>
<td valign="top">

**Average Processing Time per Request**

</td>
<td valign="top">

The average processing time per request. It is calculated by dividing the request processing time by the request count.

</td>
</tr>
<tr>
<td valign="top">

**Garbage Collection Count**

</td>
<td valign="top">

The number of garbage collection runs.

</td>
</tr>
<tr>
<td valign="top">

**Garbage Collection Time**

</td>
<td valign="top">

The time spent on garbage collection.

</td>
</tr>
</table>



<a name="loio689a9a126580475c9d0b810a813a60d6__section_i32_555_z2c"/>

## Policy Engine

**Pod-wise Resource Utilization Metrics**


<table>
<tr>
<th valign="top">

**Metric**

</th>
<th valign="top">

**Description**

</th>
<th valign="top">

**Unit**

</th>
<th valign="top">

**Expected Values**

</th>
</tr>
<tr>
<td valign="top">

**Readiness Probe Status**

</td>
<td valign="top">

Indicates whether the pod is ready to accept requests, as reported by its readiness probe.

</td>
<td valign="top">

\-

</td>
<td valign="top">

Ready

</td>
</tr>
<tr>
<td valign="top">

**CPU Usage**

</td>
<td valign="top">

The CPU usage of policyengine container compared to the CPU requests and limits.

</td>
<td valign="top">

CPU seconds

</td>
<td valign="top">

Below limit

</td>
</tr>
<tr>
<td valign="top">

**Memory Usage**

</td>
<td valign="top">

The memory usage of policyengine container compared to the memory requests and limits.

</td>
<td valign="top">

MB

</td>
<td valign="top">

Below limit

</td>
</tr>
<tr>
<td valign="top">

**Network I/O Rate**

</td>
<td valign="top">

The rate at which the policyengine container receives or transmits data over the network.

</td>
<td valign="top">

Mbps

</td>
<td valign="top">

Actual network traffic

</td>
</tr>
</table>

**Pod-wise Connections Metrics**


<table>
<tr>
<th valign="top">

**Metric**

</th>
<th valign="top">

**Description**

</th>
<th valign="top">

**Unit**

</th>
<th valign="top">

**Expected Values**

</th>
</tr>
<tr>
<td valign="top">

**Message Service Publish Failure Count**

</td>
<td valign="top">

The number of failed attempts by policyengine to publish messages to the Message Service.

</td>
<td valign="top">

\-

</td>
<td valign="top">

0 or no value

</td>
</tr>
<tr>
<td valign="top">

**Message Service Connection Status**

</td>
<td valign="top">

The status of the connection between policyengine and the Message Service.

</td>
<td valign="top">

\-

</td>
<td valign="top">

Connected

</td>
</tr>
<tr>
<td valign="top">

**Redis Connection Status**

</td>
<td valign="top">

The status of the connection between policyengine and the Redis cache.

</td>
<td valign="top">

\-

</td>
<td valign="top">

Connected \(if traffic management policies are configured\) or no value

</td>
</tr>
</table>

**Cross-pod Request/Response Metrics**


<table>
<tr>
<th valign="top">

**Metric**

</th>
<th valign="top">

**Description**

</th>
<th valign="top">

**Expected Values**

</th>
</tr>
<tr>
<td valign="top">

**Successful Calls Processed Count**

</td>
<td valign="top">

Number of calls successfully processed by all running instances of policyengine

</td>
<td valign="top">

Actual usage

</td>
</tr>
<tr>
<td valign="top">

**Errored Calls Count**

</td>
<td valign="top">

Number of calls that encountered errors \(in PE or from backend\) across all running instances of policyengine

</td>
<td valign="top">

Either no data, or it reflects actual usage in case of errors.

</td>
</tr>
<tr>
<td valign="top">

**Duration of 95% Requests**

</td>
<td valign="top">

The maximum duration for up to 95% of successful requests spent in policyengine.

</td>
<td valign="top">

Subject to actual usage, which varies based on the configured API proxies and policies.

</td>
</tr>
<tr>
<td valign="top">

**Duration of 99% Requests**

</td>
<td valign="top">

The maximum duration for up to 95% of successful requests spent in policyengine.

</td>
<td valign="top">

Subject to actual usage, which varies based on the configured API proxies and policies.

</td>
</tr>
<tr>
<td valign="top">

**Successful Request Rate**

</td>
<td valign="top">

Average per-second rate of successfully handled API calls by all instances of policyengine \(based on a 5-min moving average\).

</td>
<td valign="top">

Actual usage

</td>
</tr>
<tr>
<td valign="top">

**Error Rate**

</td>
<td valign="top">

Average per-second rate of API calls facing errors across all pods of policyengine \(based on a 5-min moving average\).

</td>
<td valign="top">

Either no data, or it reflects actual usage in case of errors.

</td>
</tr>
</table>



<a name="loio689a9a126580475c9d0b810a813a60d6__section_sjm_555_z2c"/>

## Edge Event Controller

**Resource Utilization Metrics**


<table>
<tr>
<th valign="top">

**Metric**

</th>
<th valign="top">

**Description**

</th>
<th valign="top">

**Unit**

</th>
<th valign="top">

**Expected Values**

</th>
</tr>
<tr>
<td valign="top">

**Readiness Probe Status**

</td>
<td valign="top">

It indicates whether the pod is ready to accept requests, as reported by its readiness probe.

</td>
<td valign="top">

\-

</td>
<td valign="top">

Ready

</td>
</tr>
<tr>
<td valign="top">

**CPU Usage**

</td>
<td valign="top">

The CPU usage of the edge-event-controller container compared to the CPU requests and limits.

</td>
<td valign="top">

CPU seconds

</td>
<td valign="top">

Below limit

</td>
</tr>
<tr>
<td valign="top">

**Memory Usage**

</td>
<td valign="top">

The memory usage of the edge-event-controller container compared to the memory requests and limits

</td>
<td valign="top">

MB

</td>
<td valign="top">

Below limit

</td>
</tr>
<tr>
<td valign="top">

**Network I/O Rate**

</td>
<td valign="top">

The rate at which the edge-event-controller container transmits or receives data over the network.

</td>
<td valign="top">

Kbps

</td>
<td valign="top">

Actual network traffic

</td>
</tr>
</table>

**Connections Metrics**


<table>
<tr>
<th valign="top">

**Metric**

</th>
<th valign="top">

**Description**

</th>
<th valign="top">

**Expected Values**

</th>
</tr>
<tr>
<td valign="top">

**Cloud Connection Status**

</td>
<td valign="top">

The status of the connection between the edge-event-controller pod and Cloud.

</td>
<td valign="top">

Connected

</td>
</tr>
<tr>
<td valign="top">

**Message Service Connection Status**

</td>
<td valign="top">

The status of the connection between the edge-event-controller pod and the Message Service.

</td>
<td valign="top">

Connected

</td>
</tr>
</table>

**Message Transfer Metrics**


<table>
<tr>
<th valign="top">

**Metric**

</th>
<th valign="top">

**Description**

</th>
<th valign="top">

**Expected Values**

</th>
</tr>
<tr>
<td valign="top">

**Incoming Messages Count**

</td>
<td valign="top">

Number of messages received by edge-event-controller from Cloud or Message Service.

</td>
<td valign="top">

An increasing or horizontal graph

</td>
</tr>
<tr>
<td valign="top">

**Outgoing Messages Count**

</td>
<td valign="top">

Number of messages sent by edge-event-controller to Message Service or Cloud.

</td>
<td valign="top">

An increasing or horizontal graph

</td>
</tr>
<tr>
<td valign="top">

**Successful Message Transfers Count**

</td>
<td valign="top">

Number of acknowledgments received from destination \(Cloud or Message Service\) by edge-event-controller for sent messages.

</td>
<td valign="top">

An increasing or horizontal graph

</td>
</tr>
<tr>
<td valign="top">

**Failed Message Count**

</td>
<td valign="top">

Number of messages received by edge-event-controller but not yet acknowledged successfully by the recipient.

</td>
<td valign="top">

The graph should either have no data or display a continuous zero. If the graph shows non-zero values or an upward trend, it implies failures in EEC message transfers.

</td>
</tr>
<tr>
<td valign="top">

**Message Retries Count**

</td>
<td valign="top">

Number of retries attempted by edge-event-controller for a message sent to Cloud.

</td>
<td valign="top">

Should have no data or be a flat horizontal graph. If this graph is increasing for an extended period, it indicates EEC is unable to transfer messages to cloud

</td>
</tr>
</table>



<a name="loio689a9a126580475c9d0b810a813a60d6__section_xfm_v55_z2c"/>

## Message Service

**Message Service Metrics**


<table>
<tr>
<th valign="top">

**Metrics**

</th>
<th valign="top">

**Description**

</th>
<th valign="top">

**Unit**

</th>
<th valign="top">

**Expected Values**

</th>
</tr>
<tr>
<td valign="top">

**Operational Status**

</td>
<td valign="top">

The operational status of Message Service

</td>
<td valign="top">

\-

</td>
<td valign="top">

*AD-Active*. Message service is operational and Guaranteed Message is active.

</td>
</tr>
<tr>
<td valign="top">

**Data Path Status**

</td>
<td valign="top">

The status of Message Service's Data Path

</td>
<td valign="top">

\-

</td>
<td valign="top">

*UP*. Data path is up and running, otherwise Message Service is not fully operational

</td>
</tr>
<tr>
<td valign="top">

**Disk Status**

</td>
<td valign="top">

The status of Message Service's Disk

</td>
<td valign="top">

\-

</td>
<td valign="top">

*READY*. Otherwise Message Service is not operational and cannot spool messages

</td>
</tr>
<tr>
<td valign="top">

**Config Sync Status - HA only**

</td>
<td valign="top">

\(Only relevant for HA-setup\) The status of synchronization between primary and backup broker

</td>
<td valign="top">

\-

</td>
<td valign="top">

*UP* for HA-setup, *DOWN* for non-HA setup

</td>
</tr>
<tr>
<td valign="top">

**Queues / Topic Endpoints Used**

</td>
<td valign="top">

The percentage of available queues / topic endpoints used

</td>
<td valign="top">

Percentage

</td>
<td valign="top">

Less than 80%

</td>
</tr>
<tr>
<td valign="top">

**Queues / Topic Endpoints**

</td>
<td valign="top">

The number of endpoints/queues in use

</td>
<td valign="top">

Counter

</td>
<td valign="top">

Less than maximum number of queues

</td>
</tr>
<tr>
<td valign="top">

**Connections Used**

</td>
<td valign="top">

The percentage of available connections used

</td>
<td valign="top">

Percentage

</td>
<td valign="top">

Should be less than 80%

</td>
</tr>
<tr>
<td valign="top">

**Connections**

</td>
<td valign="top">

Number of Connections in use

</td>
<td valign="top">

Counter

</td>
<td valign="top">

Less than the maximum number of connections defined by the Message Service Tier.

</td>
</tr>
<tr>
<td valign="top">

**Message Storage Used**

</td>
<td valign="top">

The percentage of available Message Storage used

</td>
<td valign="top">

Percentage

</td>
<td valign="top">

Less than 80%

</td>
</tr>
<tr>
<td valign="top">

**Messages Queued \(MB\)**

</td>
<td valign="top">

The volume of Messages queued

</td>
<td valign="top">

MB

</td>
<td valign="top">

Less than the available disk size defined by the Message Service Tier.

</td>
</tr>
<tr>
<td valign="top">

**Consumers / Egress Flows Used**

</td>
<td valign="top">

The percentage of available consumers / Egress flows used

</td>
<td valign="top">

Percentage

</td>
<td valign="top">

Should be less than 80%

</td>
</tr>
<tr>
<td valign="top">

**Consumers / Egress Flows**

</td>
<td valign="top">

The number of consumers/Egress Flows in use

</td>
<td valign="top">

Counter

</td>
<td valign="top">

Less than the maximum number of Consumers

</td>
</tr>
<tr>
<td valign="top">

**Producers / Ingress Flows Used**

</td>
<td valign="top">

The percentage of available producers / Egress Flows used

</td>
<td valign="top">

Percentage

</td>
<td valign="top">

Less than 80%

</td>
</tr>
<tr>
<td valign="top">

**Producers / Ingress Flows**

</td>
<td valign="top">

The number of producers / Ingress Flows in use

</td>
<td valign="top">

Counter

</td>
<td valign="top">

Less than the maximum number of producers.

</td>
</tr>
<tr>
<td valign="top">

**Transacted Sessions Used**

</td>
<td valign="top">

The percentage of available transacted sessions used

</td>
<td valign="top">

Percentage

</td>
<td valign="top">

Less than 80%

</td>
</tr>
<tr>
<td valign="top">

**Transacted Session**

</td>
<td valign="top">

The number of transacted sessions in use

</td>
<td valign="top">

Counter

</td>
<td valign="top">

Less than the maximum number of transacted sessions

</td>
</tr>
<tr>
<td valign="top">

**Transactions Used**

</td>
<td valign="top">

The percentage of available transactions used

</td>
<td valign="top">

Percentage

</td>
<td valign="top">

Less than 80%

</td>
</tr>
<tr>
<td valign="top">

**Transactions**

</td>
<td valign="top">

The number of transactions in use

</td>
<td valign="top">

Counter

</td>
<td valign="top">

Less than the maximum number of transactions

</td>
</tr>
</table>

**Message Metrics**


<table>
<tr>
<th valign="top">

**Metrics**

</th>
<th valign="top">

**Description**

</th>
<th valign="top">

**Unit**

</th>
<th valign="top">

**Expected Values**

</th>
</tr>
<tr>
<td valign="top">

**Number of Messages Queued**

</td>
<td valign="top">

The number of messages queued

</td>
<td valign="top">

Counter

</td>
<td valign="top">

It shouldn't increase continuously without any decreases, as this indicates messages are piling up and not being processed.

</td>
</tr>
<tr>
<td valign="top">

**Incoming Messages per Second**

</td>
<td valign="top">

The number of messages received by the Message Service per second

</td>
<td valign="top">

Counter

</td>
<td valign="top">

The messages sent to JMS queues

</td>
</tr>
<tr>
<td valign="top">

**Outgoing Messages per Second**

</td>
<td valign="top">

The number of messages transmitted by the Message Service per second

</td>
<td valign="top">

Counter

</td>
<td valign="top">

The messages consumed by JMS queues

</td>
</tr>
<tr>
<td valign="top">

**Incoming Bytes per Second**

</td>
<td valign="top">

The volume of messages received by the Message Service per second

</td>
<td valign="top">

Bytes/sec \(IEC\)

</td>
<td valign="top">

The volume of messages sent to JMS queues

</td>
</tr>
<tr>
<td valign="top">

**Outgoing Bytes per Second**

</td>
<td valign="top">

The volume of messages transmitted by the Message Service per second

</td>
<td valign="top">

Bytes/sec \(IEC\)

</td>
<td valign="top">

The volume of messages consumed from JMS queues

</td>
</tr>
</table>

**Message Service K8s Metrics**


<table>
<tr>
<th valign="top">

**Metrics**

</th>
<th valign="top">

**Description**

</th>
<th valign="top">

**Unit**

</th>
<th valign="top">

**Expected Values**

</th>
</tr>
<tr>
<td valign="top">

**All Pods Running**

</td>
<td valign="top">

The status of Message Service's pods

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

*True*. If not, Message Service itself and/or the monitoring and logging of the Message Service is not operational.

</td>
</tr>
<tr>
<td valign="top">

**Memory Usage**

</td>
<td valign="top">

The amount of memory used by Message Service

</td>
<td valign="top">

Bytes \(IEC\)

</td>
<td valign="top">

A flat graph without high peaks and which doesn't increase contentiously without any decreases.

</td>
</tr>
<tr>
<td valign="top">

**Network Utilization**

</td>
<td valign="top">

The amount of network traffic received and transmitted by Message Service

</td>
<td valign="top">

Bytes \(IEC\)

</td>
<td valign="top">

The analysis of Message Service's load/traffic

</td>
</tr>
</table>



> ### Note:  
> You can download a PostgreSQL metrics dashboard from note [3312134](https://me.sap.com/notes/3312134) and import it into Grafana manually. However, this only works for internal PostgreSQL deployments.



<a name="loio689a9a126580475c9d0b810a813a60d6__section_qgq_qd4_xfc"/>

## Edge Deploy Controller

**Deployment Metrics**


<table>
<tr>
<th valign="top">

**Metric**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

**Deployed Artifacts Count**

</td>
<td valign="top">

The number of artifacts deployed. The count is divided by ARTIFACT\_TYPE.

</td>
</tr>
<tr>
<td valign="top">

**Snapshot Failure Count**

</td>
<td valign="top">

The number of snapshot failures. This includes an aggregated count of generation and publish failures.

</td>
</tr>
<tr>
<td valign="top">

**Runtime Communication Failure Count**

</td>
<td valign="top">

The number of communication failures from EDC to runtime. The count is divided by RUNTIME\_TYPE \(worker/policy engine\).

</td>
</tr>
<tr>
<td valign="top">

**Object Store Connectivity**

</td>
<td valign="top">

The status of the connection between EDC and the object store.

</td>
</tr>
</table>

**Database Metrics**


<table>
<tr>
<th valign="top">

**Metric**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

**Database Connections**

</td>
<td valign="top">

The number of maximum, idle, and used connections in the same panel.

</td>
</tr>
<tr>
<td valign="top">

**Waiting Connections**

</td>
<td valign="top">

The number of waiting connections.

</td>
</tr>
</table>

**Message Service Metrics**


<table>
<tr>
<th valign="top">

**Metric**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

**Message Service Connectivity**

</td>
<td valign="top">

The status of the connection between EDC and Message Service.

</td>
</tr>
</table>



<a name="loio689a9a126580475c9d0b810a813a60d6__section_xzb_h2n_3hc"/>

## Audit Log

**Audit Log Agent Metrics**


<table>
<tr>
<th valign="top">

**Metric**

</th>
<th valign="top">

**Unit**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

**CPU Usage**

</td>
<td valign="top">

Fraction

</td>
<td valign="top">

Proportion of CPU resources that the Java process currently uses. A value of 0.0 means no usage, and a value of 1.0 means full usage of a single core. Values greater than 1.0 can occur on multi-core systems. Sustained high usage indicates performance issues or resource bottlenecks.

</td>
</tr>
<tr>
<td valign="top">

**Memory Usage**

</td>
<td valign="top">

Bytes

</td>
<td valign="top">

Total memory \(heap + non-heap\) currently used by the JVM process. High or growing usage indicates memory leaks, excessive object retention, or insufficient heap configuration.

</td>
</tr>
<tr>
<td valign="top">

**Garbage Collection \(GC\) Pause Time**

</td>
<td valign="top">

Seconds

</td>
<td valign="top">

Maximum pause time caused by garbage collection events since the last measurement. Long pauses increase application latency and affect performance.

</td>
</tr>
<tr>
<td valign="top">

**Messages By Topic**

</td>
<td valign="top">

Number of messages

</td>
<td valign="top">

Current number of messages waiting in each queue topic and pending re-encryption. Use this metric to identify topic backlogs, processing delays, and to make sure that all messages comply with the encryption policy.

</td>
</tr>
<tr>
<td valign="top">

**Processed Messages Rate**

</td>
<td valign="top">

Messages per second

</td>
<td valign="top">

Per-second rate of successfully processed, rate-limited, and failed export messages over 5 minutes. Use this metric to monitor export pipeline health, detect bottlenecks, failures, and throttling events.

</td>
</tr>
<tr>
<td valign="top">

**Server Requests Rate**

</td>
<td valign="top">

Requests per second

</td>
<td valign="top">

Per-second rate of successful and unsuccessful HTTP server requests over 5 minutes. Use this metric to assess server health, client experience and to detect performance degradation or errors.

</td>
</tr>
<tr>
<td valign="top">

**Client Requests Rate**

</td>
<td valign="top">

Requests per second

</td>
<td valign="top">

Per-second rate of successful and unsuccessful HTTP client requests over 5 minutes. Use this metric to monitor reliability of external service calls and detect connectivity issues.

</td>
</tr>
<tr>
<td valign="top">

**Server Response Average Latency**

</td>
<td valign="top">

Seconds \(average per request\)

</td>
<td valign="top">

Average time to serve HTTP requests, grouped by URL \(excluding requests to /actuator/prometheus\). Use this metric to identify slow endpoints, performance bottlenecks, and user experience issues.

</td>
</tr>
<tr>
<td valign="top">

**Server Requests Per Sec \[1m\]**

</td>
<td valign="top">

Seconds

</td>
<td valign="top">

Per-second rate of HTTP requests over one minute, grouped by URL. Use this metric to detect spikes or drops and to identify heavily used endpoints.

</td>
</tr>
<tr>
<td valign="top">

**Client Requests Average Latency**

</td>
<td valign="top">

Seconds \(average per request\)

</td>
<td valign="top">

Average response time for outgoing HTTP client requests, grouped by URL. Use this metric to identify slow dependencies, external service issues, and network bottlenecks.

</td>
</tr>
<tr>
<td valign="top">

**Client Requests Per Sec \[1m\]**

</td>
<td valign="top">

Requests per second

</td>
<td valign="top">

Per-second rate of outgoing HTTP client requests over one minute, grouped by URL. Use this metric to understand external service usage patterns and optimize API call frequency.

</td>
</tr>
<tr>
<td valign="top">

**Server P99 Response Latency \[5m\]**

</td>
<td valign="top">

Seconds \(P99 latency\)

</td>
<td valign="top">

The 99th percentile response latency for incoming HTTP requests over five minutes, grouped by URL. Use this metric to detect tail performance issues that affect the slowest one percent of requests.

</td>
</tr>
<tr>
<td valign="top">

**Server P95 Response Latency \[5m\]**

</td>
<td valign="top">

Seconds \(P95 latency\)

</td>
<td valign="top">

The 95th percentile response latency for incoming HTTP requests over five minutes, grouped by URL. Use this metric to monitor high-percentile performance that affects five percent of requests.

</td>
</tr>
<tr>
<td valign="top">

**Client P99 Request Latency \[5m\]**

</td>
<td valign="top">

Seconds \(P99 latency\)

</td>
<td valign="top">

The 99th percentile latency for outgoing HTTP client requests over 5 minutes, grouped by URL. Use this metric to detect network bottlenecks and extreme latency spikes in external calls.

</td>
</tr>
<tr>
<td valign="top">

**Client P95 Request Latency \[5m\]**

</td>
<td valign="top">

Seconds \(P95 latency\)

</td>
<td valign="top">

The 95th percentile latency of outgoing HTTP client requests over 5 minutes, grouped by URL. use this metric to detect performance degradation affecting a significant portion of client calls.

</td>
</tr>
<tr>
<td valign="top">

**P99 Message Processing Duration \[5m\]**

</td>
<td valign="top">

Seconds \(P99 duration\)

</td>
<td valign="top">

The 99th percentile processing duration for messages that take more than five minutes, grouped by category. Use this metric to identify rare but critical performance bottlenecks in message processing.

</td>
</tr>
<tr>
<td valign="top">

**P95 Total Message Processing Duration \[5m\]**

</td>
<td valign="top">

Seconds \(P95 duration\)

</td>
<td valign="top">

The 95th percentile of message processing duration over five minutes, grouped by category. Use this metric to monitor typical upper-bound processing times without including extreme outliers.

</td>
</tr>
<tr>
<td valign="top">

**Queue Operations Latency**

</td>
<td valign="top">

Seconds \(max. duration\)

</td>
<td valign="top">

The maximum latency for various queue operations \(poll, ack, nack, deadletter, requeue, reencryption polling\). Use this metric to detect performance bottlenecks leading to processing delays, message buildup, or system instability.

</td>
</tr>
</table>

