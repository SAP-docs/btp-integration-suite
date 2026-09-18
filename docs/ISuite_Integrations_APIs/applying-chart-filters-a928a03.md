<!-- loioa928a0364de346c8a13363aa4bd87536 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Applying Chart Filters

In the analytics dashboard, the filter option is available on the *Health* and *Usage* report pages. Use it to refine the data displayed in the reports.

To open the filter menu, click <span class="SAP-icons-V5"></span> at the top-right corner of the report page. The filter menu and options appear below the date-range selector. Once you apply the filter options, the applied filters are displayed under *Active Filters*.

The available filter options depend on the selected artifact type.



## Filters for the API Artifact Type

When the artifact type is set to *API*, you can filter reports by:

-   API Types
-   APIs
-   API Products
-   AI Products
-   Developers
-   Subscriptions for Applications
-   Subscriptions for Agents
-   MCP Servers
-   MCP Tools
-   MCP Resources



### API Types

Use the*API Types* filter to scope report data to specific API categories.


<table>
<tr>
<th valign="top">

Option

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

All

</td>
<td valign="top">

Includes data from all API types \(default\).

</td>
</tr>
<tr>
<td valign="top">

REST

</td>
<td valign="top">

Includes data from REST APIs only.

</td>
</tr>
<tr>
<td valign="top">

OData

</td>
<td valign="top">

Includes data from OData APIs only.

</td>
</tr>
</table>



## Filters for the MCP Server Artifact Type

When the artifact type is set to *MCP Server*, you can filter reports by:

-   AI Products
-   Developers
-   Subscriptions for Agents
-   MCP Servers
-   MCP Tools
-   MCP Resources
-   MCP Target Type
-   MCP Target Values



### Dependent Filters: MCP Target Type and MCP Target Value

The MCP Target Type and MCP Target Value filters \(available for the MCP Server artifact type\) operate in a parent-child \(dependent\) relationship. Select an *MCP Target Type* first, and then select the corresponding *MCP Target Value*.

**Filter by MCP Target Type**

The *MCP Target Type* filter displays the following fixed values:


<table>
<tr>
<th valign="top">

MCP Target Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API

</td>
<td valign="top">

The MCP server connects to an API as its backend target.

</td>
</tr>
<tr>
<td valign="top">

RFC

</td>
<td valign="top">

The MCP server connects to a Remote Function Call \(RFC\) as its backend target.

</td>
</tr>
<tr>
<td valign="top">

HTTP URL

</td>
<td valign="top">

The MCP server connects to an HTTP endpoint URL as its backend target.

</td>
</tr>
<tr>
<td valign="top">

MCP Server URL

</td>
<td valign="top">

The MCP server connects to another MCP server as its backend target.

</td>
</tr>
</table>

**Filter by MCP Target Values**

After you select an *MCP Target Type*, the *MCP Target Values* drop-down is dynamically populated based on your selection:


<table>
<tr>
<th valign="top">

If MCP Target Type is...

</th>
<th valign="top">

Then MCP Target Value shows...

</th>
</tr>
<tr>
<td valign="top">

API

</td>
<td valign="top">

List of available API names configured as targets.

</td>
</tr>
<tr>
<td valign="top">

RFC

</td>
<td valign="top">

List of available RFC names configured as targets.

</td>
</tr>
<tr>
<td valign="top">

HTTP URL

</td>
<td valign="top">

List of available HTTP endpoint URLs configured as targets.

</td>
</tr>
<tr>
<td valign="top">

MCP Server URL

</td>
<td valign="top">

List of available MCP server URLs configured as targets.

</td>
</tr>
</table>

> ### Note:  
> Additional filters may be available depending on the selected artifact type and runtime. Filter options are dynamically updated based on the artifact type and other selections.

