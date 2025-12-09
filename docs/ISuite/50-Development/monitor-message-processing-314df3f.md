<!-- loio314df3f8f4334dd8829c62e865cc6d02 -->

# Monitor Message Processing

The message monitor provides an overview of the messages processed on a tenant and allows you to display the details for individual messages.

To access the message monitor, choose a tile in the *Monitor Message Processing* area. The system displays messages based on the filter settings of the tile.

> ### Note:  
> In high-load scenarios, the system may still determine the number of messages while it already displays the list of messages. The determination of the message count is independent of the message search. This ensures that the message monitor doesn't encounter a timeout situation when determining a long list of messages.



## Filter Settings

You can control which messages appear by changing the filter. You can filter messages by the following categories:

**Filter Attributes**


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

*Time* 

</td>
<td valign="top">

Select from the following predefined time intervals:

-   *All*

-   *Past Minute*

-   *Past Hour*

-   *Past 24 Hours*

-   *Past Week*

-   *Past Month*

-   *Custom*

    > ### Note:  
    > When you select the *Custom* option, you can select a specific start and end time. Choose a specific date and time using a graphical element with two components: a calendar element and a circular watch element.


The specified time interval appears above the message list. When you browse different pages in the message monitor, the time interval remains the same. To change the time interval, adjust the filter settings or refresh the message monitor. This applies to all time intervals except for *Custom*.

</td>
</tr>
<tr>
<td valign="top">

*Status* 

</td>
<td valign="top">

Filter messages according to their status:

-   *All*

-   *Failed*

-   *Retry*

-   *Completed*

-   *Processing*

-   *Escalated*

-   *Cancelled*

-   *Discarded*
-   *Abandoned*

See: [Message Status](message-status-733a57b.md)

</td>
</tr>
<tr>
<td valign="top">

*Type* 

</td>
<td valign="top">

Filter all artifacts by a specific type:

-   *All*

-   *Integration Flow*

-   *API \(Edge runtimes only\)*

-   *OData API*

-   *SOAP API*

-   *REST API*




</td>
</tr>
<tr>
<td valign="top">

*Package* 

</td>
<td valign="top">

Display all messages that belong to a specific package .

If you select a package, you can also filter for the different types or artifacts that belong to that package. If you change the package or type in the filter, the system clears the artifact selection as well.

</td>
</tr>
<tr>
<td valign="top">

*Artifact* 

</td>
<td valign="top">

Display messages related to specific artifacts. You can select multiple artifacts to display their messages. By default, the system shows all artifacts.

The list includes all artifacts that have message processing logs. When you place the cursor on an artifact in the list, a tooltip displays the artifact ID.

You can filter artifacts by entering a specific sequence of characters in their name or ID. The search does not consider case sensitivity.

</td>
</tr>
<tr>
<td valign="top">

*ID* 

</td>
<td valign="top">

Filter messages using different IDs.

See: [Using IDs to Filter Messages](using-ids-to-filter-messages-a820752.md)

</td>
</tr>
</table>

Choose *Use More Fields* to display additional filter criteria.

See: [Using Additional Filter Criteria](using-additional-filter-criteria-6891f9e.md)



## Messages Table

After you select the filters, a list of all relevant messages appears under *Messages*. If the number of filtered messages exceeds 50, the list is divided across multiple pages. You can browse the different pages by selecting the navigation options. You can also enter a page number to go directly to a specific page in the list.

The following attributes appear for each message:

**Message Attributes in Message Overview**


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

*Artifact Name* 

</td>
<td valign="top">

The name of the artifact. For example, this is the name of the integration flow that specifies message processing.

The tooltip shows the technical name, the artifact, and the package name.

</td>
</tr>
<tr>
<td valign="top">

*Status* 

</td>
<td valign="top">

The status of end-to-end message processing. If messages have a critical status, you can open them to view error details.

</td>
</tr>
<tr>
<td valign="top">

*Last Updated at* 

</td>
<td valign="top">

The time at which the message processing log was last updated.

</td>
</tr>
<tr>
<td valign="top">

*Processing Time* 

</td>
<td valign="top">

The total message processing time.

</td>
</tr>
</table>



<a name="loio314df3f8f4334dd8829c62e865cc6d02__section_s3m_wqz_wgc"/>

## Message Details

You can select a message from the list to view more information about it.

In the new pane that opens, select one of the following tabs to view more details about the selected message:

