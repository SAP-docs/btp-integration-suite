<!-- loioc47533bdfc764d3ea40ed70f773c3c26 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Update MIG Version

Update the MIG detail in your Agreement transaction.



<a name="loioc47533bdfc764d3ea40ed70f773c3c26__context_t3x_qnq_pcc"/>

## Context

This function allows you to update the MIG version for a group of Agreements. There could be scenarios where a new version of a MIG is created and more than one Agreement update is needed. This function provides you with a seamless way of performing the update. Follow the procedure below to update the MIG version.



<a name="loioc47533bdfc764d3ea40ed70f773c3c26__steps_xbr_5nq_pcc"/>

## Procedure

1.  Enter a meaningful name in the *Action Name* field.

2.  Provide a description in the *Description* field and choose *Create*.

3.  In the *Select MIG* step you need to choose the MIG for which the version detail has to be updated. Under *Current MIG Version* section, select the current MIG using the value help <span class="SAP-icons-V5"></span> for the *MIG Version* field.

4.  The value help provides you with the following filter options to use and find your MIG:

    -   Name

    -   MIG Version
    -   Status
    -   Type System
    -   Type System Version
    -   Message Type

    Set the necessary filters and choose *Go*.

5.  Select a MIG from the filtered result and choose *Select*.

6.  Now, select the version from the drop-down list provided next to the MIG name.

7.  The *MIG Version* field under the *Target MIG* section gets auto-filled with the MIG name you chose in Step 5. You need to now choose the target MIG version from the drop-down list.

8.  Choose *Next*.

9.  In the *Agreements* step, you need to select the agreements to get their business transactions updated with the target MIG version. Select the checkbox of the field *Update MIG information in source templates* if you want to update the MIG information in the corresponding agreement templates.

10. The *Filters* section contains auto-filled values for the field *MIG Version*. This value is obtained from the previous step to filter agreements based on the MIG you chose. Choose *Go* to view all the agreements that use the selected MIG in their business transactions.

    You can also filter the Agreements further by their status, trading partner details and timestamps.

11. The *Agreements* table displays the agreements based on the set filter criteria. Select the Agreements that require the MIG version update and choose *Next*.

12. The *Review* step displays a summary of your selection. Choose *Finish* to execute the update.

13. The *Actions Logs* table displays the progress of your task. Choose and open your log to view the task in detail.


