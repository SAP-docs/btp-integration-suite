<!-- loioaac82bdba26f45e186fd1b944c8be4f4 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitoring System Log Files, Neo Environment

This section contains information on system log files. These log files can be either HTTP access files or default trace files.

> ### Note:  
> This information is relevant only when you use SAP Cloud Integration in the Neo environment.

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

You view the system log files by clicking *System Log Files* in the *Access Logs* area.

You can retrieve the following information from the system log file list:

**Log Files**


<table>
<tr>
<th valign="top">

Attributes



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

Displays the log file name



</td>
</tr>
<tr>
<td valign="top">

*Log Type* 



</td>
<td valign="top">

Displays 2 different log types the CP default trace or the HTTP access log



</td>
</tr>
<tr>
<td valign="top">

*Updated At* 



</td>
<td valign="top">

Displays the date of the last update



</td>
</tr>
<tr>
<td valign="top">

*Size* 



</td>
<td valign="top">

Displays the file size



</td>
</tr>
<tr>
<td valign="top">

*Actions* 



</td>
<td valign="top">

You can either download the file by selecting <span class="SAP-icons"></span> or get the URL by selecting <span class="SAP-icons"></span>.



</td>
</tr>
</table>

You can filter the log files by names and sort the list either by *Name*, *Updated At*, or file *Size*. You can either download a specific file or get the file URL. The file URL allows you to send it per mail to allow further analysis on another computer for example. In both cases, the system provides a packed log file \(.zip file\).

> ### Note:  
> The log file retention time is 7 days.

If you select *Collections*, you get the most recent log files for each runtime node. You can either download the collection or get the URL and in both cases the system provides packed log files \(.zip files\).

