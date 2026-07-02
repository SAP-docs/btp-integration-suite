<!-- loio46da32434a4e4bb8a86c5bf7e7de214d -->

# Deploying an SSH Known Hosts Artifact

This artifact type specifies the known hosts file used when configuring secure connectivity based on SSH File Transfer Protocol \(SFTP\).



## Context

An SSH known hosts artifact contains the public keys and addresses of trusted SFTP servers.



## Procedure

1.  Choose *Monitor*.

2.  Click the *Security Material* tile in the *Manage Security* section.

3.  Choose *Create* and select *Known Hosts \(SSH\)*.

4.  In the *Create SSH Known Hosts* dialog, you can import entries from a file using *Browse*, add entries manually using *Add*, or edit entries directly in the table.

    > ### Caution:  
    > Using *Browse* replaces all existing known host entries in the table with the entries from the imported file.

5.  Choose *Deploy*.

    > ### Note:  
    > For detailed instructions on creating, editing, and maintaining known host entries, see [Maintaining SSH Known Hosts for SFTP Connectivity](../ConnectionSetup/maintaining-ssh-known-hosts-for-sftp-connectivity-514e383.md).




## Results

When you refresh the *Manage Security Material* page, the new artifact is displayed in the table.

**Related Information**  


[Managing Security Material](managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

