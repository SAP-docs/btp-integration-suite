<!-- loio514e3837c060469d93aa71079ed4e261 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Maintaining SSH Known Hosts for SFTP Connectivity



## Context

The known hosts configuration is used to set up secure connectivity between Cloud Integration and an SFTP server using Secure Shell \(SSH\). It contains the addresses and public keys of trusted hosts \(SFTP servers\) that Cloud Integration can connect to.

SFTP stands for *Secure File Transfer Protocol*.

> ### Tip:  
> To get the host key for a trusted server, you can use the SSH connectivity test. See [SSH Connectivity Tests](../50-Development/ssh-connectivity-tests-da7dfd0.md).

> ### Example:  
> When your integration flow contains an SFTP receiver adapter with *Proxy Type* set to *On Premise*, the known host entry must match the virtual host name configured in the adapter.
> 
> For instance,
> 
> -   SFTP server name: `ftp123.myorg.com`
> -   SFTP receiver adapter address: `orgftp:22`
> 
> In this case, the known host entry must contain the virtual host name \(`orgftp`\) instead of the server host name \(`ftp123.myorg.com`\).

Perform the following steps to create or update the content of the known hosts file and to redeploy the updated file on the tenant.



## Working with Known Hosts Entries

You can create known host entries either by importing them from a file or by adding them manually using the Known Hosts dialog.

1.  Navigate to the *Monitor* section in the SAP Integration Suite, and go to *Manage Security* \> *Security Material* tile.
2.  Do one of the following:

    -   To create a new known hosts configuration, choose *Create* and select *Known Hosts \(SSH\)*.
    -   To update an existing configuration, select an existing Known Hosts \(SSH\) artifact and choose *Edit*.

    > ### Note:  
    > The dialog opens with an empty table for new configurations. For existing configurations, the table is automatically populated with deployed entries.

3.  In the *Create SSH Known Hosts* dialog, you can:
    -   Add entries manually using *Add*.
    -   Edit entries directly in the table.
    -   Remove entries using the :wastebasket: icon.
    -   Import entries from a file using *Browse*.

        > ### Caution:  
        > Using *Browse* replaces all existing known host entries in the table with the entries from the imported file.


4.  Review the entries in the table and choose *Deploy*.

The known hosts configuration is deployed and becomes effective for SFTP connectivity.

<a name="task_q41_5l3_tfc"/>

<!-- task\_q41\_5l3\_tfc -->

## Updating a Known Hosts File



## Procedure

1.  If you want to update an already deployed known hosts artifact on the *Manage Security Material* page, locate the *Known Hosts \(SSH\)* artifact that you want to update.

2.  Choose the :pencil2: button under the *Actions* tab.

3.  In the **Edit Known Hosts \(SSH\)** dialog, update the required entries by adding, editing, or deleting them directly in the table.

4.  Choose *Deploy* to apply the updated configuration.

    > ### Caution:  
    > SFTP scenarios might encounter failures during the period where the latest known host is not deployed in SAP Cloud Integration, so it’s recommended to perform these changes during a designated maintenance window when no critical SFTP integration flows are running and the business load is reduced. Once the known host is properly updated, these failures will automatically recover during the next schedule or execution.


<a name="task_ddq_jkm_5hc"/>

<!-- task\_ddq\_jkm\_5hc -->

## Known Host File Format



## Procedure

-   To create a new known hosts file, create a text file on your local system and add the entries using the structure shown below:

    > ### Code Syntax:  
    > ```
    > [<host name>] :<IP address> <public key algorithm> <base64 encoded public key>
    > ```
    > 
    > ```
    > [<host name>] :<port> <public key algorithm> <base64 encoded public key>
    > ```

-   Each line must contain the host name or IP address, the public key algorithm, and the public key. This information is typically provided by the participant system administrator during onboarding.

    > ### Sample Code:  
    > \[mysite.myorg.corp\]:29418 ssh-rsa AAAAB3NzaC1yc2EAAAADjkzfkjxc7awsL4bRmfvLQF+I/c81dB1onyFSH19plyfxdliuglzigutzutzuftzftTvAXXS21NYkGIxQ==

    > ### Tip:  
    > Add each trusted host in a separate row.


<a name="task_q41_5l3_yfc"/>

<!-- task\_q41\_5l3\_yfc -->

## Troubleshooting the Known Hosts File



<a name="task_q41_5l3_yfc__context_un2_tp3_tfc"/>

## Context


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Description

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

The connectivity test fails with a `reject HostKey` error

</td>
<td valign="top">

This issue usually occurs when the knownhost file in SAP Cloud Integration lacks a hostkey for the same host and algorithm.

</td>
<td valign="top">

Verify that the knownhost entries in SAP Cloud Integration are correctly updated.

</td>
</tr>
<tr>
<td valign="top">

The connectivity test fails with a `HostKey has been changed` error

</td>
<td valign="top">

This issue typically arises when the knownhost file in SAP Cloud Integration contains a hostkey for the same host and algorithm, but it does not match the host key sent by the SFTP server during the key exchange.

</td>
<td valign="top">

Ensure the knownhost entries in SAP Cloud Integration are properly updated.

</td>
</tr>
<tr>
<td valign="top">

The integration flows still fails with the error messages `reject HostKey` or `HostKey has been changed` during the execution, despite asuccessful connectivity test

</td>
<td valign="top">

 

</td>
<td valign="top">

Restart the integration flow to resolve the issue.

> ### Note:  
> Restarting the integration flow is not always necessary after deploying the correct known host file, as the error typically auto-recovers after the next poll or execution. This step is included as a fallback mechanism to clear stale knownhost entries if auto-recovery does not occur by the next poll or execution.



</td>
</tr>
</table>

**Related Information**  


[Deploying an SSH Known Hosts Artifact](../50-Development/deploying-an-ssh-known-hosts-artifact-46da324.md "This artifact type specifies the known hosts file used when configuring secure connectivity based on SSH File Transfer Protocol (SFTP).")

