<!-- loio2b771d24c8ad4e629c826a9e0897bd6c -->

# Delete the Edge Integration Cell Solution

Learn how to delete Edge Integration Cell solution from an Edge Node.



## Procedure

1.  Open the **Edge Lifecyle Management** UI.

2.  Go to the *Edge Nodes*tab.

3.  Select the Edge Node where you want to delete the solution deployment.

4.  From the *Operations* context menu, choose *Delete*.

5.  In the warning dialog that appears, choose *Yes*.




<a name="loio2b771d24c8ad4e629c826a9e0897bd6c__result_xdl_czf_fvb"/>

## Results

The Edge Integration Cell solution is deleted first. After completion, the dependent `Istio` solution is deleted automatically.

The runtime location in SAP Integration Suite is removed automatically.

> ### Note:  
> If you are using an external database or Redis instance, you need to manually clean up the Edge Integration Cell data by deleting the database schema or Redis instance.

