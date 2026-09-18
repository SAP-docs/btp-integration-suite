<!-- loioc2f3accd1fbf44f3aeb2d8eea6f741b0 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# MCP Server Charts

View the charts for MCP server artifacts across the *Overview*, *Health*, and *Usage* report pages.

> ### Note:  
> Availability of the MCP server feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

> ### Note:  
> AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through September 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).

When the *Artifact Type* is set to *MCP Server*, the following charts are available across the report pages. Expand each section to view its charts.



## Overview

The *Overview* page provides a concise report about important and key metrics for your MCP servers. By default, the *Overview* page displays report data for the last seven days.

At the top of the *Overview* report page, the following key MCP server metrics are represented in a tile format:

**KPI Tiles**


<table>
<tr>
<th valign="top">

Tile

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Total MCP Server Calls

</td>
<td valign="top">

Displays the weekly percentage difference in the total number of MCP server calls made.

</td>
</tr>
<tr>
<td valign="top">

MCP Server Response Time

</td>
<td valign="top">

Displays the weekly percentage difference in the total time \(in milliseconds\) taken to respond to an MCP request.

</td>
</tr>
<tr>
<td valign="top">

Total MCP Server Errors

</td>
<td valign="top">

Displays the weekly percentage difference in the total number of errors that occur on the MCP server and the target server.

</td>
</tr>
</table>

Each tile shows the weekly percentage difference in data for a key MCP server metric. A green-arrowed percentage difference indicates a healthy metric, whereas a red-arrowed percentage difference indicates the metric needs improvement.

Hovering over a tile displays the **Previous Value** \(previous week\), the **Current Value** \(current week\), and the **KPI Value** \(the percentage difference between the two\).

The rest of the *Overview* page displays a graphical view of key MCP server metrics, as outlined in the table below:

**MCP server-related charts**


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

Displays the top 5 MCP servers of the week based on the number of calls per agent.

</td>
</tr>
<tr>
<td valign="top">

Top Subscriptions for Agents for the Week

</td>
<td valign="top">

Displays the top 5 subscriptions for agents based on the number of calls made through each subscription during the week.

</td>
</tr>
<tr>
<td valign="top">

Top AI Products of the Week

</td>
<td valign="top">

Displays the top 5 AI products for the week based on the number of calls made by agents.

</td>
</tr>
<tr>
<td valign="top">

Top Developers of the Week

</td>
<td valign="top">

Displays the top 5 developers for the week based on the number of calls made by each developer.

</td>
</tr>
<tr>
<td valign="top">

Subscriptions for Agents for the Week

</td>
<td valign="top">

Displays the daily number of calls made through subscriptions for agents during the week.

</td>
</tr>
<tr>
<td valign="top">

Tools for the Week by Agent

</td>
<td valign="top">

Displays the number of calls made by each agent for each tool during the week.

</td>
</tr>
<tr>
<td valign="top">

Resources for the Week by Agent

</td>
<td valign="top">

Displays the number of calls made by each agent for each resource during the week.

</td>
</tr>
<tr>
<td valign="top">

Tools/Resource Counts per Response Code

</td>
<td valign="top">

Compares the number of tool calls versus resource calls for each response code.

</td>
</tr>
<tr>
<td valign="top">

Tool Errors by Agent

</td>
<td valign="top">

Displays the number of failed calls made by each agent for each tool during the week.

</td>
</tr>
<tr>
<td valign="top">

Resource Errors by Agent

</td>
<td valign="top">

Displays the number of failed calls made by each agent for each resource during the week.

</td>
</tr>
</table>



## Health

The *Health* page provides reports about key metrics related to the performance of your MCP servers.

At the top of the *Health* page, there is a date-range selector. This date-range selector lets you set the time period for which you want to analyze the reports. To set a new time period, click and drag the arrow on the date-range selector.

Above the date-range selector, select **Day**, **Hour**, or **Minutes** tabs to see daily, hourly, or 30-minute aggregate data.

-   The *Day* option displays seven touch points, one for each day of the week.

-   The *Hour* option displays 24 touch points, one for each hour of the day.

-   The *Minutes* option displays 48 touch points, one for every 30 minutes of the day.


At the top right corner of the *Health* page, click <span class="SAP-icons-V5"></span> to view advanced filter menu and options. The filter menu and options appear below the date-range selector. Once you apply the filter options, the applied filters are displayed under *Active Filters*. For the complete list of filter options, see [Applying Chart Filters](applying-chart-filters-a928a03.md).

The rest of the *Usage* page displays a graphical view of key MCP server metrics, as outlined in the table below:

**MCP server-related charts**


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

Compares the number of failed tool and resource calls for each MCP server.

</td>
</tr>
<tr>
<td valign="top">

MCP Policy Errors

</td>
<td valign="top">

Displays the number of failed calls due to policy errors for each MCP server.

</td>
</tr>
<tr>
<td valign="top">

Tool Errors by API

</td>
<td valign="top">

Displays the number of failed tool calls by API for each tool.

</td>
</tr>
<tr>
<td valign="top">

Resource Errors by API

</td>
<td valign="top">

Displays the number of failed resource calls by API for each resource.

