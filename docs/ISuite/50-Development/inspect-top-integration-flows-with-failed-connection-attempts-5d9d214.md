<!-- loio5d9d21400fd54373b934bce11288b719 -->

# Inspect Top Integration Flows with Failed Connection Attempts

Inspect the integration flows that requested a database connection but for which no free database connection was available in the selected time period.

> ### Note:  
> This section only shows content if the time filter is set so that in the associated time period critical load situations are associated with at least one integration flow.

Integration flows are sorted from top to bottom according to the number of unsuccessful attempts to request a database connection \(divided by the absolute number of attempts\).

The number of unsuccessful attempts to request a database connection during the selected time period is indicated by the cell color \(from green for a low number, up to red for a critical number of unsuccessful attempts\).

Choose a cell to display the absolute number of unsuccessful attempts to get a database connection for an integration flow \(*Unavailable Count* number\). You also get access to the following functions for the selected integration flow \(results are filtered according to the setting of the *Time* parameter\):

-   *Show Messages*

    Navigate to the *Monitor Message Processing* screen for the time period covered by the bar \(see [Monitor Message Processing](monitor-message-processing-314df3f.md)\).

-   *Show Integration Content*

    Navigate to the *Manage Integration Content* screen for the related integration flow \(see [Manage Integration Content](manage-integration-content-09a7223.md)\).

-   *Inspect Integration Flow*

    Inspect the database connection usage of the selected integration flow \(see: [Inspect Resource Consumption for Individual Integration Flow](inspect-resource-consumption-for-individual-integration-flow-3380bd6.md)\).

-   *Zoom Out* and *Zoom In* to extend/reduce the selected time period.

-   *Copy Name to Clipboard*


