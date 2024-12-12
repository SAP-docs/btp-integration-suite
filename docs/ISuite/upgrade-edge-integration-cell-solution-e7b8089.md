<!-- loioe7b80890d98e4a03a446019037112960 -->

# Upgrade Edge Integration Cell Solution

Learn how to upgrade the Edge Integration Cell solution.



## Context

If an upgradable version is available, it's visible in the Edge Lifecycle Management UI.

Service keys for connectivity to SAP Integration Suite and BTP services are rotated automatically during the upgrade of a minor version.



## Procedure

1.  Open the *Edge Lifecycle Management* UI.

2.  Go to the *Edge Nodes* tab.

3.  Choose the Edge Node where you want to upgrade the version.

4.  From the *Operations* context menu, select the Edge Integration Cell solution, and choose *Upgrade*.

    The system displays a dialog box where you choose the upgrade version, and provides solution properties. For a description of solution properties, refer to [Deploy the Edge Integration Cell Solution](deploy-the-edge-integration-cell-solution-ab81b84.md).

    > ### Note:  
    > If the new Edge Integration Cell version requires newer Edge Integration Cell Services or a newer Istio version, then both are upgraded automatically before the upgrade of Edge Integration Cell starts.
    > 
    > Upgrading dependent solutions only, such as Edge Integration Cell Service or Istio, is possible and follows the same process.

5.  Click *Upgrade*.




<a name="loioe7b80890d98e4a03a446019037112960__result_kj3_zmk_2vb"/>

## Results

-   The solution is upgraded based on helm charts of the new version.

    > ### Note:  
    > Upgrading Istio can lead to traffic disruption during the upgrade process.

-   If the upgrade of the Edge Integration Cell solution fails, you can choose to:
    -   Retry the upgrade but be aware that if failure persists after a retry you can't rollback to the last successfully deployed version.
    -   Rollback to the last successfully deployed version. For more information see [Rollback Edge Integration Cell Solution](rollback-edge-integration-cell-solution-9eec21b.md).


