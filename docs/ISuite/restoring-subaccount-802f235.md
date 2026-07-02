<!-- loio802f2359dd58469ab2f06de22a82e60a -->

# Restoring Subaccount

This topic provides information on how to restore a subaccount which is deleted from BTP cockpit and outlines the impact of subaccount deletion on your tenant and integration artifacts.

When a global account administrator deletes a subaccount using the **Force Delete** option, instead of immediate deletion, the subaccount will be marked as **Pending Deletion** and suspended for one week. During this period global admin can restore the subaccount.

See:

-   [Delete a Subaccount](https://help.sap.com/docs/btp/sap-business-technology-platform/delete-subaccount?version=Cloud)
-   [Managing Global Accounts Using the Cockpit](https://help.sap.com/docs/btp/sap-business-technology-platform/managing-global-accounts-using-cockpit?version=Cloud)



## Impact of Subaccount Deletion

During the suspension period, you can't access the tenant and the integration artifacts won't be deleted but the design time and Runtime for all the Integration Suite capabilities won't be available. The exceptions for each capability is captured in the table below:

> ### Tip:  
> If you want runtime access to be blocked immediately, then unsubscribe Integration Suite instead of using force delete from BTP cockpit. See [Unsubscribing from SAP Integration Suite](https://help.sap.com/docs/integration-suite/sap-integration-suite/unsubscribing-from-integration-suite?version=CLOUD)

****


<table>
<tr>
<th valign="top">

Capability/Runtime Profile

</th>
<th valign="top">

Area of Impact

</th>
<th valign="top">

Impact

</th>
<th valign="top">

Solution or Action

</th>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

Polling / Scheduled Integration Flows

</td>
<td valign="top">

Such integration flows \(for example, FTP adapter or scheduler-based flows\) will continue to run.

The metering for such flows will continue. See [2942344](https://me.sap.com/notes/2942344)

</td>
<td valign="top" rowspan="6">

Contact subaccount or global account admin to know the details or restore your account.

</td>
</tr>
<tr>
<td valign="top">

Cloud Integration

</td>
<td valign="top">

HTTP-Based Artifacts

</td>
<td valign="top">

Such integration flows will fail at runtime.

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

API Management solution to access data from an On Premise server

</td>
<td valign="top">

Such API Management solution configured to access data from an on premise server via API provider with connection type*On Premise* will fail at runtime.

The metering for such flows will continue. See [2942344](https://me.sap.com/notes/2942344)

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

API Management solution to connect to Integration Flows \(using API Provider with type Cloud Integration\)

</td>
<td valign="top">

Such integration flows will fail at runtime.

The metering for such flows will continue. See [2942344](https://me.sap.com/notes/2942344)

</td>
</tr>
<tr>
<td valign="top">

API Management

</td>
<td valign="top">

API Proxy Execution

</td>
<td valign="top">

Such API call execution will continue to work.

The metering for such flows will continue. See [2942344](https://me.sap.com/notes/2942344)

</td>
</tr>
<tr>
<td valign="top">

Event Mesh

</td>
<td valign="top">

Events flowing though Event Mesh topics and queues.

</td>
<td valign="top">

Events will cease to flow through Event Mesh. However, any messages already persisted in queues will not be lost.

Metering for webhook scenarios will continue. See [2942344](https://me.sap.com/notes/2942344)

</td>
</tr>
<tr>
<td valign="top">

Edge Integration Cell Runtime Profile

</td>
<td valign="top">

Integration flows in this runtime profile

</td>
<td valign="top">

Integration flows continue running.

</td>
<td valign="top">

Stop the edge node to block execution. See [Undeploy Edge Integration Cell from the Kubernetes Cluster](https://help.sap.com/viewer/caeaa5e76f8c486ebea167938fa1f40b/CLOUD/en-US/80ead4a4125349fdbd4604dea2bd34fd.html "Learn how to undeploy Edge Integration Cell from the Kubernetes cluster.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Open Connector

</td>
<td valign="top">

 

</td>
<td valign="top">

API call execution will continue to work.

The metering for such scenarios will continue. See [2942344](https://me.sap.com/notes/2942344)

</td>
<td valign="top">

Contact subaccount or global account tenant admin to know the details or restore your account.

</td>
</tr>
</table>

