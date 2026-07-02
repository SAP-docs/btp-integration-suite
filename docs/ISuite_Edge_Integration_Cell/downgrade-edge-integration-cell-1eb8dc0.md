<!-- loio1eb8dc05342b413e99273c2c83920faf -->

# Downgrade Edge Integration Cell

Use the downgrade capability to revert the Edge Integration Cell \(EIC\) solution to an earlier installed software version or patch level.



## Prerequisites

-   You must have the Edge Integration Cell Administrator role assigned in SAP Integration Suite.

-   The target version you wish to downgrade to must be a version that was previously successfully installed on the EIC instance, or a patch version thereof.

-   The EIC instance must be in a healthy or partially degraded state, a completely unresponsive instance may require the rollback procedure instead. For more information, see [Rollback Edge Integration Cell Solution](rollback-edge-integration-cell-solution-9eec21b.md).

-   Your current Kubernetes version must be supported by both the currently deployed and the target versions of the EIC.

-   Ensure that any active integration flows and runtime artifacts are reviewed before initiating a downgrade, as version-specific configurations may be affected.

-   It is recommended to create a system backup before triggering a downgrade, so that a rollback can be performed if the downgrade itself encounters errors.

-   Verify that the Kubernetes cluster hosting the EIC has sufficient resources to support the downgrade operation.




## Context

This downgrade option is introduced to address scenarios where a successful software update is followed by regression in the runtime scenarios cause unexpected issues, instability, or incompatibility in the runtime environment and where a full downgrade is either not feasible or not desired. It performs a controlled, in-place version downgrade, allowing the system to transition back to a known stable version while preserving the current runtime state where possible.



## Procedure

1.  Open Edge Lifecycle Management.

2.  Go to the *Edge Nodes* tab.

3.  Choose the Edge Node where you want to downgrade the version.

4.  From the *Operations* context menu, select the Edge Integration Cell solution, and choose *Downgrade*. The system displays a dialog box.

    The Edge Integration Cell Services solution cannot be downgraded.

5.  In the dialog box, choose your target downgrade version, review the solution properties, and choose *Downgrade*. For a description of these properties, see [Deploy the Edge Integration Cell Solution](deploy-the-edge-integration-cell-solution-ab81b84.md).

    > ### Note:  
    > The system only supports a sequential downgrade path, meaning you can revert exclusively to exactly one version lower than the current deployment. Downgrading across multiple major versions in a single operation is not supported.

    > ### Remember:  
    > SAP supports compatibility only for the **latest Edge Integration Cell version** and its **immediate predecessor** \(e.g., if version 8.10 is current, only 8.10 and 8.9 are supported\). Older versions are considered outdated.
    > 
    > Operating on an outdated version has strict consequences:
    > 
    > -   **Blocked:** You cannot deploy or undeploy any content.
    > -   **Allowed:** Previously deployed content continues to process without restrictions.
    > 
    > If the EIC instance has been freshly installed and has not yet been upgraded to a subsequent version, there is no prior version available to downgrade to. Although the downgrade option may still appear, initiating a downgrade in this state is not supported and will not succeed. Ensure that at least one successful upgrade has been performed before attempting a downgrade.




## Results

-   The Edge Integration Cell solution is downgraded based on the Helm charts of the previous version.
-   If the downgrade fails, you can choose one of the following recovery options:
    -   **Retry:** Attempt the downgrade again.

        > ### Caution:  
        > If the failure persists after a retry, you cannot roll back to the last successfully deployed version.

    -   **Rollback:** Revert to the last successfully deployed version. For more information, see [Rollback Edge Integration Cell Solution](rollback-edge-integration-cell-solution-9eec21b.md).


<a name="concept_o1b_qhg_qjc"/>

<!-- concept\_o1b\_qhg\_qjc -->

## Limitations

-   **Data and configuration impact**: Certain configuration changes or data migrations applied during the upgrade may not be automatically reversed. Administrators should manually review and, if necessary, revert any configuration changes that were applied as part of the upgrade.

-   **No guarantee of full state restoration**: Unlike the rollback capability, the downgrade does not restore a prior system snapshot. Runtime state, persisted data, and any changes made after the upgrade are not automatically reverted.

-   **One downgrade at a time**: Only one downgrade operation can be in progress at a time per EIC instance. Concurrent downgrade operations are not supported.

-   **Post-downgrade re-upgrade**: After a successful downgrade, re-upgrading to the same or a newer version is possible, but the upgrade process must be re-initiated manually.

-   **Edge Integration Cell Services exception**: The Edge Integration Cell Services solution cannot be downgraded.


