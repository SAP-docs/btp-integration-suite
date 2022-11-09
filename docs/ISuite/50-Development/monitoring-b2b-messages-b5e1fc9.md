<!-- loiob5e1fc90bfd5471ca332d54e119faeba -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitoring B2B Messages

The Business to Business \(B2B\) Monitoring view allows you to check the processing status of your B2B interchanges.

An interchange is the incoming payload for B2B transactions. It is a bulk message or a functional group, which is a special case of a bulk message. Follow the procedure below to access the monitoring tab:

1.  In your Cloud Integration application, choose *B2B Scenarios* <span class="SAP-icons"></span> and navigate to *Monitor* .

2.  The monitoring section opens with two tiles
    -   Interchanges

    -   Unassigned Interchanges

3.  Choose *Interchanges* to open the *Standard* monitoring view.

    This will display the list of message transactions that happened during the last 24 hours.

4.  The filter options are displayed in the upper part of the screen. You can filter for a particular interchange using these filter options.

    > ### Note:  
    > Choose *Custom* under the *Interchange Creation Date Time* field if you want to see messages that were created between a specific time period.

5.  If you want to customise your filter options, choose *Adapt Filters*.
6.  In the resulting dialog box, select or unselect fields depending on your preference and choose *OK*.
7.  You can also save your customised filter options using the *Save As* option provided under the down <span class="SAP-icons"></span> icon next to the title *Standard\**.
8.  Choose and open an interchange from the *Interchanges* list.
9.  The *General* tab of your interchange displays the following details
    1.  General Information

    2.  Sender
    3.  Receiver

10. The *Events* tab displays the list of business transaction events with the following details
    1.  *ID* 

        Provides the unique identification number for the event

    2.  *Type* 

        Displays the type of the event

    3.  *Date* 

        Time when the event was created

    4.  *Monitoring Reference*

        Provides you a reference link to the message details


11. Choose the link provided under *Monitoring Reference* for an event. It displays the message processing details of the integration flow involved in the transaction in a new window.
12. Navigate to the *Unassigned Interchanges* tile under the *Monitor* tab.
13. This tile displays the interchanges that resulted in an error early during the processing. Choose and open an interchange from the list.
14. You can view the details of the error in the resulting screen. The link under the *Message Processing Log ID* displays the error log details of the integration flow involved in the transaction.



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

