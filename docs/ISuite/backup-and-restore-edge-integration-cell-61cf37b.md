<!-- loio61cf37b704b3466f990696472f6fdc27 -->

# Backup and Restore Edge Integration Cell

To minimize the risk of data loss, backup of business data needs to be performed regularly. If there are errors, restore and recovery to a consistent state is required.

Edge Integration Cell stores configuration in the cloud where the data are secured as part of SAP Integration Suite services. Configuration data are automatically synchronized to Edge Integration Cell.



<a name="loio61cf37b704b3466f990696472f6fdc27__section_gw1_wvh_yyb"/>

## PostgreSQL Database and Redis Data Store

Runtime and monitoring data are stored in PostgreSQL database and Redis data store on the edge. For production environments, these services are deployed outside of Edge Integration Cell. Hence, backup and recovery of these stores is part of the external services provisioning. For more information about external services persistence options, see [3247839](https://me.sap.com/notes/3247839).

> ### Caution:  
> Restoring PostgreSQL database or Redis data store leads to service interruption for Edge Integration Cell.

> ### Note:  
> In some environments, such as Azure or AWS, when you use platform provided services, a restore may result in a new PostgreSQL DB or Redis instance. In these cases, you can change the connection properties using Edge Lifecycle Management and there's no need to follow the manual procedures described below. For more information, see [Modify Edge Integration Cell Solution Deployment Properties](modify-edge-integration-cell-solution-deployment-properties-6a060ff.md).



### Restore PostgreSQL Procedure

-   Stop Edge Integration Cell components.

    -   edc

    -   edge-api

    -   mdc

    -   worker


    Components can be stopped using: `kubectl scale deployment <name> --replicas=0 -n edge-icell`.

-   Restore PostgreSQL database.

-   Start Edge Integration Cell components.

    -   edc

    -   edge-api

    -   mdc

    -   worker


    Components can be started using: `kubectl scale deployment <name> --replicas=<n> -n edge-icell`


> ### Caution:  
> If possible, perform a complete database recovery. A point-in-time recovery leads to data loss!



### Restore Redis Procedure

-   Stop Edge Integration Cell component `policyengine`.

    `policyengine` can be stopped using : `kubectl scale deployment policyengine --replicas=0 -n edge-icell`.

-   Restore PostgreSQL database.

-   Start Edge Integration Cell component `policyengine`.

    `policyengine` can be started using : `kubectl scale deployment policyengine --replicas=<n> -n edge-icell`.


> ### Caution:  
> Depending on the persistence type, only a snapshot might be restored. Restoring only a snapshot can lead to data loss.



### Built-In Service Procedure

For non-production environments, the built-in deployment options for PostgreSQL database and Redis data store can be used. Currently, backup and restore aren't supported for these built-in services.



<a name="loio61cf37b704b3466f990696472f6fdc27__section_ljj_zzh_yyb"/>

## Message Service Persistence

For message service persistence, replication is used to secure persistent data, instead of using backup and restore procedures. Replication is set up as part of the High Availability enablement.

