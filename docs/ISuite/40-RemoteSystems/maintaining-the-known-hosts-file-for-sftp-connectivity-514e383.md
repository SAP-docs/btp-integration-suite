<!-- loio514e3837c060469d93aa71079ed4e261 -->

# Maintaining the Known Hosts File for SFTP Connectivity

Create a known hosts file and add new entries to an existing known hosts file.



<a name="loio514e3837c060469d93aa71079ed4e261__context_N10014_N10011_N10001"/>

## Context

The known hosts file ist used to set up the connection of Cloud Integration with an SFTP server using Secure Shell \(SSH\).

It contains the addresses and public keys of trusted hosts \(SFTP servers\) to connect to.

SFTP stands for *Secure File Transfer Protocol*.

Let's assume, a known hosts file has already been uploaded to the tenant \(as *Known Hosts \(SSH\)* artifact, see [Deploying an SSH Known Hosts Artifact](../50-Development/deploying-an-ssh-known-hosts-artifact-46da324.md)\).

> ### Tip:  
> To get the host key for a trusted server, you can use the SSH connectivity test \(see [SSH Connectivity Tests](../50-Development/ssh-connectivity-tests-da7dfd0.md)\).

Perform the following steps to update the content of the known hosts file and to redeploy the updated file on the tenant.



## Procedure

1.  If you'd like to create a new known hosts file, create a text file on your computer with the following content:

    The content of the known hosts file has the following structure:

    `[<host name>] :<IP address> <public key algorithm> <base64 encoded public key>`

    Example:

    `[mysite.myorg.corp]:29418 ssh-rsa AAAAB3NzaC1yc2EAAAADjkzfkjxc7awsL4bRmfvLQF+I/c81dB1onyFSH19plyfxdliuglzigutzutzuftzftTvAXXS21NYkGIxQ==`

    For each trusted host, add a separate row.

2.  Go to the SAP Integration Suite *Monitor* section, and under *Manage Security*, select the *Security Material* tile.

3.  Choose *Upload* \> *Known Hosts \(SSH\)*.

4.  Select the known hosts file from your computer and choose *Deploy*.

5.  If you like to update an already deployed known hosts artifact, on the *Manage Security Material* page select the *Known Hosts \(SSH\)* artifact that you like to update.

6.  Download the known hosts file to your computer.

7.  Go to your file directory where the known hosts file is stored.

8.  Open the known hosts file \(using a text editor, for example, Notepad\).

9.  Copy and paste the host name and IP address of the SFTP server, the public key algorithm and the public key as new line into the known hosts file and save the file. This information has been provided by the participant system administrator during onboarding.

    Note the following when your integration flow contains an SFTP receiver adapter with *Proxy Type* set to *On Premise*.

    Let's assume that the name of the SFTP server is `ftp123.myorg.com`.

    Furthermore, let's assume that in the SFTP receiver adapter you've specified the following *Address*: `orgftp:22`. In this case, the known host file must contain the virtual host name \(`orgftp`\) instead of the server host name \(`ftp123.myorg.com`\).


**Related Information**  


[Deploying an SSH Known Hosts Artifact](../50-Development/deploying-an-ssh-known-hosts-artifact-46da324.md "This artifact type specifies the known hosts file used when configuring secure connectivity based on SSH File Transfer Protocol (SFTP).")

