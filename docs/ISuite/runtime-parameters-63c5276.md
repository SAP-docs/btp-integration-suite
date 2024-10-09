<!-- loio63c52764cb58458aba7e58bbf678d453 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Runtime Parameters

Get information about the runtime parameters of the components of your Edge Integration Cell.

You can navigate to *View Runtime Parameters* \(<span class="SAP-icons-V5"></span> Runtime Parameters\) through the *Quick Links* card in the Operations Cockpit, or via *Component Monitor*.

You can use the *Component* dropdown in the upper left corner to select the specific component you want information about. Depending on the component you select, the respective information about its runtime parameters displays.

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
<td valign="top" rowspan="3">

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

Additional JVM parameters. Can be set either via env var JAVA\_OPTS in configmap edge-api or Helm value java.opts

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

Sets the drain duration before component stop.

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
<td valign="top" rowspan="8">

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

Additional JVM parameters for this component\).

Same for the others REPLICAS, MIN\_REPLICAS, etc.

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

*Solace* 

</td>
<td valign="top">

`Solace_TIER` 

</td>
<td valign="top">

Upscales the Message Service Tier.

For more information on Message Service Tiers, see [3247839](https://me.sap.com/notes/3247839).

</td>
</tr>
<tr>
<td valign="top" rowspan="7">

*Solops* 

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
> Note that the configuration parameters for Solops' MAX may be limited by the chosen Solace Tier. The Solace Tier sets system boundaries for configuration parameters such as Max Endpoints \(which includes Max Queues, with the JMS Adapter requiring three internal queues for each JMS Queue\), Max Egress Flows, Max Ingress Flows, Max Transacted Sessions \(which shares the same system limit value as Max Connections\) and Max Transactions \(which is five times the system limit value of Max Connections\).



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
</table>

