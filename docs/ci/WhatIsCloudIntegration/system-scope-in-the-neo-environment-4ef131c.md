<!-- loio4ef131c1d72a4d148817f3aad20a75eb -->

# System Scope in the Neo Environment

This section describes the system scope for Cloud Integration tenants that are deployed in the Neo environment. Read the recommendation to know how to optimize the resources when exceeding the scope.


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

500 MB

Refer to the blog on [Content Size Limits](https://blogs.sap.com/2020/08/02/cloud-integration-content-size-limits/) learn how to reduce your integration content size.

</td>
</tr>
<tr>
<td valign="top">

**JMS queues**

</td>
<td valign="top">

9 GB

9 GB, 150 transactions \(default configuration with 30 queues\)

Can be scaled up to 30 GB, 500 transactions \(with 100 queues\)

See the blog on [Cloud Integration – JMS Resource and Size Limits](https://blogs.sap.com/2017/10/04/cloud-integration-jms-resource-and-size-limits-in-cpi-enterprise-edition/) for further guidance on how to set the queue size to restrict the limit and on how to delete unused queues.

</td>
</tr>
<tr>
<td valign="top">

**Tenant database**

</td>
<td valign="top">

32 GB

See the following blogs for information on how to:

-   [Avoid Storing Payloads in the Message Processing Log](https://blogs.sap.com/2017/07/24/avoid-storing-payloads-in-the-message-processing-log/)

-   [Avoid Excessive Storage Load caused by Using MPL Attachments](https://blogs.sap.com/2018/02/12/how-to-avoid-excessive-storage-load-caused-by-using-mpl-attachments-for-message-logging/)

-   [Set the Log Level for Message Processing](https://blogs.sap.com/2017/06/22/cloud-integration-setting-the-log-level-for-message-processing/)




</td>
</tr>
<tr>
<td valign="top">

**Disk space**

</td>
<td valign="top">

2 GB

Refer to SAP Note [2648415](https://me.sap.com/notes/2648415) to learn how to optimize the integration flow development to prevent the integration flow from running into the “No More Space left on Disk” error.

</td>
</tr>
</table>

For more information on the available data storage features, refer to [Data Storages](../Development/data-storages-31efe35.md).

