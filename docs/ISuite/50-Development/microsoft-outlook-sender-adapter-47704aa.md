<!-- loio47704aaf438143f2ad7574abe60ddc8f -->

# Microsoft Outlook Sender Adapter

Microsoft Outlook Sender Adapter provides the ability to read and process mail messages from Microsoft Outlook mailbox.



<a name="loio47704aaf438143f2ad7574abe60ddc8f__fdsfkoesq30223"/>

## How the Microsoft Outlook Sender Adapter Works

If you have configured the Microsoft Outlook Sender Adapter, data exchange is performed as follows at runtime: Microsoft Outlook sends the operation request to SAP Integration Suite tenant, Microsoft Outlook Sender Adapter works on the request and sends the data to SAP Integration Suite tenant.



<a name="loio47704aaf438143f2ad7574abe60ddc8f__secction_3j4_rdc"/>

## Configure the Microsoft Outlook Sender Adapter

Once you have created a sender channel and selected the Microsoft Outlook Sender Adapter, you can configure its parameters as shown below:

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

Specify the security artifact for the selected authentication type to connect to the Microsoft Outlook account.

</td>
</tr>
<tr>
<td valign="top">

*Polling Interval \(in ms\)*

</td>
<td valign="top">

Specify the poll interval in milliseconds.

Example:`60000`

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

Example:`60000`

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received.

Example:`60000`

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

*User ID*

</td>
<td valign="top">

Specify the user principal name \(email address\) or ID to perform the operation.

Example: `john.doe@outlook.com or b393b406-9cb1-4b5d-5332-b7d6be49c81b`

</td>
</tr>
<tr>
<td valign="top">

*Folder Identifier*

</td>
<td valign="top">

Select the mode to identify the folder.

-   *Name*
-   *ID*



</td>
</tr>
<tr>
<td valign="top">

*Folder Name*

\(Only available when the Folder Identifier is set to *Name*\)

</td>
<td valign="top">

Specify the Folder Name that contains the emails to be read. Folder names are not valid for child folders, use the mail folder ID to specify them instead.

Example: `Inbox`

> ### Note:  
> If left blank, emails from all folders will be read.



</td>
</tr>
<tr>
<td valign="top">

*Mail Folder ID*

\(Only available when the Folder Identifier is set to *ID*\)

</td>
<td valign="top">

Specify the Mail Folder ID that contains the emails to be read.

Example: `AQMkAGY5NzFiZjE3LTgwNDgtNDBlYS1jM2Q4LTI3ZTQ1QjE3NG EzODkzLgAAAYtmMD5sTKHsQXpqNcMHR1CAP06ZHfBE8eMu0QQS_ GmeY9BBBICDAAAAA==`

> ### Note:  
> If left blank, emails from all folders will be read.



</td>
</tr>
<tr>
<td valign="top">

*Selection*

</td>
<td valign="top">

Specify which mails are to be processed \(all mails or only unread ones\). This field is editable, allowing you to use a filter expression to fetch mails.

-   *All*
-   *Only Unread*

> ### Note:  
> This field currently supports only filter queries.
> 
> Example: `sentDateTime lt 2025-11-28T12:00:00Z`



</td>
</tr>
<tr>
<td valign="top">

*Max Messages per Node*

</td>
<td valign="top">

Specify the maximum number of mails to be retrieved per worker node.

Example: `2`

</td>
</tr>
<tr>
<td valign="top">

*Lock Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum duration \(in milliseconds\) when the lock is active during the polling process for duplication check.

Example: `120000`

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing*

</td>
<td valign="top">

Select the action to be performed after successful iflow processing:

-   *Archive*
-   *Archive and Mark as Read*
-   *Delete*
-   *Mark as Read*



</td>
</tr>
<tr>
<td valign="top">

*Archive Folder Identifier*

\(Only available when the *Post-Processing* is set to*Archive* or *Archive and Mark as Read*\)

</td>
<td valign="top">

Select the mode to identify the archive folder.

-   *Name*
-   *ID*



</td>
</tr>
<tr>
<td valign="top">

*Archive Folder Name*

\(Only available when the Archive Folder Identifier is set to *Name*\)

</td>
<td valign="top">

Specify the name of the archive folder where the file should be archived.

Example: `Archive`

</td>
</tr>
<tr>
<td valign="top">

*Archive Mail Folder ID*

\(Only available when the Archive Folder Identifier is set to *ID*\)

</td>
<td valign="top">

Specify the ID of the archive folder where the file should be archived.

Example: `AQMkAGY4NzRhZjE5LTgxMzgtNDBmYS1kM2E4LTM3ZTU 1QjI3NGE5ODQzLgAAAYslME6tRKJsQXpzNdNHR2BAP16ZHhBE 9fNu1RQS_HneZ9BBBJCDDAAAAA==`

</td>
</tr>
<tr>
<td valign="top">

*Response Type*

</td>
<td valign="top">

Select the content type for the response payload to be returned.

-   *Application/JSON*
-   *Content Only*
-   *MIME*

> ### Note:  
> When *Response Type* is set to *Content Only*, the payload is returned as HTML. The response must therefore be handled as HTML \(e.g. forwarded to an application that supports HTML\) or treated as a raw string to extract the required information.



</td>
</tr>
</table>

