<!-- loio05fe5c02e69f4d52b9d011e68ecdb5f1 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# API Artifact Charts

View the charts for API artifacts across the *Overview*, *Health*, and *Usage* report pages.

> ### Note:  
> AI features are accessible only with the Premium and Enhanced Editions. These are provided as a free promotion through September 2026 and will be commercialized later as AI features using AI Units. For more information on availability of these AI features across SAP BTP regions, see [3463620](https://me.sap.com/notes/3463620).

When the *Artifact Type* is set to *API*, the following charts are available across the report pages. Expand each section to view its charts.



## Overview

The *Overview* page provides a concise report about important and key metrics for your API artifacts. By default, the *Overview* page provides report data for the last seven days.

At the top of the *Overview* report page, the following key API metrics are represented in a tile format:

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

Total API Calls

</td>
<td valign="top">

Displays the weekly percentage difference in the total number of API requests made.

</td>
</tr>
<tr>
<td valign="top">

API Calls via MCP Servers

</td>
<td valign="top">

Displays the weekly percentage difference in API requests made via MCP servers.

</td>
</tr>
<tr>
<td valign="top">

API Response Time

</td>
<td valign="top">

Displays the weekly percentage difference in the average API response time.

</td>
</tr>
<tr>
<td valign="top">

Total API Errors

</td>
<td valign="top">

Displays the weekly percentage difference in the total number of API and target server errors.

</td>
</tr>
</table>

Each tile shows the weekly percentage difference in data for a key API metric. A green-arrowed percentage difference indicates a healthy API metric, whereas a red-arrowed percentage difference indicates the API metric needs improvement.

Hovering over a tile displays the **Previous Value** \(previous week\), the **Current Value** \(current week\), and the **KPI Value** \(the percentage difference between the two\).

The rest of the *Overview* page displays a graphical view of key API metrics, as outlined in the table below:

**API artifact-related charts**


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

Displays the daily average number of API calls per subscription for applications.

</td>
</tr>
<tr>
<td valign="top">

Developers for the Week

</td>
<td valign="top">

Displays the daily average number of API calls made by each developer.

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

API Errors

</td>
<td valign="top">

Displays the daily number of failed API calls per API.

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
</table>



## Health

The *Health* page provides reports about key metrics related to the performance of your API artifacts.

At the top of the *Health* page, there is a date-range selector. This date-range selector lets you set the time period for which you want to analyze the reports. To set a new time period, click and drag the arrow on the date-range selector.

Above the date-range selector, select **Day**, **Hour**, or **Minutes** tabs to see daily, hourly, or 30-minute aggregate data.

-   The *Day* option displays seven touch points, one for each day of the week.

-   The *Hour* option displays 24 touch points, one for each hour of the day.

-   The *Minutes* option displays 48 touch points, one for every 30 minutes of the day.


At the top right corner of the *Health* page, click <span class="SAP-icons-V5"></span> to view advanced filter menu and options. The filter menu and options appear below the date-range selector. Once you apply the filter options, the applied filters are displayed under*Active Filters*. For the complete list of filter options, see [Applying Chart Filters](applying-chart-filters-a928a03.md).

The rest of the *Health* page displays a graphical view of key API metrics, as outlined in the table below:


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



## Usage

The *Usage* page provides reports on key metrics related to user engagement for your API artifacts.

At the top of the Usage report page, there is a date-range selector. This date-range selector lets you set the time period for which you want to analyze the reports. To set a new time period, click and drag the arrow on the date-range selector.

Above the date-range selector, you can select *Month*, *Week*, or *Day* tabs to see data by month, week, or day.

-   The *Month* option displays three touch points, one for each of the last three months inclusive the current month.

-   The *Week* option displays one touch point for each week of the last three months inclusive the current month. A week starts on a Sunday and ends on a Saturday.

-   The *Day* option displays one touch point for each day. The number of touch points displayed here varies depending upon the time range you have selected under Month or Week tabs.


At the top right corner of the *Usage* page, click <span class="SAP-icons-V5"></span> to view advanced filter menu and options. The filter menu and options appear below the date-range selector. Once you apply the filter options, the applied filters are displayed under*Active Filters*. For the complete list of filter options, see [Applying Chart Filters](applying-chart-filters-a928a03.md).

The rest of the *Usage* page displays a graphical view of key API metrics, as outlined in the table below:


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

**Related Information**  


[MCP Server Charts](mcp-server-charts-c2f3acc.md "View the charts for MCP server artifacts across the Overview, Health, and Usage report pages.")

