<!-- loiob5e1fc90bfd5471ca332d54e119faeba -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitoring B2B Messages

The Business to Business \(B2B\) Monitoring view allows you to check the processing status of your B2B interchanges.

An interchange is the incoming payload for B2B transactions. It is a bulk message or a functional group, which is a special case of a bulk message. Follow the next procedure to access the monitoring tab:

1.  Log on to yourIntegration Suite .
2.  Choose *Monitor* \> *B2B Scenarios*
3.  The monitoring section opens with two tiles
    -   Interchanges

    -   Unassigned Interchanges

4.  Choose *Interchanges* to open the *Standard* monitoring view.

    This will open the list of message transactions that happened during the last 24 hours.

5.  The filter options are available in the first part of the screen. You can filter for a particular interchange using these filter options.

    > ### Note:  
    > Choose *Custom* from the *Interchange Creation Date Time* field dropdown if you want to access messages that were created between a specific time period.

6.  You can filter the messages using their payload archiving status using the *Archiving Status* field.
7.  If you want to customise your filter options, choose *Adapt Filters*.
8.  In the resulting dialog box, select or unselect fields depending on your preference and choose *OK*.

    > ### Note:  
    > If you had defined any custom search attributes in your active agreements, they will appear in *Adapt Filters* dialog. Select them if you want to customise your search option.

9.  You can also save your customised filter options using the *Save As* option provided under the down <span class="SAP-icons-V5"></span> icon after the title *Standard\**.
10. You can also export the interchanges in Excel format using the <span class="SAP-icons-V5"></span> icon provided proceeding the list.
11. Choose and open an interchange from the *Interchanges* list.
12. The *Error Information* tab provides additional error information for the failed interchanges. Choose *Details* to access more information about the error.
13. If there are any issues with the agreement configuration, the *Error Information* tab provides a *Check Agreements* option. Select it to review the agreement details.
14. The *Used Agreement Data in Message* section provides the Partner Directory information of the interchange.
15. The corresponding transaction activities are listed in the *Valid Agreements* table. You can also filter the table details using the filter option provided by selecting the column header. Choose *Close* after viewing the details.
16. The *General* tab of your interchange displays the following information
    1.  General Information

    2.  Custom Attributes \(if defined in the agreement transaction\)
    3.  Sender
    4.  Receiver

17. The *Events* tab displays the list of business transaction events with the following details
    1.  *ID* 

        Provides the unique identification number for the event

    2.  *Type* 

        Displays the type of the event

    3.  *Date* 

        Time when the event was created

    4.  *Monitoring Reference*

        Provides you a reference link to the message details


18. Choose the link provided under *Monitoring Reference* for an event. It displays the message processing details of the integration flow involved in the transaction in a new window.
19. The *Interchange Payload* tab displays the payload file of the interchange. You can choose to open either the sender or receiver payload from the drop-down list provided in the *Version* field.
20. Choose *Download* <span class="SAP-icons-V5"></span> provided after the *Version* field if you want to download the interchange payload.
21. Navigate to the *Unassigned Interchanges* tile after the *Monitor* tab.
22. This tile displays the interchanges that resulted in an error early during the processing.
23. You can also filter the unassigned interchanges based on
    -   Error Date Time

    -   Error Category
    -   Error Information
    -   MPL ID

24. Set the filter based on your requirements and choose *Go*.
25. Choose and open an interchange from the list.
26. You can review the details of the error in the resulting dialog. The link after *Message Processing Log ID* displays the error log details of the integration flow involved in the transaction.



<a name="loiob5e1fc90bfd5471ca332d54e119faeba__section_hqr_bb5_3sb"/>

## Contact SAP Support

You can report an incident or error through the [SAP Support Portal](https://support.sap.com/en/index.html). Please use the following component for your incident:

**Ticket Component**


<table>
<tr>
<th valign="top">

Component Name

</th>
<th valign="top">

Component Description

</th>
</tr>
<tr>
<td valign="top">

LOD-HCI-PI-TPM

</td>
<td valign="top">

B2B Scenarios with Trading Partners

</td>
</tr>
</table>

