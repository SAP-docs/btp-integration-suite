<!-- loio8bf9ae4a12f145fd8d13e79849543439 -->

# Uploading an SSH Key

Upload an SSH key or a putty key to the tenant keystore.



## Context

It is possible to add an SSH or putty key to the keystore monitor instead of creating one. If you want to learn more about how to setup connections to the sftp servers, go and visit this blog: [Cloud Integration - How to Setup Secure Connection to sftp Server](https://blogs.sap.com/2017/08/03/cloud-integration-how-to-setup-secure-connection-to-sftp-server/)



## Procedure

1.  Choose the *Keystore* tile in the *Manage Security* section.

2.  On the *Current* tab, above the table, choose *Add* \> *SSH Key*.

3.  Enter an alias for the keystore entry \(*Alias* field\).

4.  Choose *Browse* and select the SSH key or putty key on your local disk.

5.  Specify the password for the key and define key specific values.

6.  Enter the required information for the certificate attributes.

    These attributes represent the coordinates of the organization associated with the certificate \(such like *Organization \(O\)*, *Organizational Unit \(OU\)*, *Country/Region \(C\)*, and so forth\).

    Note that for *Common Name \(CN\)* you need to specify an address \(for example, `myhost.com`\). Which address to specify, depends on the usage of the key pair. For example, if you use the key pair to sign a message, the address of the signing component is to be specified.

    For more information on certificates, see: [X.509 Certificates](../40-RemoteSystems/x-509-certificates-8d38a83.md).

7.  Check the settings vor the validity \(*Valid From* and *Valid Until* fields\) and, if desired, change them \(by default, the validity is set to 10 years\).

8.  Choose *Add* to create the key.


