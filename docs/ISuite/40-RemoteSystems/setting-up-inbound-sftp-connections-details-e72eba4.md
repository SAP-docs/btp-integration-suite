<!-- loioe72eba4a3d894a248ed7686caf76a332 -->

# Setting Up Inbound SFTP Connections \(Details\)



## Configuring the SFTP Client \(Tenant\)

In certain cases, you have the option to choose between the following authentication options for SFTP connectivity in the SFTP adapter:

-   User Name / Password

-   Public Key


The configuration depends on the chosen option.

If you have selected *Public Key*, perform the following steps:

1.  Create a known hosts file and enter the required data \(SFTP server host name, public key algorithm, and public key\).

2.  Generate an SFTP key pair and import it into the tenant keystore.

3.  Deploy the keystore and the known hosts file as artifacts on the tenant.


If you have selected *User Name / Password*, perform the following steps:

1.  Create a User Credentials artifact containing the credentials to be used when the SFTP client connects to the SFTP server.

2.  Deploy the artifact on the tenant using the Web UI \(Monitoring application\).




## Configuring the SFTP Server \(from which data is to be read\)

Configure the authorized keys file on the SFTP server. It has to contain the public key of the SFTP client \(tenant\).

Who performs this task depends on whether the SFTP server is hosted by the customer or by SAP.



## Configuring the Integration Flow

Configure the **SFTP sender adapter** to specify the technical details of how the data is to be read from the SFTP server.

**Related Information**  


[Creating SFTP Keys](creating-sftp-keys-3485a75.md "You can set up reliable file transfer based on SSH File Transfer Protocol (SFTP). SFTP is an enhancement of the Secure Shell (SSH) network protocol.")

[Inbound SFTP With Public Key Authentication](inbound-sftp-with-public-key-authentication-97e2baa.md "")

[Configure the SFTP Sender Adapter](../50-Development/configure-the-sftp-sender-adapter-2de9ee5.md "The SFTP sender adapter connects an SAP Integration Suite tenant to a remote system using the SSH File Transfer protocol to read files from the system. SSH File Transfer protocol is also referred to as Secure File Transfer protocol (or SFTP).")

[Blog: Dynamically Configure the SFTP Receiver Adapter](https://blogs.sap.com/2020/05/29/cloud-integration-dynamically-configure-the-sftp-receiver-adapter/)

