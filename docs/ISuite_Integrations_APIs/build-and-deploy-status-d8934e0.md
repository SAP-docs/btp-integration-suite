<!-- loiod8934e0d3ab649ecb5ae744663c7962c -->

# Build and Deploy Status

Indicates the status of an artifact that is triggered for deployment.

You can access integration flow configurations through the `BuildAndDeployStatus` resource.

For integration artifacts that have reached the worker node, another status becomes relevant, the runtime status. The runtime status indicates if a deployed artifact is ready to operate \(see [Runtime Status](runtime-status-c14a7b1.md)\).

There are the following status values for the build and deploy status.

**Status Values**


<table>
<tr>
<th valign="top">

Status

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*SUCCESS* 

</td>
<td valign="top">

The artifact is deployed on worker node\(s\).

</td>
</tr>
<tr>
<td valign="top">

*FAIL* 

</td>
<td valign="top">

The artifact isn't deployed on worker node\(s\), for example, because of a validation error/CMD checks error in the currently deployed integration flow.

</td>
</tr>
<tr>
<td valign="top">

*DEPLOYING* 

</td>
<td valign="top">

The artifact is in the process of being deployed.

</td>
</tr>
<tr>
<td valign="top">

*FAIL\_ON\_LICENSE\_ERROR* 

</td>
<td valign="top">

The artifact isn't deployed on worker node\(s\) because the integration flow contains components that require an upgrade to the user’s existing license.

</td>
</tr>
</table>

**Related Information**  


[Runtime Status](runtime-status-c14a7b1.md "Indicates if a deployed artifact is ready to operate.")

[Deployment Status View](deployment-status-view-40add87.md "Use this view to see the deployment information of the integration flows and easily navigate to the Monitor view to see the runtime status.")

