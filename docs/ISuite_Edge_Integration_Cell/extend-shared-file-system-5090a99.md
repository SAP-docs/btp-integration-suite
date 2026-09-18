<!-- loio5090a99f3a8e4903a1bf3ddc2ce5ab68 -->

# Extend Shared File System

Extend the shared file system used to preserve traces or dumps.



## Prerequisites

To extend the shared file system, your active storage class must have `allowVolumeExpansion` enabled for its underlying persistent volume.



## Context

During initial deployment, a shared file system can be enabled to preserve traces or dumps. The resulting persistent volume has a default size of 50Gi. Use this procedure to increase the file system size beyond the default.

> ### Tip:  
> To clean up data before extending the file system, configure a Cleanup Diagnostic Data job. For more information, see [Job Management](job-management-4146fa5.md).



## Procedure

1.  Create a file named `shared-config.yaml` in your editor and paste the following template:

    > ### Sample Code:  
    > ```
    > apiVersion: v1
    > kind: ConfigMap
    > metadata:
    >   name: shared-custom-config
    >   namespace: edge-icell
    > data:
    >   STORAGE_SIZE: <value>
    > ```

2.  Replace <value\> with your desired storage size and save the file.

    > ### Note:  
    > The value must be greater than the default 50Gi and strictly larger than your current size. Persistent volumes can only be expanded, not shrunk.

3.  Create the ConfigMap by executing the following command: `kubectl apply -f shared-config.yaml`.

4.  Open the *Edge Lifecycle Management* UI.

5.  Go to the *Edge Nodes* tab.

6.  Select the Edge Node where you want to extend the shared file system.

7.  Select the Edge Integration Cell solution.

8.  From the *Operations* context menu, choose *Modify Configuration*. A dialog box opens. You do not need to update any solution deployment properties here.

9.  Choose *Modify*.




## Results

The shared file system is extended to the newly specified size.

