<!-- loio2a2e1f2e6ebe4264a4debddb92d890b2 -->

# Inspect Integration Flows By System Memory Usage

Inspect relative memory allocation per integration flow for a given time period \(as selected with the *Time* parameter\).

> ### Tip:  
> Memory is continuously allocated for processing messages, and it is automatically reclaimed by garbage collection when it’s no longer used. The chart shows memory allocation. It allows you to do a relative comparison of integration flows with regard to memory consumption.

Only those integration flows that are identified as top consumers of memory in terms of allocation are shown \(sorted top-down by average usage\).

The color shade of a cell reflects the level of memory allocation. The darkest shade reflects the highest usage observed during the selected time period.

Click a cell to display the degree of memory allocation and to access one of the following functions for the selected integration flow \(results are filtered according to the setting of the *Time* parameter\):

-   *Show Messages*

    Navigate to the *Monitor Message Processing* screen for the time period covered by the bar \(see [Monitor Message Processing](monitor-message-processing-314df3f.md)\).

-   *Show Integration Content*

    Navigate to the *Manage Integration Content* screen for the related integration flow \(see [Manage Integration Content](manage-integration-content-09a7223.md)\).

-   *Copy Name to Clipboard* 

    Copy the integration flow name to the clipboard. This is useful when you use other screens where you can paste the name for filtering by integration flow.

-   *Copy Flow Step to Clipboard*

    Copy the identifier of the integration flow step that was detected as main consumer of memory to the clipboard. After navigating to the integration flow designer via the function *Show Integration Content* you can use this identifier for finding the integration flow step within the integration flow.

    > ### Tip:  
    > On the *Manage Integration Content* screen, you can select *View Deployed Artifact* to navigate to the integration flow editor for the deployed artifact. Alternatively, you can select *Navigate to Artifact Editor* to navigate to the integration flow editor in the *Design* section.


