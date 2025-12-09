<!-- loio63c52764cb58458aba7e58bbf678d453 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Runtime Parameters

View the runtime parameters of the components of your Edge Integration Cell.

On *Component Monitor*, select a component from the list to display information about its runtime parameters.

The table offers the following information:

**Runtime Parameters**


<table>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

The technical name.

</td>
</tr>
<tr>
<td valign="top">

*Category*

</td>
<td valign="top">

-   *Configuration*

-   *Environment*




</td>
</tr>
<tr>
<td valign="top">

*Default*

</td>
<td valign="top">

The default value set for this parameter. The default value can be overwritten by adding a custom value.

</td>
</tr>
<tr>
<td valign="top">

*Custom Value*

</td>
<td valign="top">

Enter a custom value and change the default value by choosing :pencil2:. Make your changes and confirm by selecting *Apply*. Choose *Save* to run the changes in the back end. A change of a runtime parameter typically causes a rolling restart of pods in Edge Integration Cell.

> ### Note:  
> You can't decrease the default values of certain parameters. If you attempt to make such changes, an error message informs you of this restriction.



</td>
</tr>
</table>

For more information on the Edge Integration Cell component configuration, have a look at the following table:


<table>
<tr>
<th valign="top">

Component

</th>
<th valign="top">

Configuration Option

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top" rowspan="6">

*Edge Deploy Controller* 

</td>
<td valign="top">

`LOG_LEVEL` 

</td>
<td valign="top">

Sets log level for a component.

Possible values are *error*, *warn*, *info*, *debug*.

</td>
</tr>
<tr>
<td valign="top">

`MIN_REPLICAS` 

</td>
<td valign="top">

Sets the minimum number of replicas for this Deployment using HorizontalPodAutoscaler \(HPA\).

</td>
</tr>
<tr>
<td valign="top">

`MAX_REPLICAS` 

</td>
<td valign="top">

Sets the maximum number of replicas for this Deployment using HorizontalPodAutoscaler \(HPA\).

</td>
</tr>
<tr>
<td valign="top">

`CPU_LIMIT` 

</td>
<td valign="top">

Sets CPU limit for this component. The default value is 600 Mi.

</td>
</tr>
<tr>
<td valign="top">

`MEMORY_LIMIT` 

</td>
<td valign="top">

Sets memory limit for this component. The default value is 512 Mi.

</td>
</tr>
<tr>
<td valign="top">

`EPHEMERAL_STORAGE_LIMIT` 

</td>
<td valign="top">

Sets ephemeral storage limit for this component. The default value is 300 Mi.

</td>
</tr>
<tr>
<td valign="top">

*Edge Event Controller* 

</td>
<td valign="top">

`LOG_LEVEL` 

</td>
<td valign="top">

Sets log level for a component.

Possible values are *error*, *warn*, *info*, *debug*.

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

*Edge Security Artifact Controller* 

</td>
<td valign="top">

`CPU_LIMIT` 

</td>
<td valign="top">

Sets CPU limit for this component.

</td>
</tr>
<tr>
<td valign="top">

`MEMORY_LIMIT` 

</td>
<td valign="top">

Sets memory limit for this component.

</td>
</tr>
<tr>
<td valign="top">

`REPLICAS` 

</td>
<td valign="top">

Sets the number of replicas for this component.

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

*Edge API Application* 

</td>
<td valign="top">

`CPU_LIMIT` 

</td>
<td valign="top">

Sets CPU limit for this component.

</td>
</tr>
<tr>
<td valign="top">

`REPLICAS` 

</td>
<td valign="top">

Sets the number of replicas for this component.

</td>
</tr>
<tr>
<td valign="top">

`JAVA_OPTS` 

</td>
<td valign="top">

Additional JVM parameters.

</td>
</tr>
<tr>
<td valign="top">

`MEMORY_LIMIT` 

</td>
<td valign="top">

Sets memory limit for this component.

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

*Monitoring Data Consumer* 

</td>
<td valign="top">

`CPU_LIMIT` 

</td>
<td valign="top">

Sets CPU limit for this component.

</td>
</tr>
<tr>
<td valign="top">

`MEMORY_LIMIT` 

</td>
<td valign="top">

Sets memory limit for this component.

</td>
</tr>
<tr>
<td valign="top">

`ISTIO_TERMINATION_DRAIN_DURATION` 

</td>
<td valign="top">

Sets the drain duration before istio termination.

</td>
</tr>
<tr>
<td valign="top">

`PRESTOP_DRAIN_DURATION` 

</td>
<td valign="top">

Sets the drain duration before the component stops.

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

*Policy Engine* 

</td>
<td valign="top">

`LOG_LEVEL` 

</td>
<td valign="top">

Sets log level for a component.

Possible values are *error*, *warn*, *info*, *debug*.

