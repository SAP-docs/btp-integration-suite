<!-- loioc86bd69e8ed54afc8d4c27227d191d91 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitor Unassigned Interchanges

Monitor the unassigned interchanges



## Context

An unassigned interchange is an interchange to which no business document has been attached. This happens when an error occurs during the metadata extraction while processing the integration flow. Such interchanges can be viewed under the *Unassigned Interchanges* tile of the B2B monitor.



## Procedure

1.  Open the *Unassigned Interchanges* tile under *Monitor* \> *B2B Scenarios*.

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
    
    **Error Date Time**
    
    </td>
    <td valign="top">
    
    Allows you to select from the following predefined time intervals during which the errors occured:

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
    > This field is enabled only if you choose *Custom* option for the field *Error Date Time*.


    
    </td>
    <td valign="top">
    
    You can set the start date and time using the date-time <span class="SAP-icons-V5"></span> button provided in the field. To select the date, interact with the calendar element and choose a specific day. To select the time, manipulate two separate circles on the watch element to set the desired hour and minute, respectively..
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    To

    > ### Note:  
    > This field is enabled only if you choose *Custom* option for the field *Error Date Time*.


    
    </td>
    <td valign="top">
    
    You can set the end date and time using the date-time <span class="SAP-icons-V5"></span> button provided in the field. To select the date, interact with the calendar element and choose a specific day. To select the time, manipulate two separate circles on the watch element to set the desired hour and minute, respectively..
    
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
    
    **Error Information**
    
    </td>
    <td valign="top">
    
    Allows you to filter interchanges based on the error information.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Message Processing Log ID**
    
    </td>
    <td valign="top">
    
    Allows you to filter the interchanges based on the MPL ID.
    
    </td>
    </tr>
    </table>
    
3.  Choose *Go* after setting the necessary filter to view the filtered interchanges.

4.  Choose *Adapt Filters* to view and add additional filter criteria.

5.  The *Unassigned Interchanges* table lists down the interchanges based on the filter criteria. The following attributes are displayed for each message: *Error Date Time*, *Error Category*, *Error Information*.

6.  Choose the settings :gear: button above the table to view and add additional table column headers. In the *Columns* dialog, select/deselect the column headers and use the up <span class="SAP-icons-V5"></span> and down <span class="SAP-icons-V5"></span> arrows to reorder the columns in the table

7.  You can also export the interchanges in Excel format using the <span class="SAP-icons-V5"></span> icon provided proceeding the list.

8.  Select an interchange from the table to view it in detail. The interchange information is displayed to the right of the interchange table. The header area provides the following information about the interchange: *Error Date Time*, *Message Processing Log ID*.

9.  Select the link under *Message Processing Log ID* to view the log in detail.

10. After the header section, the following sections are displayed:

    1.  *General Information*: This section provides the following subsections:

        -   *Error Information*: Provides you the general detail about the error such as error category and error information.

        -   *Sender*: Provides you the sender details such as adapter type, document standard, payload format and user name.

        -   *Communication Protocol*: Provides the protocol information such as file name, message ID, message content type etc.


    2.  *Unassigned Interchange Payload*: View the payload information of *Unassigned Interchange*. Choose the download <span class="SAP-icons-V5"></span> button to download your payload information.



