<!-- loio40add8788c294273bfbcf671ab0efe15 -->

# Deployment Status View

Use this view to see the deployment information of the integration flows and easily navigate to the *Monitor* view to see the runtime status.

In the *Deployment Status* view, you can see whether the artifact is deployed or not. The following attributes are displayed:


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Deployment Status

</td>
<td valign="top">

Indicates if integration flow artifact is deployed on worker node.

The following values are possible: *Deployed*, *Not Deployed*.

If the status is *Deployed*, a link is shown. Click the link to navigate to the *Monitor* view of the artifact.

</td>
</tr>
<tr>
<td valign="top">

Runtime Status

</td>
<td valign="top">

Indicates if deployed integration flow artifact is ready to operate and process messages.

An entry is shown only if *Deployment Status* is *Deployed*.

The runtime status can have the values as described under [Runtime Status](runtime-status-c14a7b1.md).

</td>
</tr>
<tr>
<td valign="top">

Deployed By

</td>
<td valign="top">

User who deployed the artifact

An entry is shown only if *Deployment Status* is *Deployed*.

</td>
</tr>
<tr>
<td valign="top">

Deployed On

</td>
<td valign="top">

Time when artifact was deployed

An entry is shown only if *Deployment Status* is *Deployed*.

</td>
</tr>
<tr>
<td valign="top">

Deployed Version

</td>
<td valign="top">

Version of artifact that is deployed

An entry is shown only if *Deployment Status* is *Deployed*.

</td>
</tr>
</table>

Additionally, on the header of integration flow editor, next to the artifact name, you see the deployment status, irrespective of which tab in the property sheet you're in.





### Benefits of the *Deployment Status* View

-   Upon a trigger for deployment, you see the deployment status in the integration flow editor itself. You need not open the *Monitor* view to see this status.

-   The link next to the deployment status points you to the *Monitor* view for integration flow, saving you clicks and time to see the runtime status.

-   If the runtime status of the artifact goes into an error, you get to see an error message explaining the reason for the error. You need not open the *Monitor* view to see the details of the error.


**Related Information**  


[Runtime Status](runtime-status-c14a7b1.md "Indicates if a deployed artifact is ready to operate.")

