<!-- loio6ad4956b4c4d484598ca9f7119313af6 -->

# Setting Up Inbound Mail Connections

Using the mail sender adapter, you connect the tenant with an e-mail server so that the tenant can read data from the e-mail server \(in a process referred to as polling\).



In other words, the tenant sends a request to the e-mail server, but the data flow is in the opposite direction, from the e-mail server to the tenant, as illustrated in the figure. The direction of the request is indicated by the arrow next to the *R* notation in the following figure, the direction of the data flow by the direction of the connection arrow.

![](images/Inbound_Mail_Connection_81cb93f.png)

Using the sender mail adapter, you can connect to mail servers through the following protocols: IMAP, POP3.

The following table lists the options for setting up secure connections for the different protocols. Consider the following table as a connection setup checklist. For a detailed description of the available properties for integration flow design, see the documentation of the individual adapter.

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

The mail sender adapter can download e-mails from an e-mail server and access the e-mail body content as well as attachments.

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

The mail sender adapter can download e-mails from an e-mail server and access the e-mail body content as well as attachments.

User name and password are sent in plain text \(only use together with SSL or TLS\).

</td>
</tr>
</table>

**Related Information**  


[Mail Adapter](../50-Development/mail-adapter-f1145cc.md "The mail adapter allows you to connect the tenant to an email server. The sender mail adapter can download e-mails and access the e-mail body content as well as attachments. The receiver mail adapter allows you to send encrypted messages by e-mail.")