</td>
</tr>
<tr>
<td valign="top">

`MIN_REPLICAS` 

</td>
<td valign="top">

Sets the minimum number of replicas for this Deployment using HorizontalPodAutoscaler \(HPA\).

</td>
</tr>
<tr>
<td valign="top">

`MAX_REPLICAS` 

</td>
<td valign="top">

Sets the maximum number of replicas for this Deployment using HorizontalPodAutoscaler \(HPA\).

</td>
</tr>
<tr>
<td valign="top" rowspan="18">

*Worker* 

</td>
<td valign="top">

`CPU_LIMIT` 

</td>
<td valign="top">

Sets CPU limit for this component.

</td>
</tr>
<tr>
<td valign="top">

`MEMORY_LIMIT` 

</td>
<td valign="top">

Sets memory limit for this component.

</td>
</tr>
<tr>
<td valign="top">

`NZDM_ENABLED` 

</td>
<td valign="top">

Enables Near Zero Downtime \(NZDM\) startup behavior for workers.

</td>
</tr>
<tr>
<td valign="top">

`REPLICAS` 

</td>
<td valign="top">

Sets the number of replicas for this component.

</td>
</tr>
<tr>
<td valign="top">

`JAVA_OPTS` 

</td>
<td valign="top">

Additional JVM parameters for this component.

You can update the metaspace size based on your content and container size.

> ### Example:  
> \-XX:MaxMetaspaceSize=750M

See: [Edge Integration Cell Runtime Scope](edge-integration-cell-runtime-scope-144c64a.md).

</td>
</tr>
<tr>
<td valign="top">

`JBP_CONFIG_SAPJVM` 

</td>
<td valign="top">

Sets parameters for java memory calculator.

</td>
</tr>
<tr>
<td valign="top">

`READINESSPROBE_FAILURE_THRESHOLD` 

</td>
<td valign="top">

Sets the failure threshold for the readiness probe of the deployment resource.

</td>
</tr>
<tr>
<td valign="top">

`EPHEMERAL_STORAGE_LIMIT` 

</td>
<td valign="top">

Sets ephemeral storage limit for this component. Default value: 10 Gi

</td>
</tr>
<tr>
<td valign="top">

`ISTIO_CPU_LIMIT`

</td>
<td valign="top">

Sets CPU limit for Istio proxy sidecar.

</td>
</tr>
<tr>
<td valign="top">

`ISTIO_CPU_REQUEST`

</td>
<td valign="top">

Sets CPU request for Istio proxy sidecar.

</td>
</tr>
<tr>
<td valign="top">

`ISTIO_MEMORY_LIMIT`

</td>
<td valign="top">

Sets memory limits for Istio proxy sidecar.

</td>
</tr>
<tr>
<td valign="top">

`ISTIO_MEMORY_REQUEST`

</td>
<td valign="top">

Sets memory request for Istio proxy sidecar.

</td>
</tr>
<tr>
<td valign="top">

`RFC_ADAPTER_POOL_CHECK_RATE`

</td>
<td valign="top">

The RFC adapter creates a pool of connections for each sender channel based on the initial connection count. This property specifies how often the system checks the connection utilization in the pool. It can also resize the pool by increasing the number of connections. A check rate of zero means no check is performed. The default value is 3,600 seconds.

</td>
</tr>
<tr>
<td valign="top">

`RFC_ADAPTER_POOL_LOAD_THRESHOLD`

</td>
<td valign="top">

A new connection in the pool starts only when a threshold is reached. If the current pool size \(available connections\) minus the value of this property is less than or equal to the number of currently working connections, a new connection starts. A value of zero means a new connection starts only if all available connections are working. If the value is larger, a new connection starts before all available connections are working. The default value is zero.

</td>
</tr>
<tr>
<td valign="top">

`RFC_ADAPTER_POOL_MAX_SIZE` 

</td>
<td valign="top">

The global adapter limit for the connection pool size. The default value is 50.

</td>
</tr>
<tr>
<td valign="top">

`RFC_ADAPTER_XML_IGNORE_BASE64_CONSTRAINTS` 

</td>
<td valign="top">

The default value is "false". If set to true, base64 incompatible characters can be decoded from RFC-XML.

</td>
</tr>
<tr>
<td valign="top">

`RFC_ADAPTER_XML_INVALID_CHARACTERS` 

</td>
<td valign="top">

The default value is "ignore". This means that there's no handling of invalid XML characters. The value "substitute" means invalid characters are replaced with character "\#".

</td>
</tr>
<tr>
<td valign="top">

`RFC_ADAPTER_XML_WRITE_XML_PREAMBLE_TO_PAYLOAD` 

</td>
<td valign="top">

Determines whether an XML preamble is added to the RFC-XML. The default value is "true".

</td>
</tr>
<tr>
<td valign="top">

*Message Service* 

