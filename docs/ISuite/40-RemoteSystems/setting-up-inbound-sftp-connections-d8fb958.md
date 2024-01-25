<!-- loiod8fb95805cca4dc88193d24a887c4f70 -->

# Setting Up Inbound SFTP Connections

Using the SFTP sender adapter, you connect an SAP Integration Suite tenant with an SFTP server so that the tenant can read data from the SFTP server \(in a process referred to as polling\).



In other words, the tenant sends a request to the SFTP server, but the data flow is in the opposite direction, from the SFTP server to the tenant, as illustrated in the figure. The direction of the request is indicated by the arrow next to the *R* notation in the following figure, the direction of the data flow by the direction of the connection arrow.

![](images/Inbound_Polling_Adapter_6acd655.png)

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

Public key

</td>
<td valign="top">

Tenant sends request to SFTP server to read files from the SFTP server \(referred to as polling\). SFTP server authenticates the tenant based on a public key.

Using this authentication option, the user \(performing the file transfer\) is authenticated by the public key associated with the user.

Recommended configuration option for secure communication is public key authentication.

More information:

[How SFTP Works](how-sftp-works-fc8467b.md)

</td>
<td valign="top">

Administrator of SFTP server:

-   Create user account.

-   Import public key \(alias `id_rsa` or `id_dsa`, as provided by tenant administrator, see below\) and import to SFTP server.


Tenant administrator:

-   In the integration flow for the SFTP sender adapter, choose *Public Key* authentication and specify the *User* \(which is defined on the SFTP server\).

-   Add host key of the SFTP server to known hosts file and deploy \(as *SSH Known Hosts* artifact\) on the tenant.

-   Maintain private key pair \(alias `id_rsa` or `id_dsa`\) in the tenant *Keystore*.

-   Export public key \(alias `id_rsa` or `id_dsa`\) from *Keystore* and hand over to SFTP server administrator.


More information: [Setting Up Inbound SFTP Connections \(Details\)](setting-up-inbound-sftp-connections-details-e72eba4.md)

</td>
</tr>
<tr>
<td valign="top">

User name/password

</td>
<td valign="top">

Tenant sends request to SFTP server to read files from the SFTP server \(referred to as polling\). SFTP server authenticates the tenant based on a public key.

Using this authentication option, the user \(performing the file transfer\) is authenticated based on credentials \(user name/password\).

More information:

[How SFTP Works](how-sftp-works-fc8467b.md)

</td>
<td valign="top">

Administrator of SFTP server:

-   Create user account.


Tenant administrator:

-   Specify user name/password in a *User Credentials* artifact and deploy artifact on tenant.

-   In the integration flow for the SFTP sender adapter, choose *User Name/Password* authentication and specify the *User Credentials* artifact \(and enter the credentials there\).

-   Add host key of the SFTP server to known hosts file and deploy \(as *SSH Known Hosts* artifact\) on the tenant.


More information: [Setting Up Inbound SFTP Connections \(Details\)](setting-up-inbound-sftp-connections-details-e72eba4.md)

</td>
</tr>
</table>

**Related Information**  


[Cloud Integration - How to Setup Secure Connections to SFTP Server](https://blogs.sap.com/2017/08/03/cloud-integration-how-to-setup-secure-connection-to-sftp-server/)

[Setting Up Inbound SFTP Connections \(Details\)](setting-up-inbound-sftp-connections-details-e72eba4.md "")