-   *Status*. This section contains status information about the message, such as the `Processing Time`. If the message does not have the status COMPLETED, the system displays the last error message if one is available.

-   *Properties*:

    -   **Message ID**

    -   *Correlation ID*
    -   *Application Message ID*
    -   *Predecessor ID*

        For more information, see: [Using IDs to Filter Messages](using-ids-to-filter-messages-a820752.md).

    -   *Sender*
    -   *Receiver*
    -   *Application Message Type*
    -   *Custom Status*
    -   *Retention Periods* for completed and uncompleted messages.

    > ### Note:  
    > *Sender*, *Receiver*, *Application Message ID*, *Application Message Type*, and *Custom Status* are optional and can be set via the Content Modifier. They're only shown if they aren’t empty.
    > 
    > The *Custom Status* is only visible if it differs from the overall processing status.

-   *Custom Header Properties*. You can set these properties using the script step. If set, the system displays them in this section.

    For more information, see: [Use Custom Header Properties to Search for Message Processing Logs](use-custom-header-properties-to-search-for-message-processing-logs-d4b5839.md)

-   *Logs*. This section displays the *Log Level* and the *Runtime Node*. Select the log level link to view the message processing log in a visual format. For more information, see [Message Processing Log](message-processing-log-b32f8cd.md).

    To access the text version, select *Open Text View*, see [Message Processing Log – Text View](message-processing-log-text-view-718309a.md).

    If the processing of an integration flow fails and the retry runs are performed, these runs appear in a table in the *Logs* section. The table displays up to 50 retries.

    If you activate *Data Archiving* for the logs of an integration artifact, the system displays the archiving status in this section. The possible statuses are:

    -   **Not Archived**:

        -   *Data Archiving* is not activated for logs of this integration artifact.

        -   *Data Archiving* does not consider logs of discarded message processing.
        -   *Data Archiving* is configured to consider logs of successfully completed messages only.

    -   **Archiving Pending**: *Data Archiving* is activated for logs of this integration artifact.
    -   **Archived**: *Data Archiving* is completed for this log.

-   *Attachments*.This section appears only when the message processing log includes attachments. The system displays a list of all attachments that can be displayed as text. You can browse the different pages to view the complete list of attachments. Select the relevant navigation options to do so.

    The following attachment formats are supported:

    -   Plain text

    -   XML. XML attachments are displayed as formatted plain text \(including tags\).

    -   Text files with comma-separated values

    -   Text files with tab-separated values. In these files, each entry appears as a single line in the text file.

    -   HTML. HTML attachments are displayed as plain text \(including tags\).


    You can open the attachments on a new screen and download them to your local file system.

-   *Artifact Details*. This section displays the artifact *Name*, *ID*, *Type*, and *Package*, if available.

    You can also use any of the following navigation links to continue working with your artifacts:


    <table>
    <tr>
    <th valign="top">

    Hyperlink
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Manage Integration Content* 
    
    </td>
    <td valign="top">
    
    Navigate to the integration content monitor.

    When you navigate to the integration content monitor, the system opens the active artifact that is currently deployed.

    See: [Manage Integration Content](manage-integration-content-09a7223.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *View deployed Artifact* 
    
    </td>
    <td valign="top">
    
    Navigate to the deployed artifact. If the artifact is an integration flow, the system displays the model for the deployed integration flow. You can't edit this model.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Navigate to Artifact Editor* 
    
    </td>
    <td valign="top">
    
    Navigate to the artifact editor which allows you to edit the artifact. If the artifact is an integration flow, you can edit the integration flow model.
    
    </td>
    </tr>
    </table>
    



<a name="loio314df3f8f4334dd8829c62e865cc6d02__section_jkv_4xd_5cc"/>

## Message Status Overview

You can quickly navigate to the *Message Status Overview* page by choosing the *Message Status Overview* button.

![](images/Message_Status_Overview_Button_782b507.png)

This view offers a detailed summary of the statuses of messages for various artifacts over a specified time period. For more information, see [Monitor Message Status Overview](monitor-message-status-overview-0cde046.md).

**Related Information**  


[Message Processing Log – Text View](message-processing-log-text-view-718309a.md "The message processing log displays structured information on the processing of a message.")

[Message Status](message-status-733a57b.md "The message processing status indicates how a messages has been processed at runtime.")

[Configuring Archiving Settings](configuring-archiving-settings-c38760d.md "You can configure the archiving settings via the Integration Content Monitor for each integration flow.")

