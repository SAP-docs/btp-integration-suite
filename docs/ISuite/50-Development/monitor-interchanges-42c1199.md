<!-- loio42c119995c0542d6b367200bddc215c5 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitor Interchanges

Monitor your processed interchanges.



<a name="loio42c119995c0542d6b367200bddc215c5__prereq_mdv_bnq_kfc"/>

## Prerequisites

To work with interchanges, your user must have the correct authorizations. Depending on your needs, you can the correct assign role collections to your user in the SAP BTP cockpit under *Security*:


<table>
<tr>
<th valign="top">

Role Template

</th>
<th valign="top">

Role Collection

</th>
<th valign="top">

Actions

</th>
</tr>
<tr>
<td valign="top">

`B2bInterchangeRead`

</td>
<td valign="top">

`PI_Integration_Developer`, `PI_Read_Only`

</td>
<td valign="top">

Read interchanges without payloads

</td>
</tr>
<tr>
<td valign="top">

`B2bInterchangePayloadRead`

</td>
<td valign="top">

Not included in a role collection

</td>
<td valign="top">

Read interchange payloads

</td>
</tr>
<tr>
<td valign="top">

`B2bInterchangeOperate`

</td>
<td valign="top">

`PI_Business_Expert`

</td>
<td valign="top">

Execute operational tasks on interchanges, such as retry, restart, or cancel

</td>
</tr>
</table>

For details about roles and the tasks and permissions for the different personas, see [Identity and Access Management for Trading Partner Management](../60-Security/identity-and-access-management-for-trading-partner-management-5979108.md).



## Context

An interchange is the incoming payload for B2B transactions. They facilitate the electronic sharing of data such as orders and invoices between trading partners. The **Monitor** tab allows you to:

-   Track interchange status

-   View detailed interchange history
-   Identify errors and resolve exceptions

Follow the procedure to know how to efficiently use the **Monitor** tab to view your interchanges.



## Procedure

1.  Choose *Interchanges* to view the interchange details.

2.  By default, a table with the list of interchanges that were processed in the last 24 hours are displayed on screen. You can modify the list using the filter options provided above the table. There are multiple filter attributes that help you filter your required interchanges:


    <table>
    <tr>
    <th valign="top">

    Attirbute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Status**
    
    </td>
    <td valign="top">
    
    Allows you to filter messages according to their status.

    In the dropdown list you can select one of the following values as the status:

    -   Failed

    -   Retry
    -   Processing
    -   Completed
    -   Waiting for Acknowledgement
    -   Acknowledgement Overdue
    -   Canceled


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Interchange Creation Time**
    
    </td>
    <td valign="top">
    
    Allows you to select from the following predefined time intervals during which the intechanges were created:

    -   All

    -   Past Minute
    -   Past 10 Minutes
    -   Past Hour
    -   Past 24 Hours
    -   Past Week
    -   Past 2 Weeks
    -   Custom

    The *Custom* option allows you to manually set a specific time period.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    From

    > ### Note:  
    > This field is enabled only if you choose *Custom* option for the field *Interchange Creation Time*.


    
    </td>
    <td valign="top">
    
    You can set the interchange creation start date and time using the date-time <span class="SAP-icons-V5"></span> button provided in the field. To select the date, interact with the calendar element and choose a specific day. To select the time, manipulate two separate circles on the watch element to set the desired hour and minute, respectively..
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    To

    > ### Note:  
    > This field is enabled only if you choose *Custom* option for the field *Interchange Creation Time*.


    
    </td>
    <td valign="top">
    
    You can set the interchange creation end date and time using the date-time <span class="SAP-icons-V5"></span> button provided in the field. To select the date, interact with the calendar element and choose a specific day. To select the time, manipulate two separate circles on the watch element to set the desired hour and minute, respectively..
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Error Category**
    
    </td>
    <td valign="top">
    
    You can filter the failed interchanges based on the error category:

    -   Initial Decryption Failed

    -   Signature Validation Failed
    -   Agreement Configuration Access Failed
    -   Interchange Validation Failed
    -   Interchange Mapping Failed
    -   Interchange Transmission Failed
    -   Acknowledgement Overdue
    -   Unspecified Error


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Sender Name**
    
    </td>
    <td valign="top">
    
    Allows you to filter interchanges based on the sender. Use the value help <span class="SAP-icons-V5"></span> button provided in the field to select one or more senders.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Receiver Name**
    
    </td>
    <td valign="top">
    
    Allows you to filter interchanges based on the receiver. Use the value help <span class="SAP-icons-V5"></span> button provided in the field to select one or more receivers.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Interchange Name**
    
    </td>
    <td valign="top">
    
    Allows you to filter for an interchange using the name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Interchange Direction**
    
    </td>
    <td valign="top">
    
    Use the drop-down list to filter interchanges based on the direction:

    -   Unknown

    -   Inbound
    -   Outbound


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Sender Document Standard**
    
    </td>
    <td valign="top">
    
    Allows you to filter for an interchange using the document standard of the sender.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Sender Message Type**
    
    </td>
    <td valign="top">
    
    Allows you to filter for an interchange using the message type of the sender.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Receiver Document Standard**
    
    </td>
    <td valign="top">
    
    Allows you to filter for an interchange using the document standard of the receiver.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Receiver Message Type**
    
    </td>
    <td valign="top">
    
    Allows you to filter for an interchange using the message type of the receiver.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Sender Interchange Control Number**
    
    </td>
    <td valign="top">
    
    Allows you to filter for an interchange using the control number of the interchange.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Archiving Status**
    
    </td>
    <td valign="top">
    
    If you have enabled archiving of the payload, you can filter your interchanges based on their archiving status:

    -   Not Relevant

    -   Archiving Pending
    -   Archived
    -   Failed
    -   Not Archived


    
    </td>
    </tr>
    </table>
    
