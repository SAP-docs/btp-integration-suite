<!-- loioda4af34080264dd4867f31ac266400d0 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Analyze APIs and MCP Servers

SAP Integration Suite provides comprehensive analytics capabilities to understand consumption and performance patterns across APIs and MCP servers.

> ### Note:  
> Availability of the MCP Server feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



<a name="loioda4af34080264dd4867f31ac266400d0__section_hwr_bkb_kfc"/>

## Prerequisites

-   You have the *PI\_Integration\_Developer* or *PI\_Read\_Only* role assigned to you.

-   The *PI\_Integration\_Developer* role:

    -   Gives you access to customize charts for API and MCP server metrics.
    -   Allows you to perform CRUD \(Create, Read, Update and Delete\) operations for charts.

    With *PI\_Read\_Only* role, you can only view charts.

-   Analytics data availability depends on Message Processing Log \(MPL\) log level configuration. For more information about monitoring and log configuration, see [Monitor APIs and MCP Servers](monitor-apis-and-mcp-servers-399b6c6.md).




<a name="loioda4af34080264dd4867f31ac266400d0__section_c5y_rwr_hfc"/>

## Analytics Dashboard

The Analytics dashboard provides powerful and easy-to-use analytical reporting tools to analyze the usage and performance of your APIs and MCP servers.

Most of the reports on the analytics dashboard are a graphical representation of data, derived using visually appealing charts. The analytical data is spread across various report pages namely Overview, Health, and Usage, with each page providing information about key API and MCP server metrics.

To access the analytics dashboard, perform the steps below:

1.  Log on to the **SAP Integration Suite**.
2.  Choose *Analyze* from the left navigation pane.



<a name="loioda4af34080264dd4867f31ac266400d0__section_esw_yxr_hfc"/>

## Report Pages

In the Analytics dashboard, you access all your reports in report pages. The reports are categorized into report pages namely Overview, Health, and Usage. These report pages provide information about key metrics related to your APIs and MCP server usage and performance.

-   **Runtime:** Select the runtime environment whose analytics data you want to view. By default, *Integration Cell* is selected. If you have multiple runtimes configured, use this drop-down to switch between different environments.

    Based on the runtime selection, the charts in the report pages will be generated and displayed accordingly. The charts that are available for **Integration Cell** runtime are described in the below section.

-   **Timezone:** The time zone switcher allows you to view analytics data based on different time zones. The default time zone shown is **UTC**. The time zone switcher is available across all the report pages including custom report pages.

-   **Artifact Type:** Select the type of artifact for which you want to view analytics. You can choose from the following options:

    -   *API:* View metrics for API artifacts.

    -   *MCP Server:* View metrics for MCP server artifacts. For more information on the MCP server feature, see [Model Context Protocol \(MCP\)](model-context-protocol-mcp-9eb9239.md).


    > ### Note:  
    > The availability of the *Artifact Type* field and *MCP Server* selection depends upon the SAP Integration Suite service plan that you use.


When the artifact type is set to *API*, the following charts and metrics are displayed across the Overview, Health, and Usage pages:



### Overview

At the top of the Overview report page, the following key API metrics are represented in a tile format:

-   **Total API Calls:** Total number of API requests made over a specified period.

-   **API Response Time:** Total time in milliseconds to respond to an API request. This round-trip time includes the API proxy overhead and the target server time.

-   **API Calls via Agents:** Total number of API requests made via agents over a specified period.

-   **Total API Errors:** Total number of errors that occur on the API, plus the errors that occurs on the target server from all the API requests and responses over a specified period.


The rest of the Overview page displays a graphical view of key API metrics, as outlined in the table below:

**Overview**


<table>
<tr>
<th valign="top">

Chart

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Calls

</td>
<td valign="top">

Displays the monthly count of API calls made.

-   *All APIs:* Displays aggregated call data across all configured APIs. This option is selected by default.
-   *Select APIs from the list:* Allows you to filter data for specific APIs using the drop-down menu. When this option is selected, a drop-down becomes active, allowing you to choose one or more specific APIs to view their individual call data.



