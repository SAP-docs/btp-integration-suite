<!-- loio40eb051fe59d452ca3704750250c6940 -->

# POP3 Connectivity Tests

When you have chosen the POP3 \(Post-Office\_Protocol\) the test tool checks the following.

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).

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

The host name must **not** contain any path or schema for example, `https://`\). In particular, you must **not** enter a URL as the host name.

</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Enter the port that is to be used for outbound communication.

Standard port is `110` or `995` 

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

Select a proxy type from the drop-down list:\(

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

Only if `On-Premise` is selected as *Proxy Ttype*.

To connect to an SAP Cloud Connector instance associated with your account, enter the location ID that you 've defined for this instance, in the destination configuration on the cloud side

</td>
</tr>
<tr>
<td valign="top">

*Protection*

Thi

</td>
<td valign="top">

Select the protection to be used, from the drop-down list.

> ### Note:  
> STARTTLS is not supported for port 995. For port `110`, STARTTLS is supported and checked.

Select the protection type:

-   `Off` \(none\)

-   `POP3S`

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

Choose which mechanism is to be used to authenticate against the server. Possible values are:

-   *Encrypted User/Password*

    The user name and password are not sent in plain text to the server. This authentication mechanism is secure even without a secure connection.

-   *Plain User/Password*

    The user name and password are sent in plain text. You should only use this option together with SSL or TLS, as otherwise an attacker could obtain the password.




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*\(mandatory\)

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

When you have selected the *Validate Server Certificate* option \(which is the default setting\), the following checks are executed:

-   If the server certificate belongs to the server the client connects to

-   If the certificate is signed by an instance the client trusts


If it was not successful and there is an error message, you can unselect the *Validate Server Certificate* option.

</td>
</tr>
<tr>
<td valign="top">

*Check Mailbox Content* 

</td>
<td valign="top">

If you check *Check Mailbox Content* the mailbox is checked and the total number of mails in the inbox is displayed.

</td>
</tr>
</table>

If the connectivity test was successful, you get the information about the different checks. The server certificates are displayed. A download option is available allowing you to save and add them to your trust store.

