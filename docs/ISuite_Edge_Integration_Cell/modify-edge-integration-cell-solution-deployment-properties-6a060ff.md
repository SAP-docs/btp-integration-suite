<!-- loio6a060ffd345a4c4ab545d5c31cb24119 -->

# Modify Edge Integration Cell Solution Deployment Properties



## Context

Use Edge Lifecycle Management \(Edge LM\) to modify the solution deployment properties of Edge Integration Cell solution.

During the upgrade the service keys for connectivity with SAP Integration Suite and BTP services are rotated as needed. For key rotation, the `modify` operation can be used even without changing specific solution properties.

> ### Note:  
> When you modify the Istio solution property for *Client IP Preservation*, it is necessary to subsequently modify the Edge Integration Cell solution. This ensures that the changes are reflected in the Policy Engine.

To modify the Edge Integration Cell deployment solution properties, proceed as follows:



## Procedure

1.  Open the *Edge Lifecyle Management* UI.

2.  Go to the *Edges Nodes* tab.

3.  Select the Edge Node where you want to update the solution properties.

4.  Select the solution where you want to update the solution properties.

5.  From the *Operations* context menu, choose *Modify Configuration*.

    The system opens a dialog box where you can update solution deployment properties.

6.  Choose *Modify*.




<a name="loio6a060ffd345a4c4ab545d5c31cb24119__result_fjz_kyc_2vb"/>

## Results

-   The solution is updated based on modified helm charts.
-   If the modify configuration operation fails, you can rollback the solution to its last successfully deployed version. For more details, see [Rollback Edge Integration Cell Solution](rollback-edge-integration-cell-solution-9eec21b.md).

