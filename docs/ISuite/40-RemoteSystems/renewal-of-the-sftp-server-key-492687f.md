<!-- loio492687fbb8e442e78fc481f2bca26cdf -->

# Renewal of the SFTP Server Key

In this use case, an SSH key pair is renewed on the SFTP server.

Security artifact renewal has to be performed in the following sequence:

1.  SFTP server administrator: Creates new server key pair.
2.  SFTP server administrator: Provides tenant administrator with the public key and informs him that the key will be exchanged on the SFTP server at a certain point in time.
3.  Tenant administrator: Adds the new public key to the *known hosts* file.

    After that step has been performed, the client \(tenant\) trusts the server either he has the old or new key.

4.  Tenant administrator: Removes the old public key entry form the *known hosts* file after the aggreed point in time.

**Related Information**  


[Creating SFTP Keys](creating-sftp-keys-3485a75.md "You can set up reliable file transfer based on SSH File Transfer Protocol (SFTP). SFTP is an enhancement of the Secure Shell (SSH) network protocol.")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

