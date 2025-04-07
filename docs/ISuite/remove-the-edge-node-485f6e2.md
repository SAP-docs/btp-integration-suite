<!-- loio485f6e2677814887924ac977bf2bd468 -->

# Remove the Edge Node

Learn how to remove a complete Edge Node with all associated solution deployments.



## Procedure

1.  Open the *Edge Lifecycle Management* UI.

2.  Go to the *Edge Nodes* tab.

3.  Select the Edge Node that you want to remove.

4.  Choose *Remove*.




<a name="loio485f6e2677814887924ac977bf2bd468__result_s3t_3bg_fvb"/>

## Results

By removing an Edge Node, all solution deployments are deleted automatically.

As a result, all resources on the Kubernetes cluster are cleaned up.

> ### Note:  
> If you are using an external database or Redis instance, you need to manually clean up the Edge Integration Cell data by deleting the database schema or Redis instance.

