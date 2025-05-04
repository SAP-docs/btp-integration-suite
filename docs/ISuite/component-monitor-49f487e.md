<!-- loio49f487ec05c54861a0f970e9bdc529e5 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Component Monitor

Get information on your components.

The *Component Monitor* card in the **Operations Cockpit** shows you the most important information regarding your components at a glance. Out of all components for Edge Integration Cell, the card always shows either those components in status *Error* or the status of the top three components, *Policy Engine*, *Worker*, and *Solace* \(Message Service\) in status *OK*.

Choose the card to view the full list of your deployed components and learn more about them. On the *Component Monitor* overview page, you can see a table with the following information:


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

The name of the component \(the list is in alphabetical order\).

</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

The status of the component's resources: *OK*, *Error* or *Warning*

This column shows the combined state of all pods and is calculated based on the **Ready** and **Pod Status** information. For the Status to be **OK** all pods'**Pod Status** must be **Running**, and their current value must equal the expected value in the **Ready** column.

> ### Note:  
> If the pod status indicates an error for one of the components, you can view the specific details of the pod events by selecting **View Pod Events**<span class="SAP-icons-V5"></span> from the *Actions* menu.



</td>
</tr>
<tr>
<td valign="top">

*Pod Name*

</td>
<td valign="top">

The technical name of the pod.

</td>
</tr>
<tr>
<td valign="top">

*Ready*

</td>
<td valign="top">

The number of resources for each component.

The values \(<number\> of <max. number\>\) indicate how many containers are ready in a pod out of the configured target number of containers.

</td>
</tr>
<tr>
<td valign="top">

*Pod Status* 

</td>
<td valign="top">

The status of the component's recent pod events. It can be any of the following:

-   *Evicted* 

-   *Running*

-   *CrashLoopBackOff* 

    *Completed* 

-   *Pending*

-   *Terminating*




</td>
</tr>
<tr>
<td valign="top">

*Restarts*

</td>
<td valign="top">

The number of times a pod has restarted after it was initialized.

> ### Note:  
> These restarts are common in Kubernetes and are nothing to worry about. However, a high number of restarts indicate that a component has a problem.



</td>
</tr>
<tr>
<td valign="top">

*Actions*

</td>
<td valign="top">

You can perform the following actions on the selected component. Depending on the component only some actions are available:

-   **View Pod Events** <span class="SAP-icons-V5"></span>. Examine the pod events associated with the selected component.

    There's no exhaustive list of all pod events, but the Kubernetes documentation provides some examples. For more information, see [https://kubernetes.io/docs/reference/kubernetes-api/cluster-resources/event-v1/\#Event.](https://kubernetes.io/docs/reference/kubernetes-api/cluster-resources/event-v1/#Event.) 

-   **View Runtime Parameters <span class="SAP-icons-V5"></span>**. Navigate to the screen **Runtime Parameters** \(also accessible through the **Quick Links** card in the **Operations Cockpit**\), which provides more detailed information on the runtime parameters of the selected component. For more information, see: [Runtime Parameters](runtime-parameters-63c5276.md).
-   *Create Heap Dump Diagnostic Task*. Diagnose issues related to memory consumption for the selected pod. For more information, see [Diagnostics](diagnostics-80f3050.md).
-   *Create Thread Dump Diagnostic Task*. Diagnose unequal resource usage that may cause system slowness for the selected pod. For more information, see [Diagnostics](diagnostics-80f3050.md).

    > ### Note:  
    > The **Create Heap** and *Thread Dump Diagnostic Tasks* actions become available for components that support *Diagnostics* \(*Edge API App*, *Monitoring Data Consumer*, *Edge Deploy Controller*, and *Edge Security Artifact Controller*\). The menu is enabled when the pod is in the *Running* status and when the number of target containers matches the number in the *Ready* column.

-   *Invalidate Access Token Cache*. Manually invalidate access tokens to streamline authorization changes. By invalidating access tokens, you ensure that the system doesn't reuse old tokens from the cache when you change role assignments. Instead, it generates new tokens accordingly. This way, the authorization changes become effective without delay.

    > ### Note:  
    > This action is enabled in the menu of the Policy Engine component.

-   *Rotate Signing Key*.View the names and validity dates of both the currently active and previous \(deprecated\) keys for the*Edge Local Authentication and Authorization* component. You can choose *Rotate* to deprecate the current key and generate a new one. To preserve active requests, the deprecated key can still verify already issued tokens. However, after a 10-minute grace period following the signing key rotation, it can't sign new tokens anymore. For more information, see [Manually Rotate Signing Keys of Access Tokens](60-Security/manually-rotate-signing-keys-of-access-tokens-0e38815.md).

    > ### Caution:  
    > In the confirmation popup, there's an option to purge the key. This means that a new *Active* signing key is created and it can be used for signing and verifying access tokens without any grace period. Use this option only in exceptional cases, like when a private key is compromised. This operation might cause active requests to fail, as tokens can't be verified anymore.




</td>
</tr>
</table>

**Related Information**  


[Operations Cockpit](operations-cockpit-ec0fc95.md "The Operations Cockpit is the central control point for operating edge integration cells and allows the Edge Integration Cell administrator to monitor and adjust system configurations and resources.")

[Job Management](job-management-4146fa5.md "Organize and schedule your existing system jobs, and add new jobs manually.")

[Runtime Parameters](runtime-parameters-63c5276.md "Get information about the runtime parameters of the components of your Edge Integration Cell.")

