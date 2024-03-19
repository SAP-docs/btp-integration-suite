<!-- loio49f487ec05c54861a0f970e9bdc529e5 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Component Monitor

Get information on the components.

The Component Monitor tile shows you the most important information regarding your components at a glance. Out of all components for Edge Integration Cell, the tile always shows either those components in status *Error* or the status of the top three components, *Policy Engine*, *Worker*, and *Solace* \(Message Service\) in status *Ok*.

Click on the tile to get a details view. On the screen, you see a table with the following information:


<table>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Name of the component in alphabetical order. The color indicates the status with green indicating *Running* \(:heavy_check_mark:\) and red indicating *Error* \(<span class="SAP-icons-V5"></span> Error\).

</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

Status of Resources:

Error

If the *Pod Status* indicates an error, select *View Pod Events* \(<span class="SAP-icons-V5"></span> View Pod Events \) to show the details of the pod events. For more information about pod events, see [https://kubernetes.io/docs/reference/kubernetes-api/cluster-resources/event-v1/\#Event.](https://kubernetes.io/docs/reference/kubernetes-api/cluster-resources/event-v1/#Event.) 

Running

</td>
</tr>
<tr>
<td valign="top">

*Pod Name*

</td>
<td valign="top">

Technical name of the pod.

</td>
</tr>
<tr>
<td valign="top">

*Ready*

</td>
<td valign="top">

Number of resources.

</td>
</tr>
<tr>
<td valign="top">

*Restarts*

</td>
<td valign="top">

Number showing the restarts made.

</td>
</tr>
</table>

> ### Note:  
> For more information on runtime parameters, see: [Runtime Parameters](runtime-parameters-63c5276.md).

**Related Information**  


[Operations Cockpit](operations-cockpit-ec0fc95.md "The Operations Cockpit is the central control point for operating edge integration cells and allows the Edge Integration Cell administrator to monitor and adjust system configurations and resources.")

[Job Management](job-management-4146fa5.md "Organize and schedule your existing system jobs, such as data store entries cleanup or trace entries cleanup, or add jobs manually.")

[Runtime Parameters](runtime-parameters-63c5276.md "Get information about the runtime parameters of your Edge Integration Cell.")