</td>
</tr>
<tr>
<td valign="top">

Top APIs of the Week

</td>
<td valign="top">

Displays the top 5 APIs of the week based on the number of calls made to each API.

</td>
</tr>
<tr>
<td valign="top">

Top API Products of the Week

</td>
<td valign="top">

Displays the top 5 products of the week based on the number of calls received for each product.

</td>
</tr>
<tr>
<td valign="top">

Top Subscriptions for Applications for the Week

</td>
<td valign="top">

Displays the top 5 subscriptions for applications based on the number of calls made during the week.

</td>
</tr>
<tr>
<td valign="top">

Top Developers of the Week

</td>
<td valign="top">

Displays the top 5 developers of the week based on the number of API calls made.

</td>
</tr>
<tr>
<td valign="top">

APIs for the Week

</td>
<td valign="top">

Displays the daily call frequency for each API, highlighting the most frequently accessed APIs.

</td>
</tr>
<tr>
<td valign="top">

APIs for the Week by Agents vs Applications

</td>
<td valign="top">

Displays the call count via agents vs applications for each API.

</td>
</tr>
<tr>
<td valign="top">

APIs for the Week by MCP Servers

</td>
<td valign="top">

Displays the call count per MCP Server for each API.

</td>
</tr>
<tr>
<td valign="top">

API Products for the Week

</td>
<td valign="top">

Displays the daily call volume for each product, highlighting the top-performing products based on call volume.

</td>
</tr>
<tr>
<td valign="top">

Subscriptions for Applications for the Week

</td>
<td valign="top">

Displays the daily average number of API calls per subscription for applications, highlighting the top applications.

</td>
</tr>
<tr>
<td valign="top">

Developers for the Week

</td>
<td valign="top">

Displays the daily average number of API calls made by each developer, highlighting the most active developers.

</td>
</tr>
<tr>
<td valign="top">

Developer Engagement

</td>
<td valign="top">

Displays the average number of calls made per application by each developer, indicating their level of engagement.

</td>
</tr>
<tr>
<td valign="top">

API Response Time

</td>
<td valign="top">

Displays the average response time, measured in milliseconds, for each API on a daily basis.

</td>
</tr>
<tr>
<td valign="top">

Slowest APIs

</td>
<td valign="top">

Displays the slowest APIs based on the average daily response time.

</td>
</tr>
<tr>
<td valign="top">

Calls per Response Code

</td>
<td valign="top">

Displays the frequency of calls categorized by different response codes.

</td>
</tr>
<tr>
<td valign="top">

API Calls per Response Code

</td>
<td valign="top">

Displays the call count per API grouped by response code.

</td>
</tr>
<tr>
<td valign="top">

Top Failing APIs

</td>
<td valign="top">

Displays the top 5 APIs with the highest number of failed calls.

</td>
</tr>
<tr>
<td valign="top">

API Errors

</td>
<td valign="top">

Displays the daily number of failed API calls per API.

</td>
</tr>
</table>



### Health

The Health page provides reports about key metrics related to the performance of your APIs. By default, it shows data for the last seven days.

At the top of the Health page, there is a date-range selector. This date-range selector lets you set the time period for which you want to analyze the reports. To set a new time period, click and drag the arrow on the date-range selector.

Above the date-range selector, select **Day**, **Hour**, or **Minutes** tabs to see daily, hourly, or 30-minute aggregate data.

The *Day* option displays seven touch points, one for each day of the week.

The *Hour* option displays 24 touch points, one for each hour of the day.

The *Minutes* option displays 48 touch points, one for every 30 minutes of the day.

At the top right corner of the Health page, click <span class="SAP-icons-V5"></span> to view advanced filter menu and options. The filter menu and options appear below the date-range selector and you can filter reports by APIs, API Types, API Products, Developers, Subscriptions for Applications, Subscriptions for Agents, MCP Servers, AI Products, MCP Tools, and MCP Resources. Once you apply the filter options, the applied filters are displayed under *Active Filters*.

The rest of the Health page displays a graphical view of key API metrics, as outlined in the table below:

**Health**