</td>
<td valign="top">

`SOLACE_TIER` 

</td>
<td valign="top">

Upscales the Message Service Tier.

For more information on Message Service Tiers, see [Message Service Tiers](runtime-parameters-63c5276.md#loio63c52764cb58458aba7e58bbf678d453__section_nht_rwb_hgc).

</td>
</tr>
<tr>
<td valign="top" rowspan="7">

*Message Service Operations* 

</td>
<td valign="top">

`LOG_LEVEL` 

</td>
<td valign="top">

Sets log level for a component.

Possible values are *error*, *warn*, *info*, *debug*.

</td>
</tr>
<tr>
<td valign="top">

`MAX_ENDPOINTS` 

</td>
<td valign="top">

Sets maximum number of queues and topic endpoints

> ### Note:  
> Note that the configuration parameters for MAX may be limited by the chosen Message Service Tier. The Message Service Tier sets system boundaries for configuration parameters such as Max Endpoints \(which includes Max Queues, with the JMS Adapter requiring three internal queues for each JMS Queue\), Max Egress Flows, Max Ingress Flows, Max Transacted Sessions \(which shares the same system limit value as Max Connections\) and Max Transactions \(which is five times the system limit value of Max Connections\).



</td>
</tr>
<tr>
<td valign="top">

`MAX_EGRESS_FLOWS` 

</td>
<td valign="top">

Sets maximum number of egress \(consumer\) flows.

</td>
</tr>
<tr>
<td valign="top">

`MAX_INGRESS_FLOWS` 

</td>
<td valign="top">

Sets maximum number of ingress \(publisher\) flows.

</td>
</tr>
<tr>
<td valign="top">

`MAX_TRANSACTED_SESSIONS` 

</td>
<td valign="top">

Sets maximum number of simultaneous transacted sessions.

</td>
</tr>
<tr>
<td valign="top">

`MAX_TRANSACTIONS` 

</td>
<td valign="top">

Sets maximum number of simultaneous transactions.

</td>
</tr>
<tr>
<td valign="top">

`MAX_SUBSCRIPTIONS` 

</td>
<td valign="top">

Sets maximum number of client subscriptions.

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

*Auditlog Agent*

</td>
<td valign="top">

`CPU_LIMIT`

</td>
<td valign="top">

Sets CPU limit for this component.

</td>
</tr>
<tr>
<td valign="top">

`MEMORY_LIMIT`

</td>
<td valign="top">

Sets memory limit for this component.

</td>
</tr>
<tr>
<td valign="top">

`REPLICAS`

</td>
<td valign="top">

Sets the number of replicas for this component.

</td>
</tr>
<tr>
<td valign="top">

`JAVA_OPTS`

</td>
<td valign="top">

Additional JVM parameters for this component.

</td>
</tr>
</table>



<a name="loio63c52764cb58458aba7e58bbf678d453__section_nht_rwb_hgc"/>

## Message Service Tiers


<table>
<tr>
<th valign="top">

Service Tier

</th>
<th valign="top">

Max. Connections

</th>
<th valign="top">

Max. Queue Messages \[millions\]

</th>
<th valign="top">

CPU Limit

</th>
<th valign="top">

Memory Limit \[GiB\]

</th>
<th valign="top">

Persistent Volume \[GiB\]

</th>
</tr>
<tr>
<td valign="top">

100

</td>
<td valign="top">

100

</td>
<td valign="top">

100

</td>
<td valign="top">

2

</td>
<td valign="top">

3.4

</td>
<td valign="top">

100

</td>
</tr>
<tr>
<td valign="top">

250

</td>
<td valign="top">

250 \(VPN\) / 1000 \(System\)

</td>
<td valign="top">

100

</td>
<td valign="top">

2

</td>
<td valign="top">

6.5

</td>
<td valign="top">

100

</td>
</tr>
<tr>
<td valign="top">

1K

</td>
<td valign="top">

1000

</td>
<td valign="top">

240

</td>
<td valign="top">

2

</td>
<td valign="top">

6.5

</td>
<td valign="top">

350

</td>
</tr>
<tr>
<td valign="top">

10K

</td>
<td valign="top">

10000

</td>
<td valign="top">

240

</td>
<td valign="top">

4

</td>
<td valign="top">

13.9

</td>
<td valign="top">

350

</td>
</tr>
<tr>
<td valign="top">

100K

</td>
<td valign="top">

100000

</td>
<td valign="top">

240

</td>
<td valign="top">

8

</td>
<td valign="top">

30.3

</td>
<td valign="top">

500

</td>
</tr>
<tr>
<td valign="top">

200K

</td>
<td valign="top">

200000

</td>
<td valign="top">

240

</td>
<td valign="top">

12

</td>
<td valign="top">

53.5

</td>
<td valign="top">

500

</td>
</tr>
</table>

