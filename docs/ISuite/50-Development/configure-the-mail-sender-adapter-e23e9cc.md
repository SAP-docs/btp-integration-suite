<!-- loioe23e9cce8a974b8c8012ffcad5494766 -->

# Configure the Mail Sender Adapter

You use the mail sender adapter to download e-mails from mailboxes using the IMAP or POP3 protocol, to access the content of the e-mail body, and to access e-mail attachments.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

If you have configured a mail sender adapter, message processing is performed as follows at runtime: According to the Scheduler settings in the mail sender adapter, the tenant sends requests to an e-mail server \(think of this as the sender system\). Nevertheless, the data flow is in the opposite direction, from the mail server to the tenant. In other words, the tenant reads files from the mail server \(a process that is also referred to as polling\).

![](images/Mail_Sender_0218387.png)

> ### Caution:  
> To take the necessary precautions in order to avoid any unwanted behavior of your scenario \(in particular, security risks\) check out the following topic:
> 
> [Important Notes on Security Risks and Mailbox Settings](important-notes-on-security-risks-and-mailbox-settings-34aa095.md)

Once you have created a sender channel and selected the mail sender adapter, you can configure the following attributes. See: [Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

Select the *General* tab and provide values in the fields as follows.

**General**


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

*Name*

</td>
<td valign="top">

Enter the name of the channel.

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as follows.

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

Specifies the host name or address of the IMAP server, for example, mail.domain.com.

Use one of the following open ports for external mail servers:

-   143 for IMAP+STARTTLS

-   993 for IMAPS

-   110 for POP3+STARTTLS

-   995 for POP3S


Example address for Yahoo IMAP server:

`imap.mail.yahoo.com:993`

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

The type of proxy that you’re using to connect to the target system.

Select *Internet* if you’re connecting to a cloud mail server.

Select *On-Premise* if you’re connecting to an on-premise mail server.

For more information, see: [Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md).

</td>
</tr>
<tr>
<td valign="top">

*Location ID* \(only if *On-Premise* is selected for *Proxy Type*\)

</td>
<td valign="top">

To connect to an SAP Cloud Connector instance associated with your account, enter the location ID that you defined for this instance in the destination configuration on the cloud side.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)* 

</td>
<td valign="top">

Specifies the network timeout for the connection attempt to the server. The default value is 30000.

</td>
</tr>
<tr>
<td valign="top">

*Protection* 

</td>
<td valign="top">

Specifies the method to use to establish an encrypted \(secure\) connection.

-   *Off*

    No encryption is initiated by the client.

    > ### Note:  
    > If your on-premise mail server requires SMTPS, select *Off* for *Protection*. The SSL connection then needs to be configured in SAP Cloud Connector.

-   *POP3S* \(only when transport protocol *POP3* has been selected when creating the channel and only when *Internet* has been selected as *Proxy Type*\)

    The TCP connection to the server is encrypted. The *S* \(in POP3S\) stands for *secure*; in technical terms, TLS encryption is applied in that case.

-   *IMAPS* \(only when transport protocol *IMAP4* has been selected when creating the channel and only when *Internet* has been selected as *Proxy Type*\)

    The TCP connection to the server is encrypted. The *S* \(in IMAPS\) stands for *secure*; in technical terms, TLS encryption is applied in that case.

-   *STARTTTLS Mandatory* 

    If the server supports STARTTLS, the client initiates encryption using TLS. If the server doesn’t support this option, the connection stops with an error.

-   *STARTTTLS Optional* 

    If the server supports STARTTLS, the client initiates encryption using TLS. If the server doesn’t support this option, client and server remain connected but communicate without encryption.




</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Specifies which mechanism is used to protect user name and password combination.

-   *Plain User Name/Password*

    The user name and password are sent in plain text. Only use this option together with SSL or TLS, as otherwise an attacker could obtain the password.

-   *Encrypted User/Password*

    The user name and password are hashed before being sent to the server. This authentication mechanism \(CRAM-MD5 and DIGEST-MD5\) is secure even without encryption.

