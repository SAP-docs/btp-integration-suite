<!-- loio6736a3726760451bab9b07017df65616 -->

# Inspect Database Transaction Usage

Inspect database transaction usage for a given time period and analyze critical situations in which long-running transactions occur.

There are no hard limits for the number and duration of database transactions. However, ideally, design your integration scenarios so that transactions are short lived. Long-living transactions can impose a significant load on database resources. A high load on database resources can cause problems in the database management system and impact message processing.

The maximum duration of database transactions \(in minutes\) is plotted in a bar graph against time.

The duration covered by a bar is:

-   One hour when *Past Day* is selected as *Time* 

-   One day when *Past Week* or *Past Month* is selected as *Time* 


The level of usage is indicated by the bar height and color \(from green for low usage, up to red for critical usage\).


<table>
<tr>
<th valign="top">

Level of Usage

</th>
<th valign="top">

Bar Color

</th>
<th valign="top">

Database Transaction Usage

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

Maximum duration: more than 30 minutes

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

Maximum duration: between 5 minutes and 30 minutes

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

Maximum duration: less than 5 minutes

</td>
</tr>
</table>

On the *Database Transactions* screen, you can find more details.

Section *Top Integration Flows by Usage* shows the maximum duration of database transactions for those integration flows that are identified as using the longest running transactions of the tenant database for a specific time period \(as selected by the *Time* parameter\).

Click a cell to display more context information for the selected integration flow \(result filtered according to the setting of the *Time* parameter\).

See: [Inspect Top Integration Flows by Maximum Transaction Duration](inspect-top-integration-flows-by-maximum-transaction-duration-ab67942.md)

> ### Note:  
> The system reads the resource consumption once per hour. That means, that there can be a maximum lag of 1 hour between the processing of an integration flow with a certain transaction setting and the *Inspect* feature to show the impact of this integration flow.



<a name="loio6736a3726760451bab9b07017df65616__section_dfd_lqt_4xb"/>

## What to Do in Critical Situations

If there are integration flows exhibiting transaction durations at warning or even critical level, check your top consuming integration flows. In particular, check the *Transaction Handling* parameter \(when the *Integration Process* or *Local Integration Process* shape is selected in the integration flow model\). Check if *Required for JDBC* is selected and, if it is, check if you can choose another option.

More information:

-   [Define Proper Transaction Handling](define-proper-transaction-handling-1c31963.md)

-   [Transaction Handling Guidelines](transaction-handling-guidelines-52e3f67.md)

-   [Define Transaction Handling](define-transaction-handling-2a5d4bc.md)


