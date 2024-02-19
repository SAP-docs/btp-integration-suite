<!-- loioc47533bdfc764d3ea40ed70f773c3c26 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Update MIGs/MAGs

Update the MIG/MAG detail in your Agreement transaction.

This function allows you to update the MIG/MAG version for a group of Agreements. There could be scenarios where a new version of a MIG/MAG is created and more than one Agreement update is needed. This function provides you with a seamless way of performing the update. Follow the procedure below.

1.  Login to your application.

2.  Navigate to *B2B Scenarios* \> *Design*.
3.  Choose the *Cross Actions* tab and select *Update MIGs/MAGs*.
4.  The *Choose Action* dialog box allows you to choose between updating a MIG or a MAG.
5.  Choose *Update MIG* if you want to update the MIG version and choose *Update MAG* if you want to update the MAG version in the Agreements.



<a name="loioc47533bdfc764d3ea40ed70f773c3c26__section_ty3_l4t_yxb"/>

## Update MIG

If you chose *Update MIG*,

1.  Enter a meaningful name in the *Action Name* field.

2.  Provide a description in the *Description* field and choose *Create*.
3.  In the next step, select the current MIG using the value help <span class="SAP-icons-V5"></span> under the *Current MIG* section.
4.  The value help allows you to search and filter your MIG based on the name, version and status. After selecting a MIG from the list, choose *Select*.
5.  Select the version from the drop-down list provided next to the MIG name.
6.  The *MIG Version* field under the *Target MIG* section gets auto-filled with the MIG name. You need to choose the target MIG version from the drop-down list.
7.  Choose *Next*.
8.  The next screen allows you to select the impacted Agreements to be updated. Choose *Go* to view all the impacted agreements.

    > ### Note:  
    > You can also filter the Agreements further by their status, trading partner details and timestamps. After maintaining the necessary filters, choose *Go* to see the results.

9.  In the *Agreements* table, select the Agreements that require the MIG version update and choose *Next*.
10. The next step displays a summary of your selection. Choose *Finish* to execute the update.
11. The *Actions Logs* table displays the progress of your task. Choose and open your log to view the task in detail.



<a name="loioc47533bdfc764d3ea40ed70f773c3c26__section_m2s_3n5_yxb"/>

## Update MAG

If you chose *Update MAG*,

1.  Enter a meaningful name in the *Action Name* field.

2.  Provide a description in the *Description* field and choose *Create*.
3.  In the next step, select the current MAG using the value help <span class="SAP-icons-V5"></span> under the *Current MAG* section.
4.  The value help allows you to search and filter your MAG based on the name, version and status. After selecting a MAG from the list, choose *Select*.
5.  Select the version from the drop-down list provided next to the MAG name.
6.  The *MAG Version* field under the *Target MAG* section gets auto-filled with the MAG name. You need to choose the target MAG version from the drop-down list.
7.  If the target MAG version that you chose contains a different version of MIG references and if you want to include the MIG references update, select the *Include MIG Versions Update* radio button. Or choose *Keep Current MAG Version*.
8.  Choose *Next*.
9.  The next screen allows you to select the impacted Agreements to be updated. Choose *Go* to view all the impacted agreements.

    > ### Note:  
    > You can also filter the Agreements further by their status, trading partner details and timestamps. After maintaining the necessary filters, choose *Go* to see the results.

10. In the *Agreements* table, select the Agreements that require the MAG version update and choose *Next*.
11. The next step displays a summary of your selection. Choose *Finish* to execute the update.
12. The *Actions Logs* table displays the progress of your task. Choose and open your log to view the task in detail.

