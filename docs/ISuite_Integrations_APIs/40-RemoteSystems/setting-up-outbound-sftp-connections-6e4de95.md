<!-- loio6e4de95808134022b1543476eea0b1b3 -->

# Setting Up Outbound SFTP Connections

Using the SFTP receiver adapter, you connect the tenant with an SFTP server so that the tenant can write data to the SFTP server.



In other words, the tenant sends a request to the SFTP server, and the data flow is in the same direction, from the tenant to the SFTP server, as illustrated in the figure. The direction of the request is indicated by the arrow next to the *R* notation in the following figure, the direction of the data flow by the direction of the connection arrow.

![](images/Outbound_SFTP_Connection_9244016.png)

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

Public Key

</td>
<td valign="top">

Public Key authentication \(recommended\): Tenant sends request to SFTP server to write files to the SFTP server. SFTP server authenticates the tenant based on a public key.

With this is authentication option, the user \(performing the file transfer\) is authenticated by the public key associated with the user.

More information:

[How SFTP Works](how-sftp-works-fc8467b.md)

</td>
<td valign="top">

Administrator of SFTP server:

-   Create user account and provide user to the tenant admin.

-   Import public key \(as provided by tenant administrator, see below\) and import to SFTP server.


Tenant administrator:

-   Maintain private key pair \(*Create* or *Add*\) in the tenant *Keystore*. Provide an alias and reuse this alias in the subsequent steps.

-   In the integration flow for the SFTP receiver adapter, choose *Public Key*, provide the alias of the key in the key store and specify the *User* \(which is defined on the SFTP server and provided by the server admin\).

-   Add host key of the SFTP server to known hosts file and deploy \(as *SSH Known Hosts* artifact\) on the tenant.

-   Export public key \(the very same which you've just created or added\) from *Keystore* and hand over to SFTP server administrator.


More information: [Setting Up Inbound SFTP Connections \(Details\)](setting-up-inbound-sftp-connections-details-e72eba4.md)

</td>
</tr>
<tr>
<td valign="top">

User name/password

</td>
<td valign="top">

Tenant sends request to SFTP server to write files to the SFTP server. SFTP server authenticates the tenant based on a public key.

Using this authentication option, the user \(performing the file transfer\) is authenticated based on credentials \(user name/password\).

Supported by SFTP sender adapter.

More information:

[How SFTP Works](how-sftp-works-fc8467b.md)

</td>
<td valign="top">

Administrator of SFTP server:

-   Create user account.


Tenant administrator:

-   Specify user name/password in a *User Credentials* artifact and deploy artifact on tenant.

-   In the integration flow for the SFTP receiver adapter, choose *User Name/Password* authentication and specify the *User Credentials* artifact \(and enter the credentials there\).

-   Add host key of the SFTP server to known hosts file and deploy \(as *SSH Known Hosts* artifact\) on the tenant.


More information: [Setting Up Inbound SFTP Connections \(Details\)](setting-up-inbound-sftp-connections-details-e72eba4.md)

</td>
</tr>
</table>

**Related Information**  


[Setting Up Outbound SFTP Connections \(Details\)](setting-up-outbound-sftp-connections-details-15401a7.md "")

