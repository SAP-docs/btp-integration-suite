<!-- loio587a9814f0bc4069be975880a57a815f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Analyze Message Usage

Analyze the number of messages that are processed by the active integration flows within a specific time interval. You can analyze the message throughput per integration flow.

The result list differentiates between messages that are exclusively exchanged between SAP systems and chargeable messages.



## Prerequisite

To utilize this feature the following role collections must be assigned to the user:

-   *PI\_Business\_Expert*
-   *PI\_Administrator*

> ### Note:  
> Data for message processing is available at the earliest from the point at which software increment 2310 was deployed on your system.



## Procedure

To utilize the *Message Usage* dashboard, perform the following steps:

1.  Choose *Monitor* \> *Integrations and APIs*.

    Under *Usage Details*, you can find the *Message Usage* tile.

    This tile displays the *Current Month* and the total number of messages processed during this time range.

2.  Choose *Message Usage* tile.

    *Message Usage Dashboard* consists the following sections:

    -   The upper left section shows the total number of messages processed during the selected time range. The messages exchanged exclusively between SAP systems \(which are not chargeable\) are separately listed and counted.
    -   The upper right section shows a diagram that visualizes message usage for the selected time range.
    -   The bottom *Integration Flow Details* section shows the details of the following:
        -   Consolidated view of message usage for the *Current Month* or selected date range.

        -   Message usage for a block or bar selected in the graph.



3.  Choose the required date range.

    > ### Caution:  
    > Maximum date range selection allowed is 31 days.
    > 
    > The system provides data that has been stored within a maximum time interval of one year. For example: If today is January 1, 2024, then for the start date of the time interval you cannot select a date that is earlier than January 1, 2023

4.  Select one of the visualization categories.


    <table>
    <tr>
    <th valign="top">

    Visualization Category
    
    </th>
    <th valign="top">

    Content of the Table
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Date Range* 
    
    </td>
    <td valign="top">
    
    A bar chart is shown \(each bar representing a day within the selected time range\). The height of the bar corresponds to the number of messages processed during the time interval.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Integration Flow* 
    
    </td>
    <td valign="top">
    
    A rectangle area chart is shown where each rectangle represents an integration flow. Size and color shade of the rectangle correspond to the number of messages processed by the integration flow. The larger or darker a rectangle, the more messages were processed by the respective integration flow for the selected time period.

    Each integration flow is identified by an ID \(for example, 1a23bcde-4fg5-6h7i-j8h9-....\).

    > ### Tip:  
    > The integration flows that were active \(deployed\) at any given time are captured. Accordingly, the messages processed by deployed integration flows are counted.
    > 
    > On deployment, a unique artifact ID is generated for an integration flow. A new artifact ID is generated with each deployment process. Hence, integration flows are indicated by an artifact ID, not be the integration flow name.


    
    </td>
    </tr>
    </table>
    
    A graph is represented with the details along with the consolidated view in the *Integration Flow Details* view.

5.  \(Optional\) On the *Integration Flow Details* view, choose :gear: and select the required attributes or fields to view them in the table.

    Depending on the chosen *Visualization Category* and attribues, a table with following entries will be shown:


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Artifact ID* 
    
    </td>
    <td valign="top">
    
    Artifact ID specified in the integration flow.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Integration Flow Name and ID* 
    
    </td>
    <td valign="top">
    
    Integration flow name and its ID.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Package Name and ID* 
    
    </td>
    <td valign="top">
    
    Integration package available in the integration flow and its ID.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Receivers* 
    
    </td>
    <td valign="top">
    
    Receivers specified in the integration flow.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Splitters* 
    
    </td>
    <td valign="top">
    
    Splitter steps specified in the integration flow.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *SAP to SAP \(Excluded\)* 
    
    </td>
    <td valign="top">
    
    Indicates if the integration flow exchanges messages between SAP systems only. If that's the case, these messages are not charged.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *JMS or Datastore Retry* 
    
    </td>
    <td valign="top">
    
    If JMS queues or data stores are included in the integration flow, message retries can happen. The number of retries is shown here.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Total Messages* 
    
    </td>
    <td valign="top">
    
    The total number of messages represented by this table entry.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *MPL Count* 
    
    </td>
    <td valign="top">
    
    The number of message processing logs.
    
    </td>
    </tr>
    </table>
    
6.  Select a rectangle or bar on the graph to view the details of a particular flow or date.

    Details of messages processed by the selected flow or date are shown in the table. To understand the attributes of the table, refer to [step 5](analyze-message-usage-587a981.md#loio587a9814f0bc4069be975880a57a815f__step_5).

7.  Choose *Download*.

    > ### Note:  
    > The downloaded excel file contains additional information for each entry. If the following integration flow steps are involved: Looping Process Call and Content Enricher.

    > ### Caution:  
    > If you download data from the *Integration Flow Details* screen, the size of the Excel file is limited to 50000 entries. If a warning is displayed that this limit has been exceeded, adjust the date range accordingly, and download again.

    > ### Tip:  
    > For more information on how tenant is defined and metered, see [3654389](https://me.sap.com/notes/3654389)


