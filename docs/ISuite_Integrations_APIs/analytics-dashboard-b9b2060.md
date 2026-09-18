<!-- loiob9b20602b80d4eaf8fa75a6472d24858 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Analytics Dashboard

The analytics dashboard provides powerful and easy-to-use analytical reporting tools to analyze the usage and performance of your APIs and MCP servers. Most of the reports on the analytics dashboard are a graphical representation of data, derived using visually appealing charts. The analytical data is spread across various report pages, namely *Overview*, *Health*, and *Usage*, with each page providing information about key metrics for the selected artifact type.

> ### Note:  
> AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through September 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).



## Accessing the Analytics Dashboard

-   The role collection *PI\_Integration\_Developer* or *PI\_Read\_Only* must be assigned to you.

    -   The *PI\_Integration\_Developer* role:
        -   Gives you access to customize charts for API and MCP server metrics.
        -   Allows you to perform CRUD \(Create, Read, Update and Delete\) operations for charts.

    -   With *PI\_Read\_Only* role, you can only view charts.

-   The MPL log level is set to **Info** or higher.

    > ### Note:  
    > Analytics data availability for API and MCP Server artifacts depends on the Message Processing Log \(MPL\) log level, which determines what data is captured and displayed. The default log level is **Info**. For more information about configuring the log level, see [Log Level Configuration for Analytics](log-level-configuration-for-analytics-5405323.md).


To access the analytics dashboard, log on to SAP Integration Suite and choose *Analyze* from the left navigation pane.



### Different Components on the Analytics Dashboard


<table>
<tr>
<th valign="top">

Component

</th>
<th valign="top">

 

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

Filter

</td>
<td valign="top">

Runtime

</td>
<td valign="top">

Choose the runtime environment whose analytics data you want to view. By default, *Integration Cell* is selected. If you have multiple runtimes configured, use the drop-down to switch between different environments.

</td>
</tr>
<tr>
<td valign="top">

Timezone

</td>
<td valign="top">

The time zone switcher allows you to view analytics data based on different time zones. The default time zone shown is **UTC**. The time zone switcher is available across all the report pages including custom report pages.

</td>
</tr>
<tr>
<td valign="top">

Artifact Type

</td>
<td valign="top">

Choose the type of artifact for which you want to view analytics. You can choose from the following options:

-   **API:** View metrics for API artifacts.

-   **MCP Server:** View metrics for MCP server artifacts.


> ### Note:  
> The availability of the *Artifact Type* field and *MCP Server* selection depends upon the SAP Integration Suite service plan that you use.



</td>
</tr>
<tr>
<td valign="top">

Chart Filters

</td>
<td valign="top">

 

</td>
<td valign="top">

In the *Health* and *Usage* report pages, click <span class="SAP-icons-V5"></span> to view advanced filter menu and options. For the complete list of filter options, see [Applying Chart Filters](applying-chart-filters-a928a03.md).

</td>
</tr>
<tr>
<td valign="top">

Add Custom View

</td>
<td valign="top">



</td>
<td valign="top">

Add custom views and create customized charts for your API or MCP server metrics that are critical to your business. For more information, see [Custom Views and Charts](custom-views-and-charts-900eca5.md).

</td>
</tr>
<tr>
<td valign="top">

Launch Assistant

</td>
<td valign="top">



</td>
<td valign="top">

The **Conversational Analytics** feature provides AI-powered insights into API usage and performance through natural language interaction. Once enabled, you can use the AI Assistant to analyze API call patterns, response times, and usage trends. For more information, see [Analyze APIs with AI Assistance](analyze-apis-with-ai-assistance-724666b.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Report Pages

</td>
<td valign="top">

Overview

</td>
<td valign="top">

The *Overview* page provides a concise report about important and key metrics for your APIs and MCP servers. See [API Artifact Charts](api-artifact-charts-05fe5c0.md) and [MCP Server Charts](mcp-server-charts-c2f3acc.md).

</td>
</tr>
<tr>
<td valign="top">

Health

</td>
<td valign="top">

The *Health* page provides reports about key metrics related to the performance of your APIs and MCP servers. See [API Artifact Charts](api-artifact-charts-05fe5c0.md) and [MCP Server Charts](mcp-server-charts-c2f3acc.md).

</td>
</tr>
<tr>
<td valign="top">

Usage

</td>
<td valign="top">

The *Usage* report page provides reports on key metrics related to user engagement for your APIs and MCP servers. See [API Artifact Charts](api-artifact-charts-05fe5c0.md) and [MCP Server Charts](mcp-server-charts-c2f3acc.md).

</td>
</tr>
<tr>
<td valign="top">

Anomalies

</td>
<td valign="top">

**Anomaly Detection** is an AI-based feature that involves the identification of patterns or data points that deviate significantly from normal behavior or expected patterns. This feature allows you to proactively identify and respond to unusual patterns or deviations in API traffic, thereby ensuring the security, reliability, and optimal performance of APIs. For more information, see [Anomaly Detection](anomaly-detection-7a4fe7d.md).

</td>
</tr>
<tr>
<td valign="top">

Predictions

</td>
<td valign="top">

**Predictions** is an AI-based feature that can forecast future API call volumes based on past call data. With this feature, you can identify trends in API traffic and view predictions for upcoming API call volumes. For more information, see [Predictions](predictions-823bcd7.md).

</td>
</tr>
<tr>
<td valign="top">

Date-Range Selector

</td>
<td valign="top">

 

</td>
<td valign="top">

In the *Health* and *Usage* report pages, there is a date-range selector. This date-range selector lets you set the time period for which you want to analyze the reports. To set a new time period, click and drag the arrow on the date-range selector.

At the top-right corner of the date-range selector, there is a small action bar with options to hide the date-range selector and refresh the reports.

Click <span class="SAP-icons-V5"></span> to hide or unhide the date-range selector.

Click <span class="SAP-icons-V5"></span> to refresh the reports with latest data from API calls.

While viewing your reports on the *Health* and *Usage* page, you can choose to keep the date-range selector always visible. You can do so by clicking on the :pushpin: icon available below the date-range selector.

</td>
</tr>
<tr>
<td valign="top">

Action Bar

</td>
<td valign="top">

 

</td>
<td valign="top">

The action bar appears at the top of each report that contains graphical data. The controls on the action bar allow you to act on the graphical data. Using these controls, you can switch between graphical view and tabular view, and switch between different chart types.

Click <span class="SAP-icons-V5"></span> to hide and unhide legends for a graph.

Click <span class="SAP-icons-V5"></span> <span class="SAP-icons-V5"></span>to view enlarged and diminished image of a graph.

Click <span class="SAP-icons-V5"></span> to switch between full screen view and default screen view.

Click <span class="SAP-icons-V5"></span> to select a different chart type. You can select between pie charts, line charts, bar charts, donut charts, or heatmaps. Note that not all chart types might be supported for a specific report.

Click <span class="SAP-icons-V5"></span> to switch between a tabular view and graphical view of a report.

</td>
</tr>
</table>

> ### Note:  
> The values on the chart for a particular dimension are shown only up to a certain threshold. Any values beyond this threshold are grouped together and labelled as **Others**. By default, the threshold value for the charts is set to **25**. To modify the threshold value, create a support ticket. For instructions, see [Request to Modify Threshold Value for Charts](request-to-modify-threshold-value-for-charts-b55f89d.md).

> ### Note:  
> The data retention period for all report types available in the analytics dashboard is 6 months. That is, the analytics dashboard stores and retains data only for a period of 6 months. After the retention period, the data is purged.