3.  Choose *Go* after setting the necessary filter to view the filtered interchanges.

4.  Choose *Adapt Filters* to view and add additional filter criteria.

5.  The *Interchanges* table lists down the interchanges based on the filter criteria. The following attributes are displayed for each message:


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
    
    **Status**
    
    </td>
    <td valign="top">
    
    Status of end-to-end interchange processing.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Error Category**
    
    </td>
    <td valign="top">
    
    The category due to which the intechange processing failed
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Sender Name**
    
    </td>
    <td valign="top">
    
    Name of the sender
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Receiver Name**
    
    </td>
    <td valign="top">
    
    Name of the receiver
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Interchange Name**
    
    </td>
    <td valign="top">
    
    Name of the interchange
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Interchange Direction**
    
    </td>
    <td valign="top">
    
    The direction of the interchange
    
    </td>
    </tr>
    </table>
    
6.  Choose the settings :gear: button above the table to view and add additional table column headers. In the *Columns* dialog, select/deselect the column headers and use the up <span class="SAP-icons-V5"></span> and down <span class="SAP-icons-V5"></span> arrows to reorder the columns in the table

7.  To cancel interchange processing, select the checkbox\(es\) next to the interchange\(s\) you want to cancel and choose *Cancel*. Interchanges can only be canceled if they are in one of the following statuses:

    > ### Remember:  
    > Canceling interchanges is a permanent action and cannot be undone.

    1.  Failed

    2.  Retry

    3.  Processing

    4.  Waiting for Acknowledgement

    5.  Aknowledgement Overdue


    > ### Tip:  
    > If you want to cancel interchanges with a specific set of status, you can do so by filtering them by that status and select all the interchanges by selecting the checkbox next to *Status* column header and choose *Actions* \> *Cancel*.
    > 
    > To cancel multiple interchanges with a specific status, follow these steps:
    > 
    > 1.  Filter the interchanges by the desired status.
    > 
    > 2.  Select all the filtered interchanges by checking the box next to the *Status* column header.
    > 3.  Choose *Actions* \> *Cancel*.
    > 
    >     > ### Note:  
    >     > Filtered results containing a large number of interchanges may prolong cancelation processing time.

    In the *Confirm Cancelation* dialog, provide a reason for terminating the interchange in the *Cancelation Reason* field and choose *Confirm Cancelation*.

8.  Choose the sort <span class="SAP-icons-V5"></span> button to sort the table values in ascending/descending order based on a particular column header.

9.  You can also export the interchanges in Excel format using the <span class="SAP-icons-V5"></span> icon provided proceeding the list.

10. Select an interchange from the table to view it in detail. The interchange information is displayed to the right of the interchange table. The header area provides the following information about the interchange:

    -   *Status*

    -   *Processing Status*
    -   *Sender Technical Acknowledgment Status*\(appears only if it applies to the interchange\)
    -   *Sender Functional Acknowledgment Status*\(appears only if it applies to the interchange\)
    -   *Receiver Functional Acknowledgment Status*\(appears only if it applies to the interchange\)
    -   *Interchange Creation Time*

11. After the header section, the following sections are displayed:

    1.  *Error Information*: This section appears only for innterchanges with the *Failed* status. Choose *Details* to access more information about the error.

        Choose *Check Agreements* to review the agreement details.

    2.  *General*: Provides the general information such as the timestamp for process initiation and completion, interchange name and direction, agreement details, transaction type etc. and the following subsections:

        -   *Custom Attributes*: The custom attributes if defined in the agreement transaction will be displayed here.

        -   *Sender*: The sender details such as message type, sender/receiver identifier, sender/receiver identifier qualifier, document standard, adapter type are displayed here.
        -   *Receiver*: The receiver details such as message type, sender/receiver identifier, sender/receiver identifier qualifier, document standard, adapter type are displayed here.

    3.  *Events*: The events section displays the *Monitoring Reference* link for the following messages:

        -   Sender Interchange Received

        -   Technical Acknowledgement Sent \(for Received Sender Interchange\)
        -   Sender Interchange Mapped
        -   Receiver Interchange Assembled
        -   Receiver Interchange Sent
        -   Error \(applicable only for interchanges with *Failed* and *Retry* statuses\)
        -   Interchange is canceled \(applicable only for interchanges with *Canceled* and does not contain any reference link\)

        Select the link provided under *Monitoring Reference* to view the respective message processing details of the intergration flow involved in the transaction in a new window.

    4.  *Interchange Payload*: View the payload information of *Sender Interchange Received* and *Receiver Interchange Assembled* here. You can switch between these two payload using the drop-down <span class="SAP-icons-V5"></span> provided for the *Version* field. Choose the download <span class="SAP-icons-V5"></span> button to download your payload information.

    5.  *Notes*: This section is only visible for interchanges that have been **Canceled**. The section mentions details of the cancelation, including:

        -   Email address of the user who initated the cancelation

        -   The reason for cancelation \(as entered by the user\)
        -   The timestamp of when the cancellation occurred
        -   A link to the associated event \(for further reference\)


12. If you want to resend or restart failed interchanges, see [Resend/Retry Interchanges](resend-retry-interchanges-8626727.md).