<table>
<tr>
<th valign="top">

Chart

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Calls

</td>
<td valign="top">

Displays the daily count of API calls made.

</td>
</tr>
<tr>
<td valign="top">

API Errors by Agents vs Applications

</td>
<td valign="top">

Displays failed call count via agents vs applications for each API.

</td>
</tr>
<tr>
<td valign="top">

API Errors by MCP Servers

</td>
<td valign="top">

Displays failed call count per MCP Server for each API.

</td>
</tr>
<tr>
<td valign="top">

Response Code Count

</td>
<td valign="top">

Displays the number of calls categorized by each response code.

</td>
</tr>
<tr>
<td valign="top">

API Response Codes

</td>
<td valign="top">

Displays the count of API calls grouped by response code for each API.

</td>
</tr>
<tr>
<td valign="top">

API Error Count by Response Code

</td>
<td valign="top">

Displays failed call counts for each API, categorized by response code.

</td>
</tr>
<tr>
<td valign="top">

API Error Count by API Type

</td>
<td valign="top">

Displays the number of failed calls per API, grouped by API type.

</td>
</tr>
<tr>
<td valign="top">

APIs with Authentication and Access Errors

</td>
<td valign="top">

Displays trends in authentication, external OAuth, and authorization errors across APIs.

</td>
</tr>
</table>



### Usage

The Usage report page provides reports on key metrics related to user-engagement. You can obtain information about the sources or medium from where you are acquiring users and traffic to your APIs, your most popular developers applications, and request verbs. By default, it displays data for the last two months and present month until the current date.

At the top of the Usage report page, there is a date-range selector. This date-range selector lets you set the time period for which you want to analyze the reports. To set a new time period, click and drag the arrow on the date-range selector.

Above the date-range selector, you can select *Month*, *Week*, or *Day* tabs to see data by month, week, or day.

The *Month* option displays three touch points, one for each of the last three months inclusive the current month.

The *Week* option displays one touch point for each week of the last three months inclusive the current month. A week starts on a Sunday and ends on a Saturday.

The *Day* option displays one touch point for each day. The number of touch points displayed here varies depending upon the time range you have selected under Month or Week tabs.

At the top right corner of the Usage page, click <span class="SAP-icons-V5"></span> to view advanced filter menu and options. The filter menu and options appear below the date-range selector and you can filter your reports by APIs, API Types, API Products, Developers, Subscription for Applications, Subscription for Agents, MCP Servers, AI Products, MCP Tools, and MCP Resources. Once you apply the filter options, the selected filters are displayed under *Active Filters*.

> ### Note:  
> Additional filters may be available depending on the selected artifact type and runtime. Filter options are dynamically updated based on the artifact type and other selections.

The rest of the Usage page displays a graphical view of key API metrics, as outlined in the table below:

**Usage**


<table>
<tr>
<th valign="top">

Chart

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Calls

</td>
<td valign="top">

Displays the daily count of API calls made.

</td>
</tr>
<tr>
<td valign="top">

APIs by Agents vs Applications

</td>
<td valign="top">

Displays the call count via agents vs applications for each API.

</td>
</tr>
<tr>
<td valign="top">

APIs by MCP Servers

</td>
<td valign="top">

Displays call count per MCP Server for each API.

</td>
</tr>
<tr>
<td valign="top">

Top API Type

</td>
<td valign="top">

Displays the number of calls per API type.

</td>
</tr>
<tr>
<td valign="top">

Developer Engagement

</td>
<td valign="top">

Displays the number of calls made by each developer, indicating their level of engagement.

</td>
</tr>
<tr>
<td valign="top">

New Developers

</td>
<td valign="top">

Displays up to 10 developers who have been recently onboarded to the Developer Hub, including their names and onboarding dates. Only developers who have made at least one API call are included.

</td>
</tr>
<tr>
<td valign="top">

New Subscriptions for Applications

</td>
<td valign="top">

Displays up to 10 newly created subscriptions for application, including the subscription name and the date and time of creation. Only subscriptions that have been used to make at least one API call are included.

</td>
</tr>
<tr>
<td valign="top">

