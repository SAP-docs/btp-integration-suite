<!-- loioc14a7b18544f4495ab32e41630074726 -->

# Runtime Status

Indicates if a deployed artifact is ready to operate.

The following status values are possible.

**Statuses**


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

*Started* 

</td>
<td valign="top">

The artifact is ready to be used.

An artifact with this status is in a final state.

</td>
</tr>
<tr>
<td valign="top">

*Error* 

</td>
<td valign="top">

The artifact requires attention by the user \(administrator\).

An artifact with this status is in a final state.

</td>
</tr>
<tr>
<td valign="top">

*Starting* 

</td>
<td valign="top">

The artifact is in the process of being deployed on the worker node\(s\) and, if deployed, is being started.

An artifact with this status is in an intermediate state.

</td>
</tr>
<tr>
<td valign="top">

*Stopping* 

</td>
<td valign="top">

The artifact is in the process of being stopped on the worker node\(s\) and, if stopped, is being undeployed.

An artifact with this status is in an intermediate state.

During the process of undeployment, the artifact has status *Stopping*. An artifact with this status cannot be restarted, undeployed or downloaded.

</td>
</tr>
</table>

> ### Tip:  
> You can also use the SAP Integration Suite OData API to get the runtime status of a deployed integration flow. For more information, see [Get Runtime Status of Deployed Integration Flow](get-runtime-status-of-deployed-integration-flow-49c7336.md).

**Related Information**  


[Deployment Status View](deployment-status-view-40add87.md "Use this view to see the deployment information of the integration flows and easily navigate to the Monitor view to see the runtime status.")

