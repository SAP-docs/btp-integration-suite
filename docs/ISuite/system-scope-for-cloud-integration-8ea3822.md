<!-- loio8ea3822bfb654e219b456959aad672c2 -->

# System Scope for Cloud Integration 

This section describes the system scope for the Cloud Integration capability. Read the recommendations to know how to optimize the resources when exceeding the scope.


<table>
<tr>
<th valign="top">

Resource

</th>
<th valign="top">

Scope

</th>
</tr>
<tr>
<td valign="top">

**Integration content**

</td>
<td valign="top">

2 GB

Refer to the blog on [Content Size Limits](https://blogs.sap.com/2020/08/02/cloud-integration-content-size-limits/) learn how to reduce your integration content size.

</td>
</tr>
<tr>
<td valign="top">

**JMS queues**

</td>
<td valign="top">

9 GB, 150 transactions \(default configuration with 30 queues\)

Can be scaled up to 30 GB, 500 transactions \(with 100 queues\)

See the blog on [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/) for further guidance on how to set the queue size to restrict the limit and on how to delete unused queues.

</td>
</tr>
<tr>
<td valign="top">

**Message processing log persistence**

</td>
<td valign="top">

35 GB

See: [Cloud Integration – Setting the Log Level for Message Processing](https://blogs.sap.com/2017/06/22/cloud-integration-setting-the-log-level-for-message-processing/)

</td>
</tr>
<tr>
<td valign="top">

**Runtime database**

</td>
<td valign="top">

35 GB

See: [Optimize Performance](50-Development/optimize-performance-491c80d.md)

</td>
</tr>
<tr>
<td valign="top">

**Disk space**

</td>
<td valign="top">

10 GB

Refer to SAP Note [2648415](https://me.sap.com/notes/2648415) to learn how to optimize the integration flow development to prevent the integration flow from running into the “No More Space left on Disk” error.

</td>
</tr>
</table>

For more information on the available data storage features, refer to [Data Storages](50-Development/data-storages-31efe35.md).