</td>
</tr>
<tr>
<td valign="top">

Tool Errors by MCP Server URL

</td>
<td valign="top">

Displays the number of failed tool calls by MCP server URL for each tool.

</td>
</tr>
<tr>
<td valign="top">

Resource Errors by MCP Server URL

</td>
<td valign="top">

Displays the number of failed resource calls by MCP server URL for each tool.

</td>
</tr>
<tr>
<td valign="top">

Tool Errors by HTTP URL

</td>
<td valign="top">

Displays the number of failed tool calls by HTTP URL for each tool.

</td>
</tr>
<tr>
<td valign="top">

Resource Errors by HTTP URL

</td>
<td valign="top">

Displays the number of failed resource calls by HTTP URL for each resource.

</td>
</tr>
<tr>
<td valign="top">

Tool Errors by RFC Destination

</td>
<td valign="top">

Displays the number of failed tool calls by RFC destination for each tool.

</td>
</tr>
<tr>
<td valign="top">

Slowest MCP Servers

</td>
<td valign="top">

Displays the average response time for the top 5 slowest MCP servers, based on the final response time of each MCP call.

</td>
</tr>
<tr>
<td valign="top">

Slowest Tools

</td>
<td valign="top">

Displays the average response time for the top 5 slowest MCP tools, based on the response time of the underlying target call \(API, RFC, or HTTP endpoint\).

</td>
</tr>
<tr>
<td valign="top">

Slowest Resources

</td>
<td valign="top">

Displays the average response time for the top 5 slowest MCP resources, based on the response time of the underlying target call \(API, RFC, or HTTP endpoint\).

</td>
</tr>
</table>



## Usage

The *Usage* page provides reports on key metrics related to user engagement for your MCP servers.

At the top of the Usage report page, there is a date-range selector. This date-range selector lets you set the time period for which you want to analyze the reports. To set a new time period, click and drag the arrow on the date-range selector.

Above the date-range selector, you can select *Month*, *Week*, or *Day* tabs to see data by month, week, or day.

-   The *Month* option displays three touch points, one for each of the last three months inclusive the current month.

-   The *Week* option displays one touch point for each week of the last three months inclusive the current month. A week starts on a Sunday and ends on a Saturday.

-   The *Day* option displays one touch point for each day. The number of touch points displayed here varies depending upon the time range you have selected under Month or Week tabs.


At the top right corner of the *Usage* page, click <span class="SAP-icons-V5"></span> to view advanced filter menu and options. The filter menu and options appear below the date-range selector. Once you apply the filter options, the selected filters are displayed under *Active Filters*. For the complete list of filter options, see [Applying Chart Filters](applying-chart-filters-a928a03.md).

The rest of the *Usage* page displays a graphical view of key MCP server metrics, as outlined in the table below:

**MCP server-related charts**


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

Compares the number of API calls made through agents and applications for each API.

</td>
</tr>
<tr>
<td valign="top">

APIs by Agents

</td>
<td valign="top">

Displays the number of agent calls that triggered API calls by agent for each API.

</td>
</tr>
<tr>
<td valign="top">

MCP Server URLs by Agents

</td>
<td valign="top">

Displays the number of agent calls that triggered MCP server calls by agent for each MCP server URL.

</td>
</tr>
<tr>
<td valign="top">

HTTP URLs by Agents

</td>
<td valign="top">

Displays the number of agent calls that triggered HTTP endpoint calls by agent for each HTTP URL.

</td>
</tr>
<tr>
<td valign="top">

RFCs by Agents

</td>
<td valign="top">

Displays the number of agent calls that triggered RFC calls by agent for each RFC.

</td>
</tr>
<tr>
<td valign="top">

Tools by API

</td>
<td valign="top">

Displays the number of tool calls that triggered API calls by API for each tool.

</td>
</tr>
<tr>
<td valign="top">

Resources by API

</td>
<td valign="top">

Displays the number of resource calls that triggered API calls by API for each resource.

</td>
</tr>
<tr>
<td valign="top">

Tools by MCP Server URL

</td>
<td valign="top">

Displays the number of tool calls that triggered MCP server calls by MCP server URL for each tool.

</td>
</tr>
<tr>
<td valign="top">

Resources by MCP Server URL

</td>
<td valign="top">

Displays the number of resource calls that triggered MCP server calls by MCP server URL for each resource.

</td>
</tr>
<tr>
<td valign="top">

Tools by HTTP URL

</td>
<td valign="top">

Displays the number of tool calls that triggered HTTP endpoint calls by HTTP URL for each tool.

</td>
</tr>
<tr>
<td valign="top">

Resources by HTTP URL

</td>
<td valign="top">

Displays the number of resource calls that triggered HTTP endpoint calls by HTTP URL for each resource.

</td>
</tr>
<tr>
<td valign="top">

Tools by RFC Destination

</td>
<td valign="top">

Displays the number of tool calls that triggered RFC calls by RFC destination for each tool.

</td>
</tr>
</table>

**Related Information**  


[API Artifact Charts](api-artifact-charts-05fe5c0.md "View the charts for API artifacts across the Overview, Health, and Usage report pages.")