-   *OAuth2 Authorization Code* \(only when transport protocol *IMAP4* has been selected when creating the channel\)

    The authentification is done via an authorization server as an intermediary step. The client can exchange the OAuth2 Authorization Code for an access token. Your user credentials are never shared with the client.

    See: [Deploying an OAuth2 Authorization Code](deploying-an-oauth2-authorization-code-081bfd7.md)

    > ### Note:  
    > -   *POP3*: OAuth is not available for POP3.
    > -   *Personal Accounts:* Microsoft does not support OAuth for personal accounts for IMAP, POP3, and SMTP. This restriction does not exist for basic authentication.




</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

</td>
<td valign="top">

Specifies the name of the *User Credentials* artifact that contains user name and password \(used to authenticate at the e-mail account\).

More information: [Deploying a User Credentials Artifact](deploying-a-user-credentials-artifact-6912d63.md)

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

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

*Folder* 

\(only if as *Transport Protocol* the option *IMAP4* has been selected\)

</td>
<td valign="top">

Specify the IMAP folder containing the mails to be read.

</td>
</tr>
<tr>
<td valign="top">

*Selection*

\(only if as *Transport Protocol* the option *IMAP4* has been selected\)

</td>
<td valign="top">

Specify which mails are to be processed \(all mails or only unread ones\).

You can select whether all or only unread mails are to be processed.

</td>
</tr>
<tr>
<td valign="top">

*Max. Messages per Poll* 

</td>
<td valign="top">

Defines the maximal number of messages to be read from the e-mail server in one polling step.

</td>
</tr>
<tr>
<td valign="top">

*Lock Timeout \(in min\)* 

</td>
<td valign="top">

Specify the max. amount of time the lock is active during the polling process.

When you start a poll, the mail adapter acquires a lock to be allowed to poll the mailbox. This lock consists of the host, username, and folder. The lock is shared across worker nodes and makes sure that only one worker node polls the same mailbox/folder at the same time. With the lock timeout, you define the max. duration for the acquired lock before it is released automatically. If the poll needs less time than the amount you defined, the lock is released earlier.

It can happen that the lock is not released after a poll \(that is, in case of a node crash\). In this case, the processing will only continue after the lock timed out or the lock is removed manually via the *Lock Monitor* \(see: [Message Locks](message-locks-bce9ae0.md)\). It’s recommended to set the lock time higher than the processing time that is required per poll. But also make sure to not block the processing for a long time in the case of a node crash. A poll is completed after the number of messages as defined in Max. Messages Per Poll has been processed.

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing* 

</td>
<td valign="top">

Specify how to handle processed mails on the server.

There are the following options:

-   *Archive* \(only if as *Transport Protocol* the option *IMAP4* has been selected\)

    Polled message is archived \(moved to specified *Archive Folder*\).

-   *Archive and Mark as Read* \(only if as *Transport Protocol* the option *IMAP4* has been selected\)

    Polled message is marked as read and archived \(moved to specified *Archive Folder*\).

-   *Delete*

    Polled message is deleted.

-   *Mark as Read*

    Polled mail is marked as read.

    > ### Note:  
    > \(Only if as *Transport Protocol* the option *IMAP4* has been selected\)
    > 
    > If *Post-Processing* is set to *Mark as Read* and the poll strategy is set to poll for all mails \(*Selection: All*\), then already processed mails are processed again at every polling interval.
    > 
    > If you want to use this parameter setting, make sure that your polling interval is sufficiently large, otherwise your process becomes inefficient.


