<!-- loioa4d5e49e24f54a7a81b31eb07f1714ac -->

# Inspect

Inspect the usage of integration resources caused by your active integration flows.

Each SAP Integration Suite tenant comes with certain physical resources that are consumed by integration flows at runtime. Examples of such integration resources are the available database connections.

*Inspect* allows you to inspect the consumption of integration resources, identify those integration flows that contribute significantly to integration-resource exhaustion, and perform steps to resolve critical situations. Based on the insights, you can, for example, optimize integration flow design to overcome integration resource bottlenecks.

> ### Note:  
> To use this feature, role collection `MonitoringDataRead` needs to be assigned to your user \(see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md)\).

The *Inspect* overview page displays various tiles that represent the consumption levels of different resources in your tenant. Each tile shows the overall consumption of a resource over the past 24 hours.

Watch the following video to learn how to use *Inspect* and for an overview of a typical workflow. The video uses database connection usage as an example, but the workflow also applies to any other resources.



<a name="loioa4d5e49e24f54a7a81b31eb07f1714ac__section_a4l_sct_2xb"/>

## Inspect Database Resources

Inspect the usage of integration resources associated with the tenant database and with the database connection pool.

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

-   Using the *Memory* tile, you can inspect resource usage of system memory caused by integration flows.

    See: [Inspect System Memory Usage](inspect-system-memory-usage-e9617dd.md)

-   Using the *Temporary Storage* tile, you can inspect the storage usage of temporary files.

    See: [Inspect Temporary Storage](inspect-temporary-storage-7cdfaa7.md)




<a name="loioa4d5e49e24f54a7a81b31eb07f1714ac__section_jhm_m1k_dcc"/>

## Inspect Content Resources

Inspect content resource usage caused by your integration artifacts.

-   Using the *Content Size* tile, you can inspect the file size that integration artifacts occupy.

    See: [Inspect Content Size](inspect-content-size-f72b7ff.md)

-   Using the *Integration Flows* tile, you can inspect the integration flows with the highest resource consumption.

    See: [Inspect Top Consuming Integration Flows](inspect-top-consuming-integration-flows-c8fd522.md)


> ### Tip:  
> When resource consumption becomes critical, a *Recommendations* button becomes available. You can choose this button to receive tailored suggestions and assistance. These recommendations help resolve potential issues when usage levels reach warning or critical stages.

