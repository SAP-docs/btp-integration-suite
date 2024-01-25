<!-- loio587a9814f0bc4069be975880a57a815f -->

# Analyze Message Usage

Analyze the number of messages are processed by the active integration flows within a specific time interval.

The result list differentiates between messages that are exclusively exchanged between SAP systems and chargeable messages.

Your user needs an assignment to the following role collections to work with this feature: *PI\_Business\_Expert*, *PI\_Administrator*.

You can analyze the message throughput per integration flow.

> ### Note:  
> You can specify a time interval of up to 31 days for which this analysis should be performed.
> 
> Data for message processing is available at the earliest from the point at which software increment 2310 was deployed on your system.

To open the *Message Usage* dashboard, perform the following steps:

1.  Choose *Monitor* \> *Integrations and APIs*.

    Under *Usage Details*, you can find the tile *Message Usage*.

    This tile displays the selected time range \(for example, *Current Month*\) and the total number of messages processed during this time range.

2.  Click the *Message Usage* tile.


The *Message Usage Dashboard* consists of the following screen areas.

-   The upper left section shows the total number of messages processed during the selected time range. The messages exchanged exclusively between SAP systems \(which are not chargeable\) are separately listed and counted.

    When adapt the date range, the numbers are refreshed accordingly.

    > ### Caution:  
    > Note that when selecting a date range, the maximum allowed number of days is 31.
    > 
    > The system provides data that has been stored within a maximum time interval of one year. For example: If today is January 1, 2024, then for the start date of the time interval you cannot select a date that is earlier than January 1, 2023.

-   The upper right section shows a diagram that visualizes message usage for the selected time range.

    As *Visualization Category*, you can select:

    -   *Integration Flow*

        If selected, a rectangle area chart is shown where each rectangle represents an integration flow. Size and color shade of the rectangle correspond to the number of messages processed by the integration flow. The larger or darker a rectangle, the more messages were processed by the respective integration flow in the selected time period.

        Each integration flow is identified by an ID \(for example, `1a23bcde-4fg5-6h7i-j8h9-....`\).

        > ### Tip:  
        > The integration flows that were active \(deployed\) at any given time are captured. Accordingly, the messages processed by deployed integration flows are counted.
        > 
        > On deployment, a unique artifact ID is generated for an integration flow. A new artifact ID is generated with each deployment process. For that reason, integration flows are indicated by an artifact ID, not be the integration flow name.

        On clicking a rectangle, in the *Integration Flow Details* view more details on message usage are shown for the selected integration flow and the date range.

    -   *Date*

        If selected, a bar chart is shown \(each bar representing a day within the selected time range\). The height of the bar corresponds to the number of messages processed during the time interval.

        On clicking a bar, in the *Integration Flow Details* view more details on message usage are shown for the day selected in the bar diagram.


-   The bottom *Integration Flow Details* section shows a detailed view of the message usage for a block or bar selected in the diagram above.



<a name="loio587a9814f0bc4069be975880a57a815f__section_utq_qxy_nzb"/>

## Integration Flow Details View

Depending on the chosen *Visualization Category*, a table with the following entries is shown:


<table>
<tr>
<th valign="top">

Visualization category

</th>
<th valign="top">

Content of the Table

</th>
</tr>
<tr>
<td valign="top">

*Integration Flow* 

</td>
<td valign="top">

A list of days \(within the selected time range\) is displayed, in which the selected integration flow processed messages. For each day, one table entry is displayed.

For each table entry, a number of attributes is shown as described below.

</td>
</tr>
<tr>
<td valign="top">

*Date* 

</td>
<td valign="top">

A list of integration flows is displayed that processed messages within the selected day. For each integration flow, one table entry is displayed.

For each table entry, the artifact is, the integration flow name, and the technical integration flow name are shown.

Furthermore, additional attributes are shown as described below.

</td>
</tr>
</table>

The following attributes are displayed for each table entry, independent of the chosen *Visualization Category*:

-   Receivers

    The receivers specified in the integration flow.

-   Splitters

    Splitter steps specified in the integration flow.

-   SAP to SAP \(Excluded\)

    Indicates if the integration flow exchanges messages between SAP systems only. If that's the case, these messages are not charged.

-   JMS or Datastore Retry

    If JMS queues or data stores are included in the integration flow, message retries can happen. The number of retries is shown here.

-   Total Messages

    The total number of messages represented by this table entry.

-   MPL Count

    The number of message processing logs.


You can download the complete list to your computer as an Excel file.

For each entry in the table, you can display more details. You also have the option to download the details for a selected entry to your computer as an Excel file.

The Excel list contains additional information for each entry such as, for example, if the following integration flow steps are involved: Looping Process Call, Content Enricher.

> ### Caution:  
> If you download data from the *Integration Flow Details* screen, the size of the Excel file is limited to 50000 entries. If a warning is displayed that this limit has been exceeded, adjust the time range filter accordingly, and attempt the download again.

> ### Tip:  
> For more information on how messages are defined and metered, see [2942344](https://me.sap.com/notes/2942344).

