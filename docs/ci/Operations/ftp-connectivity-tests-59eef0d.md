<!-- loio59eef0d6e88d46dca119077896025d36 -->

# FTP Connectivity Tests

You can perform FTP connectivity tests to check the settings required by the FTP adapter.

**FTP Connection Test**


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

The host name must **not** contain any path or schema \(for example, `https://`\). In particular, you must **not** enter a URL as the host name.

</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Choose or enter the port that is to be used for outbound communication.

Standard port is `21 (FTPES/FTP)` or `990(FTPS)` depending on the network protocol.

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

*Encryption* 

</td>
<td valign="top">

Select the encryption type:

-   `Explicit FTPS` \(none\)

-   `Implicit FTPS` 
-   `Plain FTP` 

    If you select `Plain FTP`, there is no valid server certificate.




</td>
</tr>
<tr>
<td valign="top">

*Authentication* 

</td>
<td valign="top">

Choose which mechanism is to be used to authenticate against the server. Possible values are:

-   *None*

    No authentication is attempted. No credential can be chosen.

-   *User Credentials*




</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

</td>
<td valign="top">

\(Only if *User Credentials* has been chosen for *Authentication*\)

Choose the name of a deployed credential to use for authentication.

</td>
</tr>
<tr>
<td valign="top">

*Valid Server Certificate* 

</td>
<td valign="top">

Allows you to validate the server certificate.

When you’ve selected the *Valid Server Certificate* option \(which is the default setting\), the following checks are executed:

-   If the server certificate belongs to the server the client connects to,

-   If the certificate is signed by an instance the client trusts.


If it wasn’t successful and there’s an error message, you can unselect the *Validate Server Certificate* option.

</td>
</tr>
<tr>
<td valign="top">

*Check Directory Access* 

</td>
<td valign="top">

You can check wether you can access a directory.

</td>
</tr>
<tr>
<td valign="top">

*Directory*

</td>
<td valign="top">

Select this option if you like to check the access to the target directory. If you leave the *Directory* field empty, the default directory is your home directory.

</td>
</tr>
</table>

