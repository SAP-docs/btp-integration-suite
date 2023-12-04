<!-- loio46da32434a4e4bb8a86c5bf7e7de214d -->

# Deploying an SSH Known Hosts Artifact

This artifact type specifies the known hosts file used when configuring secure connectivity based on SSH File Transfer Protocol \(SFTP\).



## Context

The known hosts file contains the public keys and addresses of the trusted SFTP servers.



## Procedure

1.  Choose *Monitor* \> *Integrations and APIs*.

2.  Select the target runtime \(*Runtime* parameter\).

    This information is only relevant for Edge Integration Cell runtime.

    For more information on how to manage security artifacts for Edge Integration Cell, see [Manage Security for Edge Integration Cell](../manage-security-for-edge-integration-cell-1783cf8.md).

3.  Click the *Security Material* tile in the *Manage Security* section.

4.  Choose *Add*.

5.  As *Type*, select *Known Hosts \(SSH\)*.

6.  Browse to the known hosts file on your computer.

7.  Choose *Deploy*.




## Results

When you refresh the *Manage Security Material* page, the new artifact is displayed in the table.

> ### Note:  
> Note the following when you have activated Edge Integration Cell:
> 
> -   You can assign one *Known Hosts \(SSH\)* artifact exactly to one runtime.
> 
> -   Apply the following rules for the artifact name:
> 
>     -   The maximum number of characters is 30.
> 
>     -   Use only lower-case ASCII alphanumeric characters.
> 
>     -   The artifact name must start and end with a letter.
> 
> 
> -   If you leave the *Name* parameter empty, the system sets the artifact name to *known.hosts*.
> 
>     If you don't leave the *Name* parameter empty, the system sets the name to *known.hosts-<custom name\>*. In other words, the prefix *known.hosts-* is added by the system.

**Related Information**  


[Managing Security Material](managing-security-material-b8ccb53.md "The Manage Security Material area provides an overview of security-related artifacts.")

