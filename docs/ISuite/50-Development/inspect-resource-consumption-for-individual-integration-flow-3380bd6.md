<!-- loio3380bd6b147846468de4e3b3a687d6a9 -->

# Inspect Resource Consumption for Individual Integration Flow

Inspect the resource consumption for a specific integration flow for a given time period.

You can navigate to this dashboard from the following screens for a selected integration flow:

-   *Database Connection Usage* \> *Top Integration Flows* \(see [Inspect Top Integration Flows by Database Connection Usage](inspect-top-integration-flows-by-database-connection-usage-79c5a05.md)\)

-   *Database Transactions* \> *Top Integration Flows* \(see [Inspect Top Integration Flows by Maximum Transaction Duration](inspect-top-integration-flows-by-maximum-transaction-duration-ab67942.md)\)

-   *Monitoring Storage* \> *Top Integration Flows* \(see [Inspect Top Integration Flows by Message Processing Log Count](inspect-top-integration-flows-by-message-processing-log-count-696b65e.md)\)

-   *Memory Usage* \> *Top Integration Flows* \(see [Inspect Integration Flows By System Memory Usage](inspect-integration-flows-by-system-memory-usage-2a2e1f2.md)\)


Select the time interval for which you want to display resource consumption. If you have selected resource type *Monitoring Storage* or *Memory Usage*, you can further filter the display by monitoring status.

You can select the resource type for which you want to display the consumption in a dropdown list.

The resource consumption for an individual integration flow is shown for the given time interval in a diagram. Depending on the chosen resource type, the diagram shows the following data:


<table>
<tr>
<th valign="top">

Selected Resource Type

</th>
<th valign="top">

Diagram Shows ...

</th>
</tr>
<tr>
<td valign="top">

*Database Connection Usage* 

</td>
<td valign="top">

The database connection usage \(in percent\) is plotted in a bar graph against time.

The bar height shows usage in percentage of the maximum usage.

The duration covered by a bar is:

Maximum usage corresponds to the situation where all database connections are used.

The level of usage is indicated by the bar height and color \(from green for low usage, up to red for critical usage\).

-   Critical \(red\) indicates more than 90%

-   Warning \(orange\) indicates between 70% and 90%

-   OK \(green\) indicates less than 70%




</td>
</tr>
<tr>
<td valign="top">

*Database Transactions* 

</td>
<td valign="top">

The maximum duration of database transactions \(in minutes\) is plotted in a bar graph against time.

The level of usage is indicated by the bar height and color \(from green for low duration, up to red for critical duration\).

-   Critical \(red\) indicates maximum duration: more than 60 minutes

-   Warning \(orange\) indicates maximum duration: between 5 minutes and 60 minutes

-   OK \(green\) indicates maximum duration: less than 5 minutes




</td>
</tr>
<tr>
<td valign="top">

*Monitoring Storage* 

</td>
<td valign="top">

The number of message processing logs stored in a dedicated time interval is plotted in a trajectory against time.

A blue bullet represents the total count of message processing logs.

</td>
</tr>
<tr>
<td valign="top">

*Memory Usage* 

</td>
<td valign="top">

The message throughput is plotted in two charts against time.

-   The total count of message processing logs \(MPLs\) for a given time period \(as selected with the *Time* parameter\) is plotted in a bar chart.

    The number of MPLs is identical to the number of messages processed during the selected time period.

-   The maximum message size within this time period is plotted in a line chart with a green bullet.




</td>
</tr>
</table>

Clicking a bar or bullet in a diagram allows you to navigate to the message monitor \(selecting *Show Messages*\).

See also: [Monitor Message Processing](monitor-message-processing-314df3f.md)

