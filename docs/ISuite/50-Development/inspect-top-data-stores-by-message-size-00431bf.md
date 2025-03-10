<!-- loio00431bf41fe545fdb2a16e45533ec935 -->

# Inspect Top Data Stores by Message Size

Inspect top local and global data stores by their message sizes for a selected time period.

You can choose to display data about global or local data stores by using the *Data Store Visibility* menu. A local data store is accessible only by a single integration flow, while a global data store is accessible by all integration flows deployed on a tenant.

You can also configure the heat map to show either the average message size of the data stores or the maximum size reached at a particular time using the *Message Size* menu.

The heat map displays only data stores identified as having the highest message sizes, sorted top-down by database volume usage. The color shade of a cell reflects the file size level.

Select a cell to get more context information and to get access to the following functions:

-   *Show Messages*

    Navigate to the *Monitor Message Processing* screen for the time period covered by the bar \(see [Monitor Message Processing](monitor-message-processing-314df3f.md)\).

-   *Show Data Stores*

    Navigate to the *Data Stores* tile, *Manage Stores* screen, to show all data stores of the tenant \(see [Managing Data Stores](managing-data-stores-ac39f1d.md)\).

-   *Inspect Data Stores*

    Inspect the usage of the selected data store in more detail.

-   *Zoom Out* and *Zoom In* to extend/reduce the selected time period.

-   *Copy Name To Clipboard*


You can also access the functions below in the heat maps that show **local** data stores:

-   *Show Database Connections*

    Inspect database connection usage \(it can correlate with database consumption by data stores\). For more information, see [Inspect Top Integration Flows by Database Connection Usage](inspect-top-integration-flows-by-database-connection-usage-79c5a05.md).

-   *Show Integration Content*

    Inspect the selected artifact \(see [Manage Integration Content](manage-integration-content-09a7223.md)\).


