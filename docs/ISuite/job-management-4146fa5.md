<!-- loio4146fa5f2d094ea9820e82c53790fe86 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Job Management

Organize and schedule your existing system jobs, such as data store entries cleanup or trace entries cleanup, or add jobs manually.

Per default, this screen shows three scheduled jobs related to the system. These are defined as *Actions*:

-   *Cleanup Data Store Entries*

-   *Cleanup Monitoring Data*

-   *Cleanup Trace Entries*


For each of the jobs, the following information is available:

**Table Overview**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Information

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Name of the system job.

</td>
</tr>
<tr>
<td valign="top">

*Last Changed By*

</td>
<td valign="top">

Information on which user last edited the job.

Per default, `SYSTEM_USER` is set.

</td>
</tr>
<tr>
<td valign="top">

*Last Changed On*

</td>
<td valign="top">

Information on when this job was last edited. The format specifies date and time down to minutes.

</td>
</tr>
<tr>
<td valign="top">

*Last Execution State*

</td>
<td valign="top">

Information on whether or not this job has run successfully.

-   *Completed*

-   *Failed*

-   *Not yet executed*

-   *Skipped*

-   *Retry*




</td>
</tr>
<tr>
<td valign="top">

*Last Execution Time*

</td>
<td valign="top">

Information on when this job was last executed. The format specifies date and time down to minutes.

</td>
</tr>
<tr>
<td valign="top">

*Next Execution Time*

</td>
<td valign="top">

Information on when this job is to be executed next. The format specifies date and time down to minutes. The date is calculated based on defined schedule settings.

</td>
</tr>
</table>

For more information, for instance on the schedule pattern for each job, select one of the jobs from the list by clicking on it. A details view opens. Select *Delete* to delete an existing job. Select *Edit* to make changes to an existing job. Depending on the job, *Parameters* and / or *Schedule* can be edited. The general information, such as *Name* and *Actions*, that is, the type of job, can't be edited.

Enter the following information for *Parameters*:

**Parameters**


<table>
<tr>
<td valign="top">

Only available for *Cleanup Monitoring Data*

</td>
<td valign="top">

-   *Delete COMPLETED Message Processing Log Data Older Than \(Days\)*: Enter a number representing days.
-   *Delete Monitoring Data Older Than \(Days\)*\(mandatory\): Enter a number representing days. The default is set to `30`.



</td>
</tr>
<tr>
<td valign="top">

Only available for *Cleanup Trace Entries*

</td>
<td valign="top">

*Delete Data Trace From Trace Table Older than \(Minutes\)*: Enter a number representing minutes. The default is set to `60`.

</td>
</tr>
</table>

Enter the following information for *Schedule*:

**Schedule**


<table>
<tr>
<td valign="top">

*Select Schedule*

</td>
<td valign="top">

The following options are available:

-   Daily

-   Monthly on Day

-   Weekly

-   On Date




</td>
</tr>
<tr>
<td valign="top">

*Schedule Type*

</td>
<td valign="top">

The following options are available:

-   Fixed Time

-   Recurrence




</td>
</tr>
<tr>
<td valign="top">

*Every* 

\(only available if for *Schedule Time* *Recurrence* is set\)

</td>
<td valign="top">

The following options are available:

-   1 min

-   5 min

-   10 min

-   15 min

-   20 min

-   30 min

-   1 h

-   2 h

-   4 h

-   6 h

-   12 h




</td>
</tr>
<tr>
<td valign="top">

*Between*

\(only available if for *Schedule Time* *Recurrence* is set\)

</td>
<td valign="top">

Specify the hours in which this job is to run between `00:00` and `24:00`.

</td>
</tr>
<tr>
<td valign="top">

*Schedule Time*

\(only available if for *Schedule Time* *Once* is set\)

</td>
<td valign="top">

Define the time when the job is supposed to run.

</td>
</tr>
</table>

Depending on your use cases, you can add or delete jobs. To add an additional job, select :heavy_plus_sign: \(Add\). In *Create Job*, enter the following details.


<table>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Enter a unique name.

</td>
</tr>
<tr>
<td valign="top">

*Actions*

</td>
<td valign="top">

Choose between:

-   *Cleanup Data Store Entries*

-   *Cleanup Monitoring Data*

-   *Cleanup Trace Entries*


> ### Note:  
> Depending on the type you choose, you have different options for *Parameters* and *Schedule*.



</td>
</tr>
</table>

**Related Information**  


[Operations Cockpit](operations-cockpit-ec0fc95.md "The Operations Cockpit is the central control point for operating edge integration cells and allows the Edge Integration Cell administrator to monitor and adjust system configurations and resources.")

[Component Monitoring](component-monitoring-49f487e.md "Get information on the components.")

