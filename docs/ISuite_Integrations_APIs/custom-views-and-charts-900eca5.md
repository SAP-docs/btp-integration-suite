<!-- loio900eca53079146489315f1fb53ad0720 -->

# Custom Views and Charts

Add custom views and create customized charts for your API or MCP \(Model Context Protocol\) server metrics that are critical to your business.

> ### Note:  
> Availability of the MCP Server feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).



## Overview

You can create custom charts to analyze traffic patterns, identify errors, track usage trends, and gain analytical insights.

Custom charts support two contexts:

-   **API Charts:** Analyze traffic and performance data for APIs, products, and subscriptions.

-   **MCP Server Charts:** Analyze traffic and performance data for MCP servers, tools, resources, and agent subscriptions.

    > ### Note:  
    > You can create either an API-relevant chart or an MCP server-relevant chart at a time. Dimensions from both contexts cannot be combined in a single chart.




## Key Concepts



### Dimensions

Dimensions define how your analytics data is categorized and grouped on the chart. They represent the attributes by which you want to slice and view your data \(for example: by API name, by response code, by MCP tool\).

Dimensions are organized into two exclusive sets:

-   **API Dimensions:** Used to create API-relevant charts.

-   **MCP Dimensions:** Used to create MCP server-relevant charts.

    The first dimension you select determines which set of dimensions becomes available for subsequent selections.




### Measures

Measures are the quantitative values displayed on the chart. They represent the metrics you want to track against your selected dimensions.



### Filters

Filters allow you to narrow down the data displayed in your chart to specific values:

-   Filters are available only for the dimensions currently added to the chart.

-   Adding or removing dimensions dynamically updates the available filters.
-   Multiple filters can be applied simultaneously.
-   Some filters have dependencies, such as MCP Target Type and MCP Target Value.



## Dimension Selection Behavior

When you create or edit custom chart page, the dimension drop-down displays all available dimensions from both the API and MCP sets:


<table>
<tr>
<th valign="top">

Action

</th>
<th valign="top">

Behavior

</th>
</tr>
<tr>
<td valign="top">

First dimension selected is from the API set

</td>
<td valign="top">

Drop-down filters to show only remaining API dimensions.

</td>
</tr>
<tr>
<td valign="top">

First dimension selected is from the MCP set

</td>
<td valign="top">

Drop-down filters to show only remaining MCP dimensions.

</td>
</tr>
<tr>
<td valign="top">

All dimensions are removed

</td>
<td valign="top">

Drop-down resets to show all dimensions from both sets.

</td>
</tr>
</table>



## Available Dimensions



### API Dimensions

The following dimensions are available for creating API-relevant charts:


<table>
<tr>
<th valign="top">

Dimension

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API Name

</td>
<td valign="top">

The name of the API.

</td>
</tr>
<tr>
<td valign="top">

API Product Name

</td>
<td valign="top">

The name of the API product the API belongs to.

</td>
</tr>
<tr>
<td valign="top">

API Proxy Basepath

</td>
<td valign="top">

The base path configured for the API.

</td>
</tr>
<tr>
<td valign="top">

API Request Method

</td>
<td valign="top">

The HTTP method used in the request \(example: GET, POST, PUT, DELETE, PATCH\)

</td>
</tr>
<tr>
<td valign="top">

API Request URL

</td>
<td valign="top">

The full request URL of the API call.

</td>
</tr>
<tr>
<td valign="top">

API Response Code

</td>
<td valign="top">

The HTTP response status code returned \(example: 200, 401, 500\)

</td>
</tr>
<tr>
<td valign="top">

API Type

</td>
<td valign="top">

The type of API \(example: REST, SOAP, OData\)

</td>
</tr>
<tr>
<td valign="top">

Developer Name

</td>
<td valign="top">

The name of the developer consuming the API.

</td>
</tr>
<tr>
<td valign="top">

Device Type

</td>
<td valign="top">

The type of device used to make the API call \(example: Desktop, Mobile, Tablet\)

</td>
</tr>
<tr>
<td valign="top">

OS Family Name

</td>
<td valign="top">

The operating system family of the calling device \(example: Windows, macOS, Linux, iOS, Android\)

</td>
</tr>
<tr>
<td valign="top">

Platform Name

</td>
<td valign="top">

The platform from which the API call originated.

</td>
</tr>
<tr>
<td valign="top">

Subscription Name for Application

</td>
<td valign="top">

The name of the application subscription used to access the API.

</td>
</tr>
</table>



### MCP Server Dimensions

The following dimensions are available for creating MCP server-relevant charts:


<table>
<tr>
<th valign="top">

Dimension

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

MCP Request URL

</td>
<td valign="top">

The request URL for the MCP server call.

</td>
</tr>
<tr>
<td valign="top">

MCP Resource Name

</td>
<td valign="top">

The name of the MCP resource accessed during the call.

</td>
</tr>
<tr>
<td valign="top">

MCP Response Code

</td>
<td valign="top">

The HTTP response status code returned \(example: 200, 401, 500\)

</td>
</tr>
<tr>
<td valign="top">

MCP Server Name

</td>
<td valign="top">

The name of the MCP server.

</td>
</tr>
<tr>
<td valign="top">

MCP Target Value

</td>
<td valign="top">

The specific backend target identifier, dynamically determined by the selected Target Type.

</td>
</tr>
<tr>
<td valign="top">

MCP Tool Name

</td>
<td valign="top">

The name of the specific MCP tool invoked during the call.

</td>
</tr>
<tr>
<td valign="top">

RFC Destination

</td>
<td valign="top">

The name of the RFC destination used during the call.

</td>
</tr>
<tr>
<td valign="top">

Subscription Name for Agent

</td>
<td valign="top">

The name of the agent subscription used to access the MCP server.

</td>
</tr>
</table>

**Related Information**  


[Create and Work with Custom Reports](create-and-work-with-custom-reports-46bea5d.md "Create your own custom reports in the analytics dashboard.")

