<!-- loio5ce5ce5a3f4a458c9d0e1e3a1bc1f2a6 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Heap Dumps

Run heap dump diagnostic tasks to diagnose issues related to memory consumption.



<a name="loio5ce5ce5a3f4a458c9d0e1e3a1bc1f2a6__section_izb_rzb_m2c"/>

## Context

You can perform heap dumps on your components to obtain reports necessary for memory analysis.

> ### Restriction:  
> You can only create a heap dump for one pod per component at a time, as this operation is resource-intensive.

In the main *Diagnostics* table, you can find some *Automatically Generated Head Dumps*. This is because the Worker component is configured to automatically create a heap dump when an OutOfMemory situation occurs and the Java VM crashes. These heap dumps are then automatically written into the shared file system.



<a name="loio5ce5ce5a3f4a458c9d0e1e3a1bc1f2a6__section_tk5_rzb_m2c"/>

## Head Dump Analysis

Run a *Heap Dump Analysis* to identify memory leaks and analyze memory consumption. For tasks in the *Created* or *Error* state, choose the *Start Analysis* action to start the *Heap Dump Analysis*.

You can also run the analysis subsequently when creating a new heap dump diagnostic task. Follow this procedure to do so:

1.  Choose *Create Diagnostic Task* and select *Heap Dump* from the dropdown list.
2.  In the new dialog box, add the relevant information that SAP Support provided for your diagnosis.
3.  Use the *Subsequent Heap Dump Analysis* switch to decide whether to run an analysis automatically after the dump. By default, this switch is *on*. You can switch off the subsequent analysis and still have the option to run it later.

    > ### Note:  
    > Subsequent heap dump analysis isn't available for Go components. Therefore, a heap dump task for *Edge Deploy Controller* moves directly into status *Completed* and you can't start any analysis for it.

4.  Choose *Run*.
5.  A new diagnostic session starts in your Edge Integration Cell, and a Kubernetes job creates in the background. The new task appears in the *Diagnostics* table with the status *Analysis Starting* .
6.  The analysis is running, with the status *Analysing* .
7.  When the status changes to *Completed*, the download button becomes available.
8.  You can now download the results of your diagnostic task. The results save as a zip file on your computer. You get a report about the general overview of the heap dump and the leak suspects.

    > ### Note:  
    > You can still download the raw heap dumps via the shared file system. You can view the corresponding path on the file system in *Details*.


> ### Note:  
> While only one diagnostic task can run at a time, analysis occurs as a subsequent background action. Therefore, multiple heap dumps can undergo analysis simultaneously, and you can also start another diagnostic task while the analysis is running.



<a name="loio5ce5ce5a3f4a458c9d0e1e3a1bc1f2a6__section_ajp_z33_m2c"/>

## Statuses and Actions

Head dumps can have special statuses and actions compared to other diagnostic tasks.


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

*Status*

</td>
<td valign="top">

-   **Running**: A heap dump is being created.
-   **Created**: No analysis has been run for these heap dump tasks yet.
-   **Analysis Starting**: The corresponding Kubernetes job launches in the background.

    > ### Note:  
    > For automatic heap dumps, the heap dump is first moved to a different folder. Due to this copying activity, you might briefly see two heap dump diagnostic tasks with the same start time but different statuses, *Created* and *Analysis Starting*. The *Created* status disappears once the second task's status changes to *Analysing*.

-   **Analysing**: The actual analysis of the heap dump is running. The corresponding Kubernetes job has limited resources, so this step can take time. The duration also depends on the size of the heap dump.
-   **Completed**: The analysis is done, and results are available for download.
-   **Error**: An error occurred during the analysis. You can choose the <span class="SAP-icons-V5"></span> information icon next to the status to view details about the error



</td>
</tr>
<tr>
<td valign="top">

*Action*

</td>
<td valign="top">

-   *Start Analysis*: Initiate the analysis of the heap dump. This action is only available for tasks in state *Created* and *Error*.

-   *Stop*: Cancel the analysis for tasks in state *Analysis Starting* or *Analysing*.

-   *Download*: Download a zip file containing two other zips, ‘Leak Suspect’ and ‘System Overview’ analysis results. This is the default action for head dumps in status *Completed*.
-   *Details*: Access *Details* by selecting the three dots. This action opens a dialog box which displays information about the task, including the path to the raw heap dump. You can download the results file using your preferred Kubernetes tools. The corresponding command is the following:

    `kubectl -n edge-icell cp <pod name>:<path> <destination path name>`




</td>
</tr>
</table>

**Related Information**  


[Diagnostics](diagnostics-80f3050.md "Run diagnostic tasks and collect the necessary information for troubleshooting your Edge Integration Cell.")

