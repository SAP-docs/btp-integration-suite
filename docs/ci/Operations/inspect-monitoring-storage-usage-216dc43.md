<!-- loio216dc43e45b7423eb670e6e1e7bd05e0 -->

# Inspect Monitoring Storage Usage

Inspect usage of the monitoring storage database for a given time period \(as selected with the *Time* parameter\).

At runtime, monitoring data is written to a database. For each integration flow processed at runtime, a message processing log is written that contains information about the processing steps \(see [Message Processing Log](message-processing-log-b32f8cd.md)\).

> ### Tip:  
> Each SAP Cloud Integration tenant is associated with a physical database that has a limited size. This database is used by certain steps during the runtime of integration flows .

The usage of database storage is plotted in a bar graph against time.

The bar height shows the data volume \(in MB\) used by monitoring data for a given time period \(as selected with the *Time* parameter\).

A green bullet represents the total count of message processing logs.

The level of usage is indicated by the bar height and color \(from green for low usage, up to red for critical usage\). The thresholds are based on the entitlement for monitoring storage consumption in the monitoring database.


<table>
<tr>
<th valign="top">

Level of Usage

</th>
<th valign="top">

Bar Color

</th>
<th valign="top">

Database Connection Usage

</th>
</tr>
<tr>
<td valign="top">

Critical

</td>
<td valign="top">

Red

</td>
<td valign="top">

More than 90%

</td>
</tr>
<tr>
<td valign="top">

Warning

</td>
<td valign="top">

Orange

</td>
<td valign="top">

Between 70% and 90%

</td>
</tr>
<tr>
<td valign="top">

OK

</td>
<td valign="top">

Green

</td>
<td valign="top">

Less than 70%

</td>
</tr>
</table>

The default value of the entitlement is 35 GB, as documented at [What Is SAP Cloud Integration?](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/what-is-sap-cloud-integration).

If the entitlement is exceeded there is a risk of overloading the database storage, which might eventually cause problems in the database management system.

The duration covered by a bar represents the average usage during:

-   One hour when *Past Day* is selected as *Time* 

-   One day when *Past Week* or *Past Month* is selected as *Time* 


Click a bar to get more context information and to get access to the following functions \(the results are filtered according to the setting of the *Time* parameter\):

-   *Show Messages*

    Navigate to the *Monitor Message Processing* screen for the selected time period \(see [Monitor Message Processing](monitor-message-processing-314df3f.md)\).

-   *Inspect Usage*

    Navigate to the *Top Integration Flows* screen that allows you to inspect the topic integration flows by message processing log count.


*Zoom Out* and *Zoom In* to extend/reduce the selected time period. 

> ### Note:  
> The system reads the resource consumption once per hour. That means, that there can be a maximum lag of 1 hour between the processing of an integration flow writing monitoring data and the *Inspect* feature to show the impact of this integration flow.



<a name="loio216dc43e45b7423eb670e6e1e7bd05e0__section_tqd_3w1_bxb"/>

## Top Integration Flows

On the *Top Integration Flows* screen, you can find more details in the section *Top Flows by Message Processing Log Count*.

Shows those integration flows that write the most message processing logs for a specific time period \(as selected by the *Time* parameter\).

Click a cell to display more context information for the selected integration flow \(result filtered according to the setting of the *Time* parameter\):

See: [Inspect Top Integration Flows by Message Processing Log Count](inspect-top-integration-flows-by-message-processing-log-count-696b65e.md)



<a name="loio216dc43e45b7423eb670e6e1e7bd05e0__section_vgy_pw5_ywb"/>

## What to Do in Critical Situations

If the entitlement for the monitoring database volume is approached or even exceeded, you can inspect which integration flows are the top contributors \(see [Inspect Top Integration Flows by Message Processing Log Count](inspect-top-integration-flows-by-message-processing-log-count-696b65e.md)\). For the top consuming integration flows you can ensure that the message processing *Log Level* parameter is set to *Info* 

To do that, in the *Monitor* section, click a tile in the *Manage Integration Content* section select the integration flow, and configure the *Log Configuration* parameter accordingly.

See: [Setting Log Levels](setting-log-levels-4e6d3fc.md) 

You can also check if there are integration flows showing many erroneous message processing logs. To filter for such integration flows, set the *Message Processing Status* filter to *Failed*. Check the respective integration flow and fix the root cause for the failures.

More information:

[Guidelines and Best Practices for Message Monitoring](guidelines-and-best-practices-for-message-monitoring-6f598b4.md)

