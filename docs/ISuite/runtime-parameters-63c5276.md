<!-- loio63c52764cb58458aba7e58bbf678d453 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Runtime Parameters

Get information about the runtime parameters of your Edge Integration Cell.

Select *View Runtime Parameters* \(<span class="SAP-icons-V5"></span> Runtime Parameters\) to jump directly to the runtime parameters of the component.

Depending on your selected component, the information about runtime parameters changes on this screen. Use the drop-down in the upper left corner to change your selection of components. The table offers the following information:

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

The default value set for this parameter. The default value can be overwritten by the custom value.

</td>
</tr>
<tr>
<td valign="top">

*Custom Value*

</td>
<td valign="top">

Enter a custom value and change the default value by clicking on :pencil2:. Make your changes and confirm by selecting *Apply*. Select *Save* to run the changes in the back end. A change of a runtime parameter will typically cause a rolling restart of pods in Edge Integration Cell.

</td>
</tr>
</table>

> ### Note:  
> Not all parameters can be decreased by a custom value. If you attempt to make such a change, an error is thrown and you're informed accordingly.

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
<td valign="top" rowspan="3">

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
<td valign="top" rowspan="5">

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

