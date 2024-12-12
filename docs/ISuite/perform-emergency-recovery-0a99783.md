<!-- loio0a99783d662d45b28142129854aae518 -->

# Perform Emergency Recovery



## Context

Perform an emergency recovery in cases where the Edge Integration Cell needs to be restored from scratch, such as if the Kubernetes \(K8s\) cluster environment was lost.

As a foundational step, ensure you have Kubernetes backups available to facilitate the restoration of the K8s environment. Typically, this involves restoring etcd. Please refer to the backup and recovery procedures specific to your underlying platform, whether it be Azure AKS, Amazon EKS, SUSE Rancher, or Red Hat OpenShift.

> ### Note:  
> Create a K8s backup always after you upgrade or modify a solution \(Edge LM or Edge Integration Cell\) to reflect the latest K8s environment state.

> ### Caution:  
> An emergency recovery cannot recover Message Service data as Solace does not support persistent volume recovery. Messages stored in JMS queues or temporarily stored MPL events will be lost.



## Procedure

1.  Start with a restore of the K8s environment. As a result, all Edge LM and Edge Integration Cell K8s resources, such as Deployments, StatefulSets, Custom Resources, ConfigMaps, Secrets, etc., should be restored.

2.  Check the state of restored K8s resources to verify that all required pods are available. Open the Edge LM UI and check the status of Edge Nodes and solutions. This may require a recovery of the Edge Node. For more information, see [Performing Emergency Operations on an Edge Node.](https://help.sap.com/docs/EDGE_LIFECYCLE_MANAGEMENT/9d5719aae5aa4d479083253ba79c23f9/94b35056bbf94a73a6716a8d194a78d6.html)

3.  If needed, restore and recover the external databases, such as PostgreSQL and Redis.

4.  As the Message Service does not support restore and recovery of persistent volumes, you need to recreate the Message Service. To do so, perform the following steps:

    -   To delete StatefulSet, execute the following command: `kubectl -n edge-icell-services delete sts ssb-solace`.


    -   To delete Persistent Volume Claims \(data-ssb-solace-1, data-ssb-solace-2 exist only for an HA setup\), execute the following commands:
        -   `kubectl -n edge-icell-services delete pvc data-ssb-solace-0`
        -   `kubectl -n edge-icell-services delete pvc data-ssb-solace-1`
        -   `kubectl -n edge-icell-services delete pvc data-ssb-solace-2`


    -   To edit custom resource, perform the following command: `kubectl -n edge-icell-services edit solacesoftwarebroker solace`. This opens an editor showing the custom resource definition in the section spec. In the spec section, look for the field `statusRevisionCount`. If the `statusRevisionCount` field exists, increase its value; otherwise set it to 1. Save the changes and exit the editor.

    -   To restart the deployment, execute the following commands:
        -   `kubectl -n edge-icell rollout restart deploy solops`
        -   `kubectl -n edge-icell rollout restart deploy mdc`
        -   `kubectl -n edge-icell rollout restart deploy worker`


5.  To cleanup the artifact cache, connect to the PostgreSQL database and execute the following SQL statements:

    -   `delete from edc_artifact_entity;`
    -   `delete from edc_queue_artifact_mapping_info_entity;`

    After recreating the Message Service, all queues for Integration Flows using JMS must be recreated. Therefore, the local artifact cache should be cleaned up. This enforces artifact synchronization from the Cloud, recreates the artifact cache and JMS queues, and ensures a consistent state.

6.  To restart the Edge Dploy Controller, execute the following command: `kubectl -n edge-icell rollout restart deploy edc`.


