<!-- loio8c5436aba9c04606a6a611b50cc8c064 -->

# Renewal of User on SFTP Server

Files are stored on the SFTP server in directories referred to as mailboxes. For each mailbox, a user is specified to control access to the data. In this use case, the mailbox user on the SFTP server is changed.

There are two sub use cases, depending on whether the tenant pulls data from or pushes data to the SFTP server.



## Tenant Pulls Data from SFTP Server

User renewal has to be performed in the following sequence:

1.  SFTP server administrator: Creates a new user on the SFTP server with all relevant configurations \(for example, mailbox\).
2.  SFTP server administrator: Informs the tenant administrator that an old user shall be exchanged by a new one and that the new user already exists on the SFTP server.
3.  Tenant administrator: Informs integration developer that he should exchange the old SFTP user with the new one \(in the corresponding integration flow\).
4.  Integration developer: Exchanges the old SFTP user with the new one in the integration flow.
5.  Integration developer: Informs the tenant administrator that user has been exchanged.
6.  Tenant administrator: Informs SFTP server administrator that the user has been exchanged.
7.  SFTP server administrator: Makes sure that all data of the old user has been fetched by the tenant.

    If this is not the case he transfers the relevant data into the mailbox of the new user.




## Tenant Pushes Data to SFTP Server

User renewal has to be performed in the following sequence:

1.  SFTP server administrator: Creates a new user on the SFTP server with all relevant configurations \(for example, mailbox\).
2.  SFTP server administrator: Informs the tenant administrator that an old user shall be exchanged by a new one and that the new user already exists on the SFTP server.
3.  Tenant administrator: Informs the integration developer that he should exchange the old SFTP user with the new one \(in the corresponding integration flow\).
4.  Integration developer: Exchanges the old SFTP user with the new one in the integration flow.
5.  Integration developer: Informs the tenant administrator that user has been exchanged.
6.  Tenant administrator: Informs the SFTP server administrator that the user has been exchanged.
7.  If a pulling component relies on the data, the SFTP server administrator makes sure that the poller has read all data from the mailbox of the old user. If this is not the case, the SFTP server administrator transfers the data into the mailbox of the new user.

**Related Information**  


[Creating SFTP Keys](creating-sftp-keys-3485a75.md "You can set up reliable file transfer based on SSH File Transfer Protocol (SFTP). SFTP is an enhancement of the Secure Shell (SSH) network protocol.")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