Top Browsers

</td>
<td valign="top">

Displays the most used web browsers for API calls.

</td>
</tr>
<tr>
<td valign="top">

Top User Agents

</td>
<td valign="top">

Displays the most used user agents for API calls.

</td>
</tr>
<tr>
<td valign="top">

Top Operating Systems

</td>
<td valign="top">

Displays the most used operating systems, highlighting the top operating systems based on usage statistics.

</td>
</tr>
<tr>
<td valign="top">

Top Device Types

</td>
<td valign="top">

Displays the most used device types, highlighting the top devices based on usage frequency.

</td>
</tr>
<tr>
<td valign="top">

Request Verb Call Count

</td>
<td valign="top">

Displays the count of API calls categorized by request verb \(e.g., GET, POST, PUT, DELETE\).

</td>
</tr>
</table>

When the artifact type is set to *MCP Server*, the following charts and metrics are displayed across the Overview, Health, and Usage pages:



### Overview

At the top of the Overview report page, the following key MCP server metrics are represented in a tile format:

-   **Total MCP Server Calls:** Total number of MCP server calls made over a specified period.

-   **MCP Server Response Time:** Total time in milliseconds to respond to an MCP request.

-   **Total MCP Server Errors:**Total number of errors that occur on the MCP server, plus the errors that occurs on the target server from all the MCP requests and responses over a specified period.


The rest of the Overview page displays a graphical view of key MCP server metrics, as outlined in the table below:

**Overview**


<table>
<tr>
<th valign="top">

Chart

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

MCP Server Calls

</td>
<td valign="top">

Displays the daily count of MCP server calls made.

-   *All MCP Servers:* Displays aggregated call data across all configured MCP servers. This option is selected by default.
-   *Select MCP Servers from the list:* Allows you to filter data for specific MCP servers using the drop-down menu. When this option is selected, a drop-down becomes active, allowing you to choose one or more specific MCP servers to view their individual call data.



</td>
</tr>
<tr>
<td valign="top">

Top MCP Servers of the Week

</td>
<td valign="top">

Displays the top 5 most frequently called MCP servers for the week, showing the call count per agent for each MCP server.

</td>
</tr>
<tr>
<td valign="top">

Top Subscriptions for Agents for the Week

</td>
<td valign="top">

Displays the top 5 most active subscriptions for agents for the week, showing the call count per subscription for each agent.

</td>
</tr>
<tr>
<td valign="top">

Top API Products of the Week

</td>
<td valign="top">

Displays the top 5 products of the week based on the number of calls received for each product.

</td>
</tr>
<tr>
<td valign="top">

Top Developers of the Week

</td>
<td valign="top">

Displays the top 5 most active developers of the week.

</td>
</tr>
<tr>
<td valign="top">

Subscriptions for Agents for the Week

</td>
<td valign="top">

Displays the daily call count for each agent subscription during the week.

</td>
</tr>
<tr>
<td valign="top">

Tools for the Week by Agent

</td>
<td valign="top">

Displays the call count per agent for each tool during the week.

</td>
</tr>
<tr>
<td valign="top">

Resources for the Week by Agent

</td>
<td valign="top">

Displays the call count per agent for each resource during the week.

</td>
</tr>
<tr>
<td valign="top">

Tools/Resource Counts per Response Code

</td>
<td valign="top">

Displays a comparison of tool and resource call counts across response codes.

</td>
</tr>
<tr>
<td valign="top">

Tool Errors by Agent

</td>
<td valign="top">

Displays the failed call count per agent for each tool.

</td>
</tr>
<tr>
<td valign="top">

Resource Errors by Agent

</td>
<td valign="top">

Displays the failed call count per agent for each resource.

</td>
</tr>
</table>



### Health

The Health page provides reports about key metrics related to the performance of your MCP servers. By default, it shows data for the last seven days.

At the top of the Health page, there is a date-range selector. This date-range selector lets you set the time period for which you want to analyze the reports. To set a new time period, click and drag the arrow on the date-range selector.

Above the date-range selector, select **Day**, **Hour**, or **Minutes** tabs to see daily, hourly, or 30-minute aggregate data.

