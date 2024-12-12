<!-- loio9176ad7c017643eab79e7460f0f8fb42 -->

# Fix Edge Integration Cell Upgrade Issues

Check and fix the Edge Integration Cell solution upgrade issues.



## Context

During solution upgrade, you encounter the following error:

`Action [Create or Update Helm Custom Resource (Solace)] failed: Custom Resource from kind [HelmRelease] reached FAILED state when performing [UpdateFailed], due to [post-upgrade hook failed, lastHookErrMsg: 'Failed status for monitored CR 'edge-icell-services/solace' with group/version/kind 'xbem.sap.com/v1/SolaceSoftwareBroker'']`

To resolve the upgrade error, perform the following steps:



## Procedure

1.  To check the custom resource status, enter the command `kubectl get SolaceSoftwareBroker solace -n edge-icell-services` in the kubectl tool..


    <table>
    <tr>
    <th valign="top">

    Custom Resource Status
    
    </th>
    <th valign="top">

    Action
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    If the custom resource status is **Pending**:
    
    </td>
    <td valign="top">
    
    Enter the command `kubectl get pod -n edge-icell-services` in the kubectl tool.

    Check which of the `ssb-solace-<n>` pods show status **Pending** or status **Running** with an incomplete **READY count**, for example 2/3 instead of 3/3. For these pods, enter the command `kubectl describe pod <name> -n edge-icell-services` in the kubectl tool.

    Check for error events and try to fix the error causes, or open a ticket on component BC-CP-IS-EDG-DPL.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    If the custom resource status is **Failed**:
    
    </td>
    <td valign="top">
    
    Enter the command `kubectl get pod -n edge-icell-services` in the kubectl tool.

    Confirm that `ssb-solace-<n>`pods show status **Running** and **READY count** 3/3.

    If this is not the case, open a ticket on component BC-CP-IS-EDG-DPL

    To trigger a reconcile of the custom resource status, enter the command: `kubectl edit SolaceSoftwareBroker solace -n edge-icell-services` in the kubectl tool. This opens an editor showing the custom resource definition.

    In the section spec, look for the field `statusRevisionCount`.

    > ### Sample Code:  
    > ```
    > spec:
    >   ...
    >   pullSecret: edgelm-image-pull-secret
    >   statusRevisionCount: 1
    > 
    > ```

    Increase the value for `statusRevisionCount`.

    Save the change and exit the command tool.

    If the spec section doesn't contain the `statusRevisionCount` field, add it in a new line and set the value to 1 \(keep the indentation\). The change triggers a reconcile.

    You can then check the status again as described in step 1.
    
    </td>
    </tr>
    </table>
    
2.  Trigger the upgrade retry in the Edge Lifecycle Management UI.

    If the upgrade still fails, open a ticket on component **BC-CP-IS-EDG-DPL**.


