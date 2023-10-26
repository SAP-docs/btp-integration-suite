<!-- loio8b112ba77c3b4896a95b711840b46627 -->

# Setting Up Outbound Mail Connections

Using the mail receiver adapter, you connect the tenant with an e-mail server so that the tenant can send emails to the e-mail server.



In other words, the tenant sends a request to the e-mail server, and the data flow is in the same direction, from the tenant to the e-mail server, as illustrated in the figure. The direction of the request is indicated by the arrow next to the *R* notation in the following figure, the direction of the data flow by the direction of the connection arrow.

![](images/Outbound_Mail_Connection_f690647.png)

Using the mail receiver adapter, you can connect to mail servers through the SMTP protocol.

The following table lists the options for setting up secure connections. Consider the following table as a connection setup checklist. For a detailed description of the available properties for integration flow design, see the documentation of the individual adapter.

****


<table>
<tr>
<th valign="top">

Authentication

</th>
<th valign="top">

Description

</th>
<th valign="top">

How to configure \(checklist\) ...

</th>
</tr>
<tr>
<td valign="top">

Encrypted user/password

</td>
<td valign="top">

User name and password are hashed before being sent to the server.

</td>
<td valign="top" rowspan="2">

-   Create and deploy a *User Credentials* artifact that contains the credentials \(user name and password\) of the e-mail account owner.

-   In the integration flow / mail receiver adapter, specify the mail adapter settings. In particular, as *Credential Name* specify the name of the *User Credentials* artifact to use for this connection.




</td>
</tr>
<tr>
<td valign="top">

Plain user/password

</td>
<td valign="top">

User name and password are sent in plain text \(only use together with SSL or TLS\).

</td>
</tr>
</table>

**Related Information**  


[Mail Adapter](../50-Development/mail-adapter-f1145cc.md "The mail adapter allows you to connect the tenant to an email server. The sender mail adapter can download e-mails and access the e-mail body content as well as attachments. The receiver mail adapter allows you to send encrypted messages by e-mail.")

