<!-- loiofb103944fc9340efae59631bdb7b145e -->

# Create Heap and Thread Dumps

Learn how to create heap and thread dumps.



## Context

You can create heap and thread dumps using the `jvmmon` SAPJVM tool.



## Procedure

1.  To identify the pod for which you want to trigger a dump, use `kubectl get pods -n edge-icell`.

2.  To connect to a worker pod, use `kubectl exec -it <pod name> -n edge-icell -- bash`.

3.  Run `jvmmon`.

    -   To create a thread dump, use `dump stacktrace`.

        Thread dumps are written to directory `/opt/karaf/ or /var/lib/worker/data` \(if external storage is enabled\).

    -   To create a heap dump, use `dump heap`.

        Heap dumps are stored in directory `/opt/karaf or /var/lib/worker/data` \(if external storage is enabled\).

        > ### Note:  
        > If external storage is enabled, the dumps for all pods are available under `/var/lib/worker/dumps` on the worker pods.

        You can copy heap dump files using `kubectl cp <pod name>:/opt/karaf/<file name> <dest file name>`.



