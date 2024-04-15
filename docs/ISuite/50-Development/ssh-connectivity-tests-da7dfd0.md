<!-- loioda7dfd0f1fce401d99bca63e2de5bde1 -->

# SSH Connectivity Tests



## Context

When you have selected the SSH connection type, the test tool checks if the SSH outbound connection reaches the associated SFTP server.

Depending on the chosen authentication, the following is checked by the test:

-   If the server \(host\) is reachable for the tenant
-   If the configured `known_hosts` file deployed on the tenant contains the certificate of the SSH server.



## Procedure

1.  In the *Manage Security* section, select *Connectivity Tests*.

2.  Select *SSH*.

3.  Define the attributes for the test.

    **SSH Connection Test Options**


    <table>
    <tr>
    <th valign="top">

    Attribute
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Host* 
    
    </td>
    <td valign="top">
    
    Enter the host name of the receiver.

    The host name must **not** contain any path or schema \(for example, `myHost.org`\). In particular, you must **not** enter a URL as the host name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Port* 
    
    </td>
    <td valign="top">
    
    Enter the port that is to be used for outbound communication.

    Standard port is `22`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Type* 
    
    </td>
    <td valign="top">
    
    Select a proxy type from the drop-down list:

    -   *Internet* 

        or

    -   *On-Premise*

        This option is only available if *Cloud Integration* has been selected as runtime.

    -   *Manual* 

        This option is only available if *Edge* has been selected as runtime.


    For more information, see [Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md) 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Location ID* 

    \(only available if *On-Premise* is selected for *Proxy Type*\)
    
    </td>
    <td valign="top">
    
    To connect to a Cloud Connector instance associated with your account, enter the location ID that you 've defined for this instance, in the destination configuration on the cloud side
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Protocol*

    \(only available if *Manual* is selected for *Proxy Type*\)
    
    </td>
    <td valign="top">
    
    Specify the type of proxy server which is used to communicate to the SFTP server. Choose between the following options:

    -   *HTTP*

    -   *SOCKS Version 4*

    -   *SOCKS Version 5*



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Host*

    \(only available if *Manual* is selected for *Proxy Type*\)
    
    </td>
    <td valign="top">
    
    Enter the name of the proxy host to be used. For example: `proxy.mycompany.com`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Port*

    \(only available if *Manual* is selected for *Proxy Type*\)
    
    </td>
    <td valign="top">
    
    Enter the proxy port number to be used.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Credential Name*

    \(only available if *Manual* is selected for *Proxy Type* and if *HTTP* or *SOCKS Version 5* is selected for *Proxy Protocol*\)
    
    </td>
    <td valign="top">
    
    Enter the referenced credential name used for proxy authentication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Timeout \(ms\)* 
    
    </td>
    <td valign="top">
    
    Specifies a timeout \(in milliseconds\) after which the connection to the server \(host\) should be terminated. The default value is 10.000 ms.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authentication* 
    
    </td>
    <td valign="top">
    
    There are the following options:

    -   *None*

        SFTP server does not require any authentication of the calling component.

    -   *Public Key*

        SFTP server authenticates the calling component \(tenant\) based on a public key. If selected, a user name \(specified under *User Name*\) and the key \(specified under *Private Key Alias*\) are evaluated by the system to authenticate the tenant against the SFTP server.

    -   *User Credentials*

        SFTP server authenticates the calling component \(tenant\) based on the user name and password. To make this configuration setting work, you need to define the user name and password in a *User Credential* artifact and deploy the artifact on the tenant.

    -   *Dual*

        SFTP server authenticates the calling component \(tenant\) with two authentication methods: based on a public key and based on user credentials.

        At runtime, the system evaluates the values of additional parameters in the following way:

        -   For the authentication step based on user credentials: Credentials from the deployed artifact with the name given by the *Credential Name* parameter are evaluated by the system to authenticate the tenant against the SFTP server.

        -   For the authentication step based on public key: User name contained in the deployed artifact with name given by the *Credential Name* parameter and the key identified by the *Private Key Alias* parameter are evaluated by the system to authenticate the tenant against the SFTP server.




    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *User Name* 
    
    </td>
    <td valign="top">
    
    \(Only if *Public Key* or *Dual* is selected as *Authentication*\)

    Enter the ID of the user under which the tenant calls the SFTP server.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Private Key Alias* 
    
    </td>
    <td valign="top">
    
    \(Only if *Public Key* or *Dual* is selected as *Authentication*\)

    Alias to identify the private key in the keystore used for the communication with the SFTP server.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Credential Name*\)
    
    </td>
    <td valign="top">
    
    \(only if *User Credentials* or *Dual* is selected as *Authentication*\)

    Name of User Credentials artifact deployed on the tenant.

    This artifact contains user name and password that are used for authentication at the server.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Host Key Verification* 
    
    </td>
    <td valign="top">
    
    \(Only if *Public Key*, *User Credentials*, or *Dual* is selected as *Authentication*\).

    Verifies the host key.

    -   *Against Tenant*

        Host key is verified against *known\_hosts* artifact deployed on tenant.

    -   *Against Partner Directory*

        Host key is verified against known hosts defined in Partner Directory..

        > ### Note:  
        > You can also load a known\_hosts file from the Partner Directory. To point to the Partner Directory content, you need to set the following property in the integration flow before calling the SFTP receiver adater:
        > 
        > `SAP_FtpPdUri` 
        > 
        > You can use, for example, a Content Modifier for this purpose.
        > 
        > The value of the property needs apply to the following format:
        > 
        > `pd:partnerId:parameterId:Binary`

    -   Off


    > ### Note:  
    > It is recommended to use this option **with particular caution** when you have selected *User Credentials* as *Authentication* because in that case you take the risk that you forward the password to an unverified server.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Check Directory Access* 
    
    </td>
    <td valign="top">
    
    Only if *Public Key* or *User Credentials* is selected as *Authentication*\)

    Select this option if you like to check the access to the target directory. If you leave the *Directory* field empty, the default directory is your home directory.

    > ### Restriction:  
    > You can only specify sub-directories of the home directory.


    
    </td>
    </tr>
    </table>
    
    > ### Tip:  
    > You can also use the connectivity test to get the host key of the SFTP server.
    > 
    > 1.  Enter the host name of SFTP server.
    > 
    > 2.  For *Authentication* select *None*.
    > 
    > 3.  Choose *Send*.
    > 
    >     If the host name of SFTP server is correct, the test provides the message `Successfully reached host at xxx:22`.
    > 
    > 4.  Choose *Copy Host Key*.
    > 
    > 
    > This key is required to specify the known hosts file \(to be uploaded as *Known Hosts \(SSH\)* artifact\).
    > 
    > See:
    > 
    > -   [Maintaining the Known Hosts File for SFTP Connectivity](../40-RemoteSystems/maintaining-the-known-hosts-file-for-sftp-connectivity-514e383.md)
    > 
    > -   [Deploying an SSH Known Hosts Artifact](deploying-an-ssh-known-hosts-artifact-46da324.md)


**Related Information**  


[Setting Up Outbound SFTP Connections \(Details\)](../40-RemoteSystems/setting-up-outbound-sftp-connections-details-15401a7.md "")

