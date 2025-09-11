<!-- loio514e3837c060469d93aa71079ed4e261 -->

# Maintaining the Known Hosts File for SFTP Connectivity



## Context

The known hosts file is used to set up the connection of Cloud Integration with an SFTP server using Secure Shell \(SSH\). It contains the addresses and public keys of trusted hosts \(SFTP servers\) to connect to.

SFTP stands for *Secure File Transfer Protocol*.

> ### Tip:  
> To get the host key for a trusted server, you can use the SSH connectivity test. See [SSH Connectivity Tests](../50-Development/ssh-connectivity-tests-da7dfd0.md).

> ### Example:  
> When your integration flow contains an SFTP receiver adapter with *Proxy Type* set to *On Premise*.
> 
> Let's assume that the name of the SFTP server is `ftp123.myorg.com`.
> 
> Furthermore, let's assume that in the SFTP receiver adapter you've specified the following *Address*: `orgftp:22`. In this case, the known host file must contain the virtual host name `(orgftp)` instead of the server host name `(ftp123.myorg.com)`.

Perform the following steps to create or update the content of the known hosts file and to redeploy the updated file on the tenant.

<a name="create_known_host"/>

<!-- create\_known\_host -->

## Creating the Known Hosts File



## Procedure

1.  If you'd like to create a new known hosts file, create a text file on your computer with the following content:

    The content of the known hosts file has the following structure:

    > ### Code Syntax:  
    > ```
    > [<host name>] :<IP address> <public key algorithm> <base64 encoded public key>
    > ```
    > 
    > ```
    > [<host name>] :<port> <public key algorithm> <base64 encoded public key>
    > ```

    > ### Note:  
    > For each trusted host, add a separate row.

    > ### Example:  
    > > ### Sample Code:  
    > > \[mysite.myorg.corp\]:29418 ssh-rsa AAAAB3NzaC1yc2EAAAADjkzfkjxc7awsL4bRmfvLQF+I/c81dB1onyFSH19plyfxdliuglzigutzutzuftzftTvAXXS21NYkGIxQ==

2.  Navigate to SAP Integration Suite *Monitor* section, and *Manage Security* \> *Security Material* tile.

3.  Choose *Upload* \> *Known Hosts \(SSH\)*.

4.  Select the known hosts file from your computer and choose *Deploy*.


**Related Information**  


[Deploying an SSH Known Hosts Artifact](../50-Development/deploying-an-ssh-known-hosts-artifact-46da324.md "This artifact type specifies the known hosts file used when configuring secure connectivity based on SSH File Transfer Protocol (SFTP).")

<a name="task_q41_5l3_tfc"/>

<!-- task\_q41\_5l3\_tfc -->

## Updating the Known Hosts File



## Procedure

1.  If you want to update an already deployed known hosts artifact on the *Manage Security Material* page, select the *Known Hosts \(SSH\)* artifact that you want to update.

2.  Download the known hosts file to your computer.

3.  Go to your file directory where the known hosts file is stored.

4.  Open the known hosts file \(using a text editor, for example, Notepad\).

5.  Copy and paste the host name and IP address of the SFTP server, the public key algorithm and the public key as new line into the known hosts file and save the file. This information has been provided by the participant system administrator during onboarding.

6.  Go to the SAP Cloud Integration *Monitor* section, and under *Manage Security*, select the *Security Material* tile.

7.  Choose *Upload Known Hosts \(SSH\)*.

8.  Select the known hosts file from your computer and choose *Deploy*.

    > ### Caution:  
    > SFTP scenarios might encounter failures during the period where the latest known host is not deployed in SAP Cloud Integration, so it’s recommended to perform these changes during a designated maintenance window when no critical SFTP integration flows are running and the business load is reduced. Once the known host is properly updated, these failures will automatically recover during the next schedule or execution.


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

