<!-- loio314df3f8f4334dd8829c62e865cc6d02 -->

#  Monitor Message Processing

The message monitor provides an overview of the messages processed on a tenant and allows you to display the details for individual messages.

You open the message monitor by clicking a tile in the *Monitor Message Processing* area.

Messages are displayed according to the filter settings of the tile.



## Filter Settings

You can control which messages are displayed by changing the filter.

You can filter messages by *Time*, *Status*, and *Artifact*.

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

Allows you to select from the following predefined time intervals:

-   *All*

-   *Past Minute*

-   *Past Hour*

-   *Past 24 Hours*

-   *Past Week*

-   *Past Month*

-   *Custom*


You can select the start and end time of the interval.

The specified time interval is displayed above the message list. When you browse different pages of the message monitor, the time interval stays the same. You can only modify the time interval by changing the filter settings or by refreshing the message monitor \(applies to all-time intervals except for *Custom*\).



</td>
</tr>
<tr>
<td valign="top">

 *Status* 



</td>
<td valign="top">

Allows you to filter messages according to their status.

In the dropdown list you can select one of the following values as the status:

-   *All*

-   *Failed*

-   *Retry*

-   *Completed*

-   *Processing*

-   *Escalated*

-   *Cancelled*

-   *Discarded*
-   *Abandonded*



</td>
</tr>
<tr>
<td valign="top">

 *Artifact* 



</td>
<td valign="top">

Allows you to display messages associated with specific artifacts.

The value help list contains all artifacts and packages for which Message Processing Logs might exist.

When you position the cursor on an artifact in the value help list, name and type are displayed and the tooltip shows additional information.

When you select one of the following entries in the value help list, you can also filter for all artifacts with a dedicated type:

-   *All Integration Flows*

-   *All OData APIs*

-   *All SOAP APIs*

-   *All REST APIs*


You can filter for artifacts with a specific sequence of characters in their name or ID. The search is case insensitive.



</td>
</tr>
</table>

Go to *Use More Fields* to display addition filter criteria, such as:

-   *Sender*

-   *Receiver*

-   *Custom Status*

-   *Application Message Type*

-   *Custom Header*


A value help is available for the *Sender*, *Receiver*, *Custom Status*, and *Application Message Type* fields. The list of available values depends on your integration design.

To filter for a dedicated value of a custom header, in the *Custom Header* field, enter an expression like: ***<custom header name\> = <custom header value\>***

Alternatively, you can search for IDs in the*ID* field, and display messages associated with various IDs such as:

**ID**


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

 *Message ID* 



</td>
<td valign="top">

Identifies the message uniquely.



</td>
</tr>
<tr>
<td valign="top">

 *Correlation ID* 



</td>
<td valign="top">

Identifies correlated messages



</td>
</tr>
<tr>
<td valign="top">

 *Application ID* 



</td>
<td valign="top">

Is set when an `SAP_ApplicationID` header element is specified in the associated integration flow in the Content Modifier step.



</td>
</tr>
</table>

If you search for message processing logs by ID, the system first checks whether there’s a message with the specified Message ID. If the Message ID is not found, the system searches for the Correlation ID. There can be more than one message found for one Correlation ID. If no message is found, the system searches for messages with the given application ID.

This search attribute can’t find messages where the Correlation ID is the same as an existing Message ID, or the Application ID equals a Correlation ID or Message ID \(by coincidence\).

Searching for messages by using the ID attribute is helpful for support use cases \(for root cause analysis, for example\).



## Messages Table

The messages for the selected filter settings are displayed in a table under *Messages*. If the number of filtered messages exceeds 50, the list is split over several pages \(each page containing a maximum of 50 messages\). You can browse through the different pages by selecting the corresponding navigation options \(*Show first data page*, *Show last data page*, *Show previous data page*, and *Show next data page*\).

Alternatively, you can enter a page number to navigate to a specific page of the list.

The following attributes are displayed for each message:

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

Display name of the artifact \(for example, the name of the integration flow that specifies the message processing\).

The tooltip shows the technical name, the artifact, and the package name.



</td>
</tr>
<tr>
<td valign="top">

 *Status* 



</td>
<td valign="top">

Status of end-to-end message processing.



</td>
</tr>
<tr>
<td valign="top">

 *Last Updated at* 



</td>
<td valign="top">

Time at which the message processing log was last updated.



</td>
</tr>
<tr>
<td valign="top">

 *Processing Time* 



</td>
<td valign="top">

Total message processing time.



</td>
</tr>
</table>

For a selected message, the details are displayed to the right of the message table. The header area provides the following information about the selected message: *Artifact Name* and *Last Updated at*.

Below the header, the following sections contain detailed information about the selected message:

-   *Status*

    Contains status information about the message such as the `Processing Time`. If the message is **NOT** in status COMPLETED, the last error message is displayed \(if available\).

-   *Properties*

    Contains

    -   The *Message ID*

    -   The *Correlation ID*
    -   The *Sender*
    -   The *Receiver*
    -   The *Application Message ID*
    -   The *Application Message Type*
    -   The *Custom Status*

    > ### Note:  
    > *Sender*, *Receiver*, *Application Message ID*, *Application Message Type*, and *Custom Status* are optional and can be set via the Content Modifier. They’re only visible if they aren’t empty.
    > 
    > The *Custom Status* is only visible if it differs from the overall processing status.

-   *Custom Header Properties*

    The properties can be set using the script step. If they’re set, they’re displayed in this section.

    For more information, see: [Use Custom Header Properties to Search for Message Processing Logs](use-custom-header-properties-to-search-for-message-processing-logs-d4b5839.md)

-   *Logs*

    Displays the *Log Level* and the *Runtime Node*. Clicking the log level link takes you to the message processing log displayed in table form. You access the textual representation by selecting *Open Text View*.

    If the processing of an integration flow failed and retry runs were performed, the runs are displayed in a table \(up to 50 retries\) in the *Logs*section.

    If Data Archiving is activated for logs of an integration artifact, the archiving status is displayed in this section. The status are:

    -   **Not Archived**:

        -   Data Archiving is not activated for logs of this integration artifact.

        -   Data Archiving does not consider logs of discarded message processing.
        -   Data Archiving is configured to consider logs of successfully completed messages only.

    -   **Archiving Pending**: Data Archiving is activated for logs of this integration artifact.
    -   **Archived**: Data Archiving is completed for this log.

-   *Attachments*

    This section is only displayed if the message processing log contains attachments.

    Any type of attachment that can be displayed as text is supported. In particular, the following types of content can be displayed:

    -   Plain text

    -   XML

        XML attachments are displayed as formatted plain text \(including tags\).

    -   Text files with comma-separated values

    -   Text files with tab-separated values

        In these files, each entry is represented as one line of the text file.

    -   HTML

        HTML attachments are displayed as plain text \(including tags\).


-   *Artifact Details*

    This section displays the artifact *Name*, *ID*, *Type*, and *Package*, if available. You can open the integration flow by clicking the *View deployed Artifact* link. To edit the integration flow model, click the *Navigate to Artifact Editor* link. You can also navigate to the Integration Content Monitor by selecting the *Manage Integration Content* link. You will get a list of all artifacts matching the ID-string displayed in the search field.


**Related Information**  


[Message Processing Log – Text View](message-processing-log-text-view-718309a.md "The message processing log displays structured information on the processing of a message.")

[Message Status](message-status-733a57b.md "")

[Configuring Archiving Settings](configuring-archiving-settings-c38760d.md "You can configure the archiving settings via the Integration Content Monitor for each integration flow.")