The *Day* option displays seven touch points, one for each day of the week.

The *Hour* option displays 24 touch points, one for each hour of the day.

The *Minutes* option displays 48 touch points, one for every 30 minutes of the day.

At the top right corner of the Health page, click <span class="SAP-icons-V5"></span> to view advanced filter menu and options. The filter menu and options appear below the date-range selector and you can filter reports by Developers, Subscriptions for Agents, MCP Servers, AI Products, MCP Tools, MCP Resources, MCP Target Type and MCP Target Values. Once you apply the filter options, the applied filters are displayed under *Active Filters*.

The rest of the Health page displays a graphical view of key MCP server metrics, as outlined in the table below:

**Health**


<table>
<tr>
<th valign="top">

Chart

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

MCP Server Errors by Tool vs Resource

</td>
<td valign="top">

Displays a comparison of failed tool and resource calls across MCP servers.

</td>
</tr>
<tr>
<td valign="top">

MCP Policy Errors

</td>
<td valign="top">

Displays the number of failed calls caused by policy errors for each MCP server.

</td>
</tr>
<tr>
<td valign="top">

Tool Errors by API

</td>
<td valign="top">

Displays the number of failed tool calls, grouped by API.

</td>
</tr>
<tr>
<td valign="top">

Resource Errors by API

</td>
<td valign="top">

Displays the number of failed resource calls, grouped by API.

</td>
</tr>
<tr>
<td valign="top">

Tool Errors by HTTP URL

</td>
<td valign="top">

Displays the number of failed tool calls, grouped by HTTP URL.

</td>
</tr>
<tr>
<td valign="top">

Resource Errors by HTTP URL

</td>
<td valign="top">

Displays the number of failed resource calls, grouped by HTTP URL.

</td>
</tr>
<tr>
<td valign="top">

Tool Errors by RFC Destination

</td>
<td valign="top">

Displays the number of failed tool calls, grouped by RFC destination.

</td>
</tr>
<tr>
<td valign="top">

Slowest MCP Servers

</td>
<td valign="top">

Displays the average response time per MCP server, showing up to 5 of the slowest-performing MCP servers.

</td>
</tr>
<tr>
<td valign="top">

Slowest Tools

</td>
<td valign="top">

Displays the average response time per tool, showing up to 5 of the slowest-performing tools.

</td>
</tr>
<tr>
<td valign="top">

Slowest Resources

</td>
<td valign="top">

Displays the average response time per resource, showing up to 5 of the slowest-performing resources.

</td>
</tr>
</table>



### Usage

The Usage report page provides reports on key metrics related to user-engagement. You can obtain information about the sources or medium from where you are acquiring users and traffic to your MCP servers. By default, it displays data for the last two months and present month until the current date.

At the top of the Usage report page, there is a date-range selector. This date-range selector lets you set the time period for which you want to analyze the reports. To set a new time period, click and drag the arrow on the date-range selector.

Above the date-range selector, you can select *Month*, *Week*, or *Day* tabs to see data by month, week, or day.

The *Month* option displays three touch points, one for each of the last three months inclusive the current month.

The *Week* option displays one touch point for each week of the last three months inclusive the current month. A week starts on a Sunday and ends on a Saturday.

The *Day* option displays one touch point for each day. The number of touch points displayed here varies depending upon the time range you have selected under Month or Week tabs.

At the top right corner of the Usage page, click <span class="SAP-icons-V5"></span> to view advanced filter menu and options. The filter menu and options appear below the date-range selector and you can filter your reports by Developers, Subscription for Agents, MCP Servers, AI Products, MCP Tools, MCP Resources, MCP Target Type, and MCP Target Values. Once you apply the filter options, the selected filters are displayed under *Active Filters*.

> ### Note:  
> Additional filters may be available depending on the selected artifact type and runtime. Filter options are dynamically updated based on the artifact type and other selections.

The rest of the Usage page displays a graphical view of key MCP server metrics, as outlined in the table below:

**Usage**


<table>
<tr>
<th valign="top">

