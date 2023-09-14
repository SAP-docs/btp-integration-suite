<!-- loio5e16205804a74e81b5f22a43bccb64c3 -->

# Renewal of the SFTP Client Key \(on Tenant\)

In this use case, an SSH key pair is renewed on the SFTP client \(tenant\).

> ### Note:  
> It depends on the **operating model** whether the tenant administrator and the integration developer are at the customer or at SAP. In the **customer-managed operating model**, the tenant administrator and integration developer tasks are performed by the customer. In the **SAP-managed operating model**, these tasks are performed by SAP.

Security artifact renewal has to be performed in the following sequence:

1.  Tenant administrator: Generates new key pair for the SFTP client.
2.  Tenant administrator: Exports the public key from the keystore and provides the SFTP server administrator with the public key.
3.  SFTP server administrator: Imports the public key \(provided by the tenant administrator\) into the SFTP server truststore.
4.  SFTP server administrator: Informs tenant administrator that public key has been imported into the truststore of the SFTP server.
5.  Tenant administrator: Exchanges in the keystore the old key pair with the new one.

**Related Information**  


[Creating SFTP Keys](../ConnectionSetup/creating-sftp-keys-3485a75.md "You can set up reliable file transfer based on SSH File Transfer Protocol (SFTP). SFTP is an enhancement of the Secure Shell (SSH) network protocol.")

[Involved Roles](involved-roles-3968091.md "The security artifact renewal process requires that different persons perform a sequence of steps in a coordinated way on each side of the communication. The exact sequence depends on the kind of security material which is renewed and on the use case.")

[Creating a Key Pair/SSH Key Pair](creating-a-key-pair-ssh-key-pair-b8a8601.md "Create a key pair or a Secure Shell (SSH) key pair.")

