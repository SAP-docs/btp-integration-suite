<!-- loio15401a769405499d8de32232fbc407c7 -->

# Setting Up Outbound SFTP Connections \(Details\)



## Configuring the SFTP Client \(Tenant\)

In certain cases, you have the option to choose between the following authentication options for SFTP connectivity in the SFTP adapter:

-   User Name/Password

-   Public Key


The configuration depends on the chosen option.

When you've selected *Public Key*, perform the following steps:

1.  Create a known hosts file and enter the required data \(SFTP server host name, public key algorithm, and public key\).

2.  Generate an SFTP key pair and import it into the tenant keystore.

3.  Deploy the keystore and the known hosts file as artifact on the tenant.


When you've selected *User Name/Password*, perform the following steps:

1.  Create a User Credentials artifact that contains the credentials based on which the SFTP client connects to the SFTP server.

2.  Deploy the artifact on the tenant using the Web UI \(Monitoring application\).


> ### Note:  
> You can also load a known\_hosts file from the Partner Directory. To point to the Partner Directory content, you need to set the following property in the integration flow before calling the SFTP receiver adapter:
> 
> `SAP_FtpPdUri` 
> 
> You can use, for example, a Content Modifier for this purpose.
> 
> The value of the property needs to apply to the following format:
> 
> `pd:partnerId:parameterId:Binary`



## Configuring the SFTP Server \(To Which Data Is Io Be Written\)

Configure the authorized keys file on the SFTP server. It has to contain the public key of the SFTP client \(tenant\).

Who performs this task depends on whether the SFTP server is hosted by the customer or by SAP.



## Configuring the Integration Flow

Open the related integration flow and configure the **SFTP receiver adapter** to specify the technical details of how the data is to be written to the SFTP server.

**Related Information**  


[Blog: Dynamically Configure the SFTP Receiver Adapter](https://blogs.sap.com/2020/05/29/cloud-integration-dynamically-configure-the-sftp-receiver-adapter/)

[How SFTP Works](how-sftp-works-fc8467b.md "")

[Creating SFTP Keys](creating-sftp-keys-3485a75.md "You can set up reliable file transfer based on SSH File Transfer Protocol (SFTP). SFTP is an enhancement of the Secure Shell (SSH) network protocol.")

[Configure the SFTP Receiver Adapter](../50-Development/configure-the-sftp-receiver-adapter-4ef52cf.md "The SFTP receiver adapter connects an SAP Integration Suite tenant to a remote system using the SSH File Transfer protocol to write files to the system. SSH File Transfer protocol is also referred to as Secure File Transfer protocol (or SFTP).")

[Outbound SFTP With Public Key Authentication](outbound-sftp-with-public-key-authentication-d96b2d7.md "")

