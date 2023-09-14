<!-- loio567eb42ef7c349e78c8c814dfeecd696 -->

# Inspect Database Connection Usage

Inspect database connection usage for a given time period and analyze critical situations in which insufficient database connections are available.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Cloud Foundry environment.

> ### Tip:  
> Each SAP Cloud Integration tenant is associated with a physical database that has a limited size. This database is used by certain steps during the runtime of integration flows .

Every integration flow step that implies access to the tenant database requires a database connection. This number of available database connections is a limited integration resource.

Database connection usage depends on the integration flow design and on the volume of the processed data. There can also be situations where not enough connections are available. Furthermore, the configured transaction handling settings have an effect on database connection usage.

You can change the displayed time period be selecting a different option in the dropdown box under *Time*.

The database connection usage \(in percent\) is plotted in a bar graph against time.

The bar height shows usage in percentage of the maximum usage.

The duration covered by a bar is:

-   One hour when *Past Day* is selected as *Time* 

-   One day when *Past Week* or *Past Month* is selected as *Time* 


Maximum usage corresponds to the situation where all database connections are used.

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

A green bullet represents the number of successful attempts to connect to the database \(and reflects how actively the database is being used\)

A red bullet indicates a situation where the Cloud Integration runtime can't get any database connections \(because no free database connection is available\).

Click a bullet to display the number of failed database connection attempts.

Click a bar or a bullet to get access to the following functions \(results are filtered according to the setting of the *Time* parameter\):

-   *Show Messages*

    Inspect the message processing log for the selected time interval.

    Opens the *Monitor Message Processing* screen for the selected time period \(see [Monitor Message Processing](monitor-message-processing-314df3f.md)\).

-   *Inspect Usage*

    Inspect database connection usage per integration flow.

    Opens the *Database Connections* screen that allows you to inspect database connection resources in more detail.


*Zoom Out* and *Zoom In* to extend/reduce the selected time period.

> ### Note:  
> The system reads the resource consumption once per hour. That means, that there can be a maximum lag of 1 hour between the processing of an integration flow consuming database connections and the *Inspect* feature to show the impact of this integration flow.



<a name="loio567eb42ef7c349e78c8c814dfeecd696__section_tqd_3w1_bxb"/>

## Database Connections

On the *Database Connections* screen, you can find more details and functions in the following sections:


<table>
<tr>
<th valign="top">

Section



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*Top Integration Flows by Database Connection Usage* 



</td>
<td valign="top">

Shows the database connection usage for those integration flows that are identified as top consumers of the database connection pool for a given time period \(as selected with the *Time* parameter\).

See: [Inspect Top Integration Flows by Database Connection Usage](inspect-top-integration-flows-by-database-connection-usage-79c5a05.md)



</td>
</tr>
<tr>
<td valign="top">

*Integration Flows Affected by Unavailable Connections* 



</td>
<td valign="top">

Shows integration flows that cause critical database connection load \(unavailable connections\) for a given time period \(as selected with the *Time* parameter\).

> ### Note:  
> This section only shows content if the time filter is set so that in the associated time period, critical load situations are associated with at least one integration flow.

See: [Inspect Integration Flows Affected by Unavailable Connections](inspect-integration-flows-affected-by-unavailable-connections-5d9d214.md)



</td>
</tr>
</table>



<a name="loio567eb42ef7c349e78c8c814dfeecd696__section_vgy_pw5_ywb"/>

## What to Do in Critical Situations

If there are not enough database connections, check your top consuming integration flows. In particular, check the *Transaction Handling* parameter \(when the Integration Process or Local Integration Process shape is selected in an integration flow model\). Check if *Required for JDBC* is selected and, if it is, check if you can choose another option.

More information:

-   [Define Proper Transaction Handling](../Development/define-proper-transaction-handling-1c31963.md)

-   [Transaction Handling Guidelines](../Development/transaction-handling-guidelines-52e3f67.md)

-   [Define Transaction Handling](../Development/define-transaction-handling-2a5d4bc.md)


