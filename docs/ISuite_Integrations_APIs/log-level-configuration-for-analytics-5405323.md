<!-- loio540532393117453a96829e8993a84574 -->

# Log Level Configuration for Analytics

Analytics data availability for API and MCP Server artifacts depends on the Message Processing Log \(MPL\) log level, which determines what data is captured and displayed in the analytics dashboard. The default log level is **Info**.



## Configuring the Log Level

To adjust the MPL log level for an API or MCP Server artifact:

1.  Log on to SAP Integration Suite.
2.  From the left navigation pane, choose *Monitor* \> *Integrations and APIs*.
3.  Choose *Manage Integration Content* and select the deployed API or MCP Server artifact.
4.  Navigate to the *Log Configuration* section and set the desired log level.

    > ### Note:  
    > The default log level is *Info*.

5.  Save your changes.

For more information about monitoring and log configuration, see [Monitor APIs and MCP Servers](monitor-apis-and-mcp-servers-399b6c6.md).



### Log Level Reference


<table>
<tr>
<th valign="top">

Log Level

</th>
<th valign="top">

Analytics Behavior

</th>
</tr>
<tr>
<td valign="top">

None

</td>
<td valign="top">

No analytics data is captured. The analytics dashboard will show no results.

</td>
</tr>
<tr>
<td valign="top">

Info \(default, recommended\)

</td>
<td valign="top">

All standard API and MCP Server analytics data is available.

</td>
</tr>
<tr>
<td valign="top">

Error

</td>
<td valign="top">

Analytics data is available only for **failed** API or MCP Server calls.

</td>
</tr>
<tr>
<td valign="top">

Debug

</td>
<td valign="top">

All standard API and MCP Server analytics data is available.

</td>
</tr>
<tr>
<td valign="top">

Trace

</td>
<td valign="top">

All standard API and MCP Server analytics data is available.

</td>
</tr>
</table>