Chart

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

APIs by Agents vs APIs by Applications

</td>
<td valign="top">

Displays a comparison of API calls made by agents and applications for each API.

</td>
</tr>
<tr>
<td valign="top">

APIs by Agents

</td>
<td valign="top">

Displays the number of API calls made by each agent.

</td>
</tr>
<tr>
<td valign="top">

HTTP URLs by Agents

</td>
<td valign="top">

Displays the number of calls made by each agent, grouped by HTTP URL.

</td>
</tr>
<tr>
<td valign="top">

RFCs by Agents

</td>
<td valign="top">

Displays the number of calls made by each agent, grouped by RFC destination.

</td>
</tr>
<tr>
<td valign="top">

Tools by API

</td>
<td valign="top">

Displays the number of calls for each tool, grouped by API.

</td>
</tr>
<tr>
<td valign="top">

Resources by API

</td>
<td valign="top">

Displays the number of calls for each resource, grouped by API.

</td>
</tr>
<tr>
<td valign="top">

Tools by HTTP URL

</td>
<td valign="top">

Displays the number of calls for each tool, grouped by HTTP URL.

</td>
</tr>
<tr>
<td valign="top">

Resources by HTTP URL

</td>
<td valign="top">

Displays the number of calls for each resource, grouped by HTTP URL.

</td>
</tr>
<tr>
<td valign="top">

Tools by RFC Destination

</td>
<td valign="top">

Displays the number of calls for each tool, grouped by RFC destination.

</td>
</tr>
</table>

> ### Note:  
> The values on the chart for a particular dimension are shown only up to a certain threshold. Any values beyond this threshold are grouped together and labelled as **Others**. By default, the threshold value for the charts is set to **25**. If you wish to modify the threshold value for the charts, please create a support ticket. To create a support ticket, see [Request to Modify Threshold Value for Charts](request-to-modify-threshold-value-for-charts-b55f89d.md).

> ### Note:  
> The data retention period for all report types available in the analytics dashboard is 6 months. That is, the analytics dashboard stores and retains data only for a period of 6 months. After the retention period, the data is purged.



<a name="loioda4af34080264dd4867f31ac266400d0__section_ub1_h2v_jfc"/>

## Date-Range Selector

In the **Health** and **Usage** report pages, there is a date-range selector. This date-range selector lets you set the time period for which you want to analyze the reports. To set a new time period, click and drag the arrow on the date-range selector.

At the top-right corner of the date-range selector, there is a small action bar with options to hide the date-range selector and refresh the reports.

Click <span class="SAP-icons-V5"></span> to hide or unhide the date-range selector.

Click <span class="SAP-icons-V5"></span> to refresh the reports with latest data from API calls.

While viewing your reports on the Health and Usage page, you can choose to keep the data-range selector always visible. You can do so by clicking on the :pushpin: icon available below the date-range selector.



<a name="loioda4af34080264dd4867f31ac266400d0__section_wqv_n2v_jfc"/>

## Action Bar

The Action Bar appears at the top of each report that contains graphical data. The controls on the action bar allow you to act on the graphical data. Using these controls, you can switch between graphical view and tabular view, and switch between different chart types.

Click <span class="SAP-icons-V5"></span> to hide and unhide legends for a graph.

Click <span class="SAP-icons-V5"></span> <span class="SAP-icons-V5"></span>to view enlarged and diminished image of a graph.

Click <span class="SAP-icons-V5"></span> to switch between full screen view and default screen view.

Click <span class="SAP-icons-V5"></span> to select a different chart type. You can select between pie charts, line charts, bar charts, donut charts, or heatmaps. Note that not all chart types might be supported for a specific report.

Click <span class="SAP-icons-V5"></span> to switch between a tabular view and graphical view of a report.

**Related Information**  


[Custom Views and Charts](custom-views-and-charts-900eca5.md "Add custom views and create customized charts for your API or MCP (Model Context Protocol) server metrics that are critical to your business.")

[Create and Work with Custom Reports](create-and-work-with-custom-reports-46bea5d.md "Create your own custom reports in the analytics dashboard.")