Note that the configuration of the mail server can in certain cases override dedicated *Post-Processing* settings \(see: [Important Notes on Security Risks and Mailbox Settings](important-notes-on-security-risks-and-mailbox-settings-34aa095.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Archive Folder* \(only if for *Post-Processing* the option *Archive* or *Archive and Mark as Read* is selected\)

</td>
<td valign="top">

Specify name of folder where mail is to be archived.

</td>
</tr>
<tr>
<td valign="top">

*Remove Attachments* 

</td>
<td valign="top">

Select this option if attachments are to be removed from the mail before further processing.

</td>
</tr>
<tr>
<td valign="top">

*Include Original Mail* 

</td>
<td valign="top">

Enable this option to include the original e-mail in the `SAP_MAIL_ORIGINAL_MESSAGE` property for further processing such as verification of the original e-mail.

The mail adapter polls the messages from the mailbox and splits them into header, property, and body. This means that the original signed e-mail can no longer be verified during further processing.

To verify signed e-mails, you can include the original e-mail in the `SAP_MAIL_ORIGINAL_MESSAGE` property.

</td>
</tr>
<tr>
<td valign="top">

*Decode MIME Headers*

\(selected by default\)

</td>
<td valign="top">

Enable this setting to decode and unfold Multipurpose Internet Mail Extensions \(MIME\) headers that have been encoded during transport.

MIME header fields are inserted by the e-mail server at the beginning of the data transmission. An example for a MIME header is `Content-Type` that indicates the media type of the transferred data.

> ### Note:  
> It is recommended to keep this option selected.

Non-ASCII characters are not allowed in MIME messages. MIME `encoded-word` syntax is used to encode the non-ASCII characters.

For more details, see: [MIME \(Multipurpose Internet Mail Extensions\) Part Three: Message Header Extensions for Non-ASCII Text](https://www.rfc-editor.org/rfc/rfc2047) \(RFC-2047\).

</td>
</tr>
<tr>
<td valign="top">

*Automatically Disconnect*

\(selected by default\)

</td>
<td valign="top">

When selected, SAP Cloud Integration disconnects from the e-mail server after each poll.

</td>
</tr>
</table>

> ### Caution:  
> Mail attachments with the same attachment name aren't supported.
> 
> If there are duplicate attachments, the adapter generates unique attachment names by attaching a GUID to the original attachment name.
> 
> If the attachment name isn't set, the adapter generates a new attachment name by generating a GUID as attachment name.
> 
> Example 1:
> 
> Incoming mail contains the following attachments:
> 
> -   myAttachment.pdf
> 
> -   myAttachment.pdf
> 
> -   myAttachmentUnique.pdf
> 
> 
> Result after mail sender:
> 
> -   myAttachment\_b3160958-c58c-436e-a4b9-5078e7c1cdf5.pdf
> 
> -   myAttachment\_250f0bb4-adda-4129-9635-f5f6f15e7ce3.pdf
> 
> -   myAttachmentUnique.pdf
> 
> 
> Example 2:
> 
> Incoming mail contains the following attachments:
> 
> -   myAttachment
> 
> -   myAttachment
> 
> -   myAttachmentUnique
> 
> 
> Result after mail sender:
> 
> -   myAttachment\_73e53699-ca6e-4ba1-88ce-b87336720141
> 
> -   myAttachment\_c25201a5-f7c6-4113-88bc-617289fd676c
> 
> -   myAttachmentUnique

Select the *Scheduler* tab and provide values in the fields as follows.

> ### Caution:  
> How you specify the *Scheduler* settings depends on the constraints and requirements of your integration scenario. However, make sure to use the *Scheduler* parameters advisedly: Specify the scheduler settings in such a way that messages are not polled with too high frequency. Use the following interval 1 minute only if really required. Otherwise, there’s the risk to overload the mail server.

**Scheduler**


<table>
<tr>
<th valign="top">

Scheduler Option

</th>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="4">

*Schedule on Day*

\(mails are to be polled at a specific day\)

</td>
<td valign="top">

On Date

</td>
<td valign="top">

Specify the date on which you want the operation to be executed.

</td>
</tr>
<tr>
<td valign="top">

On Time

</td>
<td valign="top">

Specify the time at which you want the operation to be executed.

</td>
</tr>
<tr>
<td valign="top">

Every

</td>
<td valign="top">

Specify the interval at which you want the operation to be executed.

</td>
</tr>
<tr>
<td valign="top">

Time Zone

</td>
<td valign="top">

Select the time zone that you want the scheduler to use as a reference for the date and time settings.

</td>
</tr>
<tr>
<td valign="top" rowspan="6">

*Schedule to Recur*

\(mails are to be polled periodically\)

</td>
<td valign="top">

Daily

</td>
<td valign="top">

Specify that the messages are to be polled daily \(either at a specific time as defined next to the checkbox *On Time* or in a specific time interval as defined next to the checkbox *Every*\).

</td>
</tr>
<tr>
<td valign="top">

Weekly

</td>
<td valign="top">

Specify that the messages are to be polled weekly. Select the checkboxes to indicate the days of the week on which you want the operation to be executed. Also specify the time \(checkbox *On Time*\) or interval \(checkbox *Every*\) for the schedule to recur.

</td>
</tr>
<tr>
<td valign="top">

Monthly

</td>
<td valign="top">

Specify that the messages are to be polled monthly. Select the day of the month on which you want the operation to be executed. Also specify the time \(checkbox *On Time*\) or interval \(checkbox *Every*\) for the schedule to recur.

</td>
</tr>
<tr>
<td valign="top">

On Time

</td>
<td valign="top">

Specify the time at which you want the operation to be executed.

</td>
</tr>
<tr>
<td valign="top">

Every

</td>
<td valign="top">

Specify the interval at which you want the operation to be executed.

</td>
</tr>
<tr>
<td valign="top">

Time Zone

</td>
<td valign="top">

Select the time zone that you want the scheduler to use as a reference for the date and time settings.

</td>
</tr>
</table>

Example: With the configuration shown in the next figure, the integration flow are activated every week on Monday to poll e-mails on this day every hour, between 00:00 and 24:00 \(Greenwich Time Zone\).

![](images/Mail_Adapter_Scheduler_dbf7aee.png)



> ### Note:  
> **Additional Notes**
> 
> -   To access an attachment, you have to use Groovy script or JavaScript.
> 
>     For more information about how to access attachments, see the following [blog](https://blogs.sap.com/2017/02/19/replacing-the-message-body-with-an-attachment/) and the documentation for the Script step.
> 
> -   To access the mail attributes \(Subject, From, or To\), you have to set them manually as *Allowed Headers* on the *Runtime Configuration* tab. This adds them to an allowlist.
> 
> -   The mail sender adapter can decrypt encrypted mails and verifies the signature of a signed message. You can access the results of the verification via headers and Exchange properties. For more information, see: [Headers and Exchange Properties Provided by the Integration Framework](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/d0fcb0988f034e889f611c6e36d43ad5.html?table_hhg_tbq_f2b=SAP_MAIL).
> 
> -   The property *Include Original Mail* was changed to allow the saving of duplicate attachments. Before this change, duplicate attachments got lost.

**Related Information**  


[Important Notes on Security Risks and Mailbox Settings](important-notes-on-security-risks-and-mailbox-settings-34aa095.md "")

[Blog on How to Connect CPI with Your On-Premise Mail Server](https://blogs.sap.com/2020/01/08/cloud-integration-connect-cpi-with-your-on-premise-mail-server/)

[Generating a Key Pair](../40-RemoteSystems/generating-a-key-pair-abb324d.md "")

[Options to Protect Mail Connections](options-to-protect-mail-connections-94bd058.md "")

[About Headers and Exchange Properties](about-headers-and-exchange-properties-0974c4f.md "")

[Headers and Exchange Properties Provided by the Integration Framework](headers-and-exchange-properties-provided-by-the-integration-framework-d0fcb09.md "")

[https://blogs.sap.com/2020/08/20/cloud-intgration-connect-to-microsoft-365-mail-with-oauth2/](https://blogs.sap.com/2020/08/20/cloud-intgration-connect-to-microsoft-365-mail-with-oauth2/)

