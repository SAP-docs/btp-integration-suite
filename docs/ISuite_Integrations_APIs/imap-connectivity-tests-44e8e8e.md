<!-- loio44e8e8ed5cc84db5ba79578f61d4ad4a -->

# IMAP Connectivity Tests

When you have chosen the IMAP \(Internet Message Access Protocol\) connection, the test tool checks the following:

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

-   If the receiver \(host\) is reachable for the tenant

**IMAP Connectivity Test Options**


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

*Host* 

</td>
<td valign="top">

Enter the host name of the receiver.

The host name must **not** contain any path or schema, for example, `https://`\). In particular, you must **not** enter a URL as the host name.

</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Enter the port that is to be used for outbound communication.

Standard port is `143 (IMAP/STARTTLS)` or `993/IMAPS` 

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

Select a proxy type from the drop-down list:

-   `Internet` 

    or

-   `On-Premise`



</td>
</tr>
<tr>
<td valign="top">

*Location ID*

</td>
<td valign="top">

Only if `On-Premise` is selected as *Proxy Type*.

To connect to an SAP Cloud Connector instance associated with your account, enter the location ID that you 've defined for this instance, in the destination configuration on the cloud side

</td>
</tr>
<tr>
<td valign="top">

*Protection* 

</td>
<td valign="top">

Select the protection type:

-   `Off` \(none\)

-   `IMAPS` 

    > ### Note:  
    > The secure protocol is only available for the *Proxy Type* `Internet`.

-   `STARTTLS Mandatory`
-   `STARTTLS Optional`



</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Choose the mechanism to authenticate against the server. Possible values are:

-   *Encrypted User/Password*

    The user name and password aren’t sent in plain text to the server. This authentication mechanism is secure even without a secure connection.

-   *Plain User/Password*

    The user name and password are sent in plain text. Use this option only together with SSL or TLS, as otherwise an attacker could obtain the password.




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Enter a credential name or select one from the drop-down list.

</td>
</tr>
<tr>
<td valign="top">

*Validate Server Certificate* 

</td>
<td valign="top">

Allows you to validate the server certificate \(only when *Protection* is not `Off`\).

When you’ve selected the *Validate Server Certificate* option \(which is the default setting\), the following checks are executed:

-   If the server certificate belongs to the server the client connects to,

-   If the certificate is signed by an instance the client trusts.


If it wasn’t successful and there’s an error message, you can unselect the *Validate Server Certificate* option.

</td>
</tr>
<tr>
<td valign="top">

-   *List Folders*

    or for

-   *Check Mailbox Content*



</td>
<td valign="top">

If you check*List Folders*, you get a list of mail folders.

If you select *Check Mailbox Content*, the folders are checked and the total number of mails and the number of unread mails is displayed.

</td>
</tr>
<tr>
<td valign="top">

*Folder* \(mandatory\)

</td>
<td valign="top">

If you select *Check Mailbox Content*, you can specify a folder.

</td>
</tr>
</table>

If the connectivity test was successful, you get the information about the different checks. The server certificates are displayed. A download option is available allowing you to save and add them to your trust store.

