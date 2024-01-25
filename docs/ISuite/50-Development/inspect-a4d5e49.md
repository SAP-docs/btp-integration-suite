<!-- loioa4d5e49e24f54a7a81b31eb07f1714ac -->

# Inspect

Inspect the usage of integration resources caused by your active integration flows.

Each SAP Integration Suite tenant comes with certain physical resources that are consumed by integration flows at runtime. Examples of such integration resources are the available database connections.

You can inspect consumption of integration resources, identify those integration flows that contribute significantly to integration-resource exhaustion, and perform steps to resolve critical situations. Based on the insights, you can, for example, optimize integration flow design to overcome integration resource bottlenecks.

> ### Note:  
> To use this feature, role collection `MonitoringDataRead` needs to be assigned to your user \(see [Tasks and Permissions](../60-Security/tasks-and-permissions-556d557.md)\).



<a name="loioa4d5e49e24f54a7a81b31eb07f1714ac__section_a4l_sct_2xb"/>

## Inspect Database Resources

Inspect database resource usage caused by your active integration flows.

Click *Inspect* to inspect the usage of integration resources associated with the tenant database and with the database connection pool.

-   Using the *Connections* tile, you can inspect resource usage of the database connections caused by integration flows.

    See: [Inspect Database Connection Usage](inspect-database-connection-usage-567eb42.md)

-   Using the *Data Store* tile, you can inspect resource usage of the tenant database caused by integration flows using data store operations steps.

    See: [Inspect Data Store Usage](inspect-data-store-usage-fcc08f6.md)

-   Using the *Transactions* tile, you can inspect resource usage of the database transactions caused by integration flows.

    See: [Inspect Database Transaction Usage](inspect-database-transaction-usage-6736a37.md)

-   Using the *Monitoring Storage* tile, you can inspect resource usage of the monitoring database storage caused by integration flows.

    See: [Inspect Monitoring Storage Usage](inspect-monitoring-storage-usage-216dc43.md)




<a name="loioa4d5e49e24f54a7a81b31eb07f1714ac__section_wjn_jlw_hzb"/>

## Inspect System Resources

Inspect system resource usage caused by your active integration flows.

Using the *Memory* tile, you can inspect resource usage of system memory caused by integration flows.

See: [Inspect System Memory Usage](inspect-system-memory-usage-e9617dd.md)

