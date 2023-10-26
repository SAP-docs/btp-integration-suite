<!-- loio6a9c03046bd24d7083927a8274bc03b3 -->

# Checking JMS Resources

Storage capacities of a queue have a limit.

In the *JMS Resources* information box, you can see the status of the current JMS resource usage.

-   *Ok* \(all resources show status *OK*\)

-   *Critical* \(at least one of the resources with status *Critical*\)

-   *Exhausted* \(at least one of the resources with status *Exhausted*\)


Click *Details* to find out more details.

**JMS Resource Details**


<table>
<tr>
<td valign="top">

*Number of Queues* 

</td>
<td valign="top">

Number of queues already in use in reference to the maximum number of queues available.

This row illustrates the remaining resources:

-   *Ok* \(green\): multiple queues remaining.

-   *Critical* \(orange\): only one or no queue remaining.


> ### Note:  
> For more information on how to increase the JMS resources, check out [JMS Resource Limits and Optimizing their Usage](jms-resource-limits-and-optimizing-their-usage-4857054.md).



</td>
</tr>
<tr>
<td valign="top">

*Capacity* 

</td>
<td valign="top">

Data volume \(in MB\) already used compared to the maximum data volume available.

This row illustrates the remaining resources:

-   *Ok* \(green\): Informs the user that the total number of MBs available is \> 20%.

-   *Critical* \(orange\): Informs the user that the total number of MBs available is < 20%.

-   *Exhausted* \(red\): Informs the user that the total number of MBs has reached 95% of the overall available storage.




</td>
</tr>
<tr>
<td valign="top">

*Queue Status* 

</td>
<td valign="top">

Displays a summary of the individual statuses of the respective queues.

> ### Note:  
> The color changes according to the total queues’ statuses.

-   *Ok*\(green\): all queues display the status *Ok*.

-   *Critical* \(orange\): min. 1 queue with status *Warning*.

-   *Exhausted*\(red\): min. 1 queue with status *Error*.




</td>
</tr>
<tr>
<td valign="top">

*Transactions* 

</td>
<td valign="top" rowspan="3">

Consumers, providers, and an open transaction are always required to process a message at runtime. If a message is stored to the JMS queue \(for example, by a JMS receiver channel\), a provider is required. For polling a message from the JMS queue, a consumer is required \(for example, a JMS sender channel\).

If the *JMS Resources* display the status *Critical*, you need to optimize the usage of transactions in consumers and providers.

See:

-   [Define Proper Transaction Handling](define-proper-transaction-handling-1c31963.md)

-   [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/) \(SAP Community blog\)




</td>
</tr>
<tr>
<td valign="top">

*Providers* 

</td>
</tr>
<tr>
<td valign="top">

*Consumers* 

</td>
</tr>
<tr>
<td valign="top">

*Runtime Nodes* 

</td>
<td valign="top">

Number of runtime nodes \(aka worker nodes\) in use.

</td>
</tr>
</table>



<a name="loio6a9c03046bd24d7083927a8274bc03b3__section_fw1_t1l_2yb"/>

## More Information

For more information on the limits and how to increase storage capacity, check out:

-   [JMS Resource Limits and Optimizing their Usage](jms-resource-limits-and-optimizing-their-usage-4857054.md)

-   [JMS Resource Limits and Optimizing their Usage](jms-resource-limits-and-optimizing-their-usage-4857054.md) \(SAP Community blog\)


