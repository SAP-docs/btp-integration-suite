<!-- loio4146fa5f2d094ea9820e82c53790fe86 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Job Management

Organize and schedule your existing system jobs, and add new jobs manually.



<a name="loio4146fa5f2d094ea9820e82c53790fe86__section_ezf_zpb_ycc"/>

## Context

You can perform the following types of jobs, also refereed to as *Actions*:

-   *Cleanup Data Store Entries*. Delete data store entries that have reached the retention time.

-   *Cleanup Monitoring Data*. Clean up monitoring data by deleting message processing log \(MPL\) data for messages in their final state. You can also delete the aggregated data of tenants if the creation date is within the specified number of days from the command's execution date.

-   *Cleanup Trace Entries*. Delete trace messages that have reached the retention time.

-   *Cleanup Diagnostic Data*. Delete manually created diagnostic tasks and automatically generated heap dumps. This job also deletes empty working directories that were created by the Worker component on the shared file system but are no longer in use.

Per default, *Cleanup Data Store Entries*, *Cleanup Monitoring Data*, and *Cleanup Trace Entries* are scheduled during the installation time. However, you must schedule *Cleanup Diagnostic Data* manually.

The overview screen shows a list of all your existing jobs. For each of the jobs, the following information is available:

**Table Overview**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

The name of the system job.

</td>
</tr>
<tr>
<td valign="top">

*Last Changed By*

</td>
<td valign="top">

Information on which user last edited the job.

> ### Note:  
> `SYSTEM_USER` is the default user for the jobs scheduled at installation.



</td>
</tr>
<tr>
<td valign="top">

*Last Changed On*

</td>
<td valign="top">

Information on when this job was last edited. The format specifies the date and time down to minutes.

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

Information on when this job was last executed. The format specifies the date and time down to minutes.

</td>
</tr>
<tr>
<td valign="top">

*Next Execution Time*

</td>
<td valign="top">

Information on when this job is to be executed next. The format specifies the date and time down to minutes. The date is calculated based on defined schedule settings.

</td>
</tr>
</table>

For more information on the parameters and schedule pattern for each job, select one job from the list and the details view opens. You can choose **Delete** to delete an existing job and **Edit** to make changes to an existing job.

> ### Note:  
> Depending on the job, you can edit **Parameters** and/or **Schedule**. The general information, such as **Name** and **Actions**, can't be changed.



<a name="loio4146fa5f2d094ea9820e82c53790fe86__section_nhn_dqb_ycc"/>

## Procedure

To add a new job, select :heavy_plus_sign: \(Add\). Depending on the **Action** you select, you need to define different parameters:


<table>
<tr>
<th valign="top">

*Action*

</th>
<th valign="top">

*Parameters*

</th>
<th valign="top">

*Description*

</th>
</tr>
<tr>
<td valign="top">

*Cleanup Monitoring Data*

</td>
<td valign="top">

-   *Delete Processing Log Data for Completed Messages Older Than \(Days\)*
-   *Delete Monitoring Data Older Than \(Days\)*



</td>
<td valign="top">

Enter the number of days.

</td>
</tr>
<tr>
<td valign="top">

*Cleanup Trace Entries*

</td>
<td valign="top">

*Delete Trace Data Older Than \(Minutes\)* 

</td>
<td valign="top">

Enter the number of days. The default is set to `60`.

</td>
</tr>
<tr>
<td valign="top">

*Cleanup Data Store Entries*

</td>
<td valign="top">

No parameters.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*Cleanup Diagnostic Data*

</td>
<td valign="top">

*Delete Data Older Than \(Days\)* :

</td>
<td valign="top">

Enter the number of days. The default is set to `30`.

</td>
</tr>
</table>

Enter the following information for *Schedule*:

**Schedule**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
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

-   Fixed Time. The job executes at the specific time you select.

-   Recurrence. The job executes regularly at the time interval you select.




</td>
</tr>
<tr>
<td valign="top">

*Every* 

\(only available if *Schedule Type* *Recurrence* is set\)

</td>
<td valign="top">

Select a time period.

</td>
</tr>
<tr>
<td valign="top">

*Between*

\(only available if *Schedule Type* *Recurrence* is set\)

</td>
<td valign="top">

Specify the hours in which this job is to run between `00:00` and `24:00`.

</td>
</tr>
<tr>
<td valign="top">

*Schedule Time*

\(only available if *Schedule Type Fixed Time* is set\)

</td>
<td valign="top">

Define the time when the job is to run.

</td>
</tr>
</table>

**Related Information**  


[Operations Cockpit](operations-cockpit-ec0fc95.md "The Operations Cockpit is the central control point for operating edge integration cells and allows the Edge Integration Cell administrator to monitor and adjust system configurations and resources.")

[Component Monitor](component-monitor-49f487e.md "Get information on your components.")

