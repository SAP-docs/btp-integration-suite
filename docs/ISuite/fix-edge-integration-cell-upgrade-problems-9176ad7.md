<!-- loio9176ad7c017643eab79e7460f0f8fb42 -->

# Fix Edge integration Cell Upgrade Problems

Check and fix solution upgrade issues.



## Context

During solution upgrade, you encounter the following error:

Action \[Create or Update Helm Custom Resource \(Solace, Edge Integration Cell Services\)\] failed:

Custom Resource such as `HelmRelease]` reached FAILED state, when performing `[UpdateFailed]`, due to `[failed to update release: post-upgrade hooks failed: 1 error occurred: * job failed: BackoffLimitExceeded]`

To resolve the upgrade error, perform the following steps:



## Procedure

1.  Check custom resource status.

    To check the status , use the kubectl tool to enter the command: `kubectl get SolaceSoftwareBroker solace -n edge-icell-services`.

2.  Custom resource status is **pending**.

    If custom resource status is **pending**, enter the command `kubectl get pod -n edge-icell-services`. Check which `ssb-solace-<n>`pods show status **Pending** or **Running** with incomplete **READY count**, e.g. 2/3 instead of 3/3. For these pods, enter the command `kubectl describe pod <name> -n edge-icell-services` in the kubectl tool.

    Check for error events and try to fix the error causes, or open a ticket on component BC-CP-IS-EDG-DPL.

3.  If custom resource status is **failed**.

    If custom resource status is **failed**, enter the command `kubectl get pod -n edge-icell-services`. Confirm that `ssb-solace-<n>`pods show status **Running**and **READY count** 3/3. If not, open a ticket on component BC-CP-IS-EDG-DPL.

    Trigger a reconcile of the custom resource status by entering the command: `kubectl edit SolaceSoftwareBroker solace -n edge-icell-services`. This opens an editor showing the custom resource definition. in the section spec, look for the field `statusRevisionCount`.

    > ### Sample Code:  
    > ```
    > spec:
    >   ...
    >   pullSecret: edgelm-image-pull-secret
    >   statusRevisionCount: 1
    > 
    > ```

    Increase the value for `statusRevisionCount`, save and exit.

    If the spec section doesn't contain the field, add it in a new line and set the value to 1 \(keep the indentation\). The change triggers a reconcile.

    You can then check the status again as described in step 1.

4.  Retry the upgrade.

    trigger the *Retry* in the Edge Lifecycle Management UI.

    If the upgrade still fails, open a ticket on component **BC-CP-IS-EDG-DPL**.


