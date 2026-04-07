<!-- loio0d61459af2c64e9a9f123dcbb619d5a9 -->

# Microsoft Outlook Receiver Adapter

The Microsoft Outlook Receiver adapter allows you to manage Microsoft Outlook resources such as Calendar, Mail Folders, Attachments, and Messages etc.



## How the Microsoft Outlook Receiver Adapter works

If you have configured the Microsoft Outlook Receiver Adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Microsoft Outlook \(this is a receiver system\), Microsoft Outlook Receiver Adapter works on the request and sends the data back to the SAP Integration Suite tenant.



## Configure the Microsoft Outlook Receiver Adapter

Once you have created a receiver channel and selected the Microsoft Outlook Receiver Adapter, you can configure its parameters as shown below:

**Connection**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Specify the address for the Microsoft Outlook service.

Default: `https://graph.microsoft.com`

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the authentication method and permission type: 'Delegated' for user-level access, 'Application' for app-level access.

-   *OAuth2 Client Credentials \(Application Permissions\)*
-   *OAuth2 Authorization Code \(Delegated Permissions\)*



</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the security artifact for the selected authentication type to connect to your Microsoft Outlook account.

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable this property to reuse the connection.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received.

</td>
</tr>
</table>

**Processing**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Resource*

</td>
<td valign="top">

Select the resource on which to perform an operation:

-   *Mail Folder*
-   *Mail Message*
-   *Attachment*
-   *Calendar*



</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the operation to be performed:

Example: *List messages*

</td>
</tr>
<tr>
<td valign="top">

*User ID*

</td>
<td valign="top">

Specify the user principal name \(email address\) or ID to perform the operation.

Example: `b393b406-9cb1-4b5d-5332-b7d6be49c81b`

</td>
</tr>
<tr>
<td valign="top">

*Group ID*

</td>
<td valign="top">

Specify the Group ID to perform the operation.

Example: `b991a872-b048-43ae-9074-4246a246745e`

</td>
</tr>
<tr>
<td valign="top">

*Folder Identifier*

</td>
<td valign="top">

Select the mode to identify the folder using its ID or name.

</td>
</tr>
<tr>
<td valign="top">

*Folder Name*

</td>
<td valign="top">

Specify the name of the folder where the operation will be performed.

</td>
</tr>
<tr>
<td valign="top">

*Mail Folder ID*

</td>
<td valign="top">

Specify the Mail Folder ID to perform the operation.

</td>
</tr>
<tr>
<td valign="top">

*Calendar Group ID*

</td>
<td valign="top">

Specify the Calendar Group ID to perform the operation.

</td>
</tr>
<tr>
<td valign="top">

*Calendar ID*

</td>
<td valign="top">

Specify the Calendar ID to perform the operation.

</td>
</tr>
<tr>
<td valign="top">

*Mail Message ID*

</td>
<td valign="top">

Specify the Mail Message ID to perform the operation.

</td>
</tr>
<tr>
<td valign="top">

*Attachment ID*

</td>
<td valign="top">

Specify the Attachment ID associated with a message, event, etc.

</td>
</tr>
<tr>
<td valign="top">

*Child Folder ID*

</td>
<td valign="top">

Specify the Child Folder ID associated with the subfolder on which this operation will be performed.

</td>
</tr>
<tr>
<td valign="top">

*Thread ID*

</td>
<td valign="top">

Specify the Thread ID to perform the operation. This ID represents a conversation thread within a group.

</td>
</tr>
<tr>
<td valign="top">

*Event ID*

</td>
<td valign="top">

Specify the Event ID of the calendar event. This ID groups related messages or posts into a thread.

</td>
</tr>
<tr>
<td valign="top">

*Conversation ID*

</td>
<td valign="top">

Specify the Conversation ID to perform the operation.

Example: `AAQkAGRhZmRhMWM3LTYwZTktNDZmYy1hNWU1LThhZWU4NzI2YTEyZgAQABKPPJ682apIiV1UFlj7XxY=`

</td>
</tr>
<tr>
<td valign="top">

*Post ID*

</td>
<td valign="top">

Specify the Post ID to perform the operation. This ID represents an individual message or post within a thread.

</td>
</tr>
<tr>
<td valign="top">

*Start Date Time*

</td>
<td valign="top">

Specify the date and time from when the calendar view should be fetched.

Example: `2026-01-08T15:00:00`

</td>
</tr>
<tr>
<td valign="top">

*End Date Time*

</td>
<td valign="top">

Specify the date and time until when the calendar view should be fetched.

Example: `2026-02-08T16:00:00`

</td>
</tr>
<tr>
<td valign="top">

*Request Format*

</td>
<td valign="top">

Select the payload format of the request body.

Example: *Application/JSON*

</td>
</tr>
<tr>
<td valign="top">

*Response Format*

</td>
<td valign="top">

Select the payload format of the response body.

Example: *Text/Plain*

</td>
</tr>
<tr>
<td valign="top">

*Next Link URL*

</td>
<td valign="top">

Specify the Next Link URL to perform the operation.

Example: `https://graph.microsoft.com/v1.0/users/{{userId}}/mailFolders?%24select=id%2cdisplayName%2cisHidden&%24top=8&%24skip=8`

</td>
</tr>
<tr>
<td valign="top">

*Delta Link \(URL\)*

</td>
<td valign="top">

Specify the Delta Link \(URL\) to perform the operation; leave blank for the initial request.

</td>
</tr>
<tr>
<td valign="top">

*Query Parameters*

</td>
<td valign="top">

Specify the query parameter. When using multiple parameters, ensure they are separated by "&".

Example: `$top=20&$expand=members.`

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to be sent to the target system. Use an asterisk \(\*\) to send all custom headers to the target system. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property.

</td>
</tr>
</table>

