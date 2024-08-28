<!-- loio80f3050fb26e42a6b09dfcdb06f8cd50 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Diagnostics

Run diagnostic tasks and collect the necessary information for troubleshooting your Edge Integration Cell.



<a name="loio80f3050fb26e42a6b09dfcdb06f8cd50__section_im3_4gp_hcc"/>

## Prerequisites

A file system is required in order to use *Diagnostics*. This is because the information collected by the diagnostic tasks is stored in the file system. If you didn't enable the file system during the installation of your Edge Integration Cell , you need to reinstall it and choose the *Enable Shared File System*option. For more information, see [Deploy the Edge Integration Cell Solution](deploy-the-edge-integration-cell-solution-ab81b84.md).



<a name="loio80f3050fb26e42a6b09dfcdb06f8cd50__section_nh4_hhp_hcc"/>

## Diagnostic Tasks

You can access *Diagnostics* through the *Quick Links* card on the Operations Cockpit.

When you experience a problem with your system, SAP Support requires diagnostic data to troubleshoot your issue. You can collect this information by running a diagnostic task.

*Diagnostics* allows you to create new diagnostic tasks and delete previous ones.

> ### Note:  
> You can only run one diagnostic task at a time. Make sure to stop any currently running tasks before starting a new one.

The main table displays a list of previous diagnostic tasks, and shows the following information:


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

*Start Time*

</td>
<td valign="top">

The date when the diagnostics session was initiated.

</td>
</tr>
<tr>
<td valign="top">

*Type*

</td>
<td valign="top">

The type of diagnostic task. It can be any of the following:

-   *Custom Logging*. Temporarily increase the log level for a list of log locations and collect the required debug information for diagnosing your issue.




</td>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

The name of the diagnostic task.

</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

The status of the diagnostic session. It can be either *Completed* or *Running*.

</td>
</tr>
<tr>
<td valign="top">

*Started By* 

</td>
<td valign="top">

The user who ran the diagnostic task.

</td>
</tr>
<tr>
<td valign="top">

*Actions*

</td>
<td valign="top">

Depending on the status of the diagnostic task, you can either *Download* the diagnostic results or *Stop* running the diagnostic session.

</td>
</tr>
</table>

To create a new diagnostic task, perform the following steps:

1.  Choose *Create Diagnostic Task* and select the required diagnostic type from the dropdown list.
2.  Add the relevant information that SAP Support provided for your diagnostic task and choose *Run*. A new diagnostic session starts in the Edge Integration Cell, and the new task is displayed in the *Diagnostics* table with the status *Running*.
3.  While the diagnostic session is running, reproduce the problem you want to diagnose in parallel. This action writes debugging information to the log files on the file system, allowing *Diagnostics* to collect the relevant data for troubleshooting.
4.  When you're done, choose *Stop* to finish the session. The status changes to *Completed*, and the download button becomes available.

    > ### Note:  
    > If you don't stop the session manually, it stops automatically after 10 minutes.

5.  You can now download the results of your diagnostic task. The results save as a zip file on your computer.


> ### Tip:  
> Delete old diagnostic tasks regularly to save space on the file system. You can select one or multiple items from the*Diagnostic Task* list and choose the *Delete* icon.



<a name="loio80f3050fb26e42a6b09dfcdb06f8cd50__section_xds_1jp_hcc"/>

## Custom Loggers

You can add custom loggers when creating a new custom logging task. You can either add them individually or mass import a list of loggers.

To add them individually, follow these steps:

1.  Choose the add \(:heavy_plus_sign:\) icon in the popup window that opens when you create a new logging task.
2.  Specify the *Component* and *Log Level*, and provide the *Log Location*.
3.  Choose the *Add* button to add the custom logger. You can repeat the previous steps to add all the custom loggers you need.
4.  When you're done, you can choose *Run* to initiate the diagnosis.

To mass import a list of loggers, choose the import \(<span class="SAP-icons-V5"></span>\) icon in the popup window that opens when you create a new logging task. Paste your list of loggers in the *Custom Logger* field. Make sure that you enter one log location per line and that the data follows this format: <Component\>,<Log Location\>,<Log Level\>. T The system adds each new location to the custom logger and overwrites any matching existing locations.

> ### Note:  
> For mass import, the component should have an internal name, such as edge-api. The supported log levels are *TRACE*, *DEBUG*, *INFO*, *WARNING*, *ERROR*, and *OFF*.

You can edit and delete your custom loggers later by choosing the respective icons next to the logger you want to modify.

