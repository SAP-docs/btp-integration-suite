<!-- loioe3dce8814857444eacbcf0d3ca4e6706 -->

# SFTP Adapter

Use SFTP adapter to encrypt and exchange sensitive business data between trading partners.



<a name="loioe3dce8814857444eacbcf0d3ca4e6706__section_eft_f5j_rlb"/>

## Use



The SFTP Adapter connects an SAP Cloud Integration tenant to a remote system using the SSH File Transfer protocol to write files to the system. The SFTP adapter uses a certificate and keystore to authenticate the file transfer unlike the standard FTP. The SFTP adapter achieves secure transfer by encrypting sensitive information before transmitting it on the network. It uses SSH protocol to transfer files.



> ### Note:  
> If you want to dynamically override the configuration of the adapter, you can set the following header before calling the SFTP adapter:
> 
> -   CamelFileName
> 
>     Overrides the existing file and directory name that is set directly in the endpoint.
> 
>     This header can be used to dynamically change the name of the file and directory to be called.

The following examples show the header CamelFileName, read via XPath from the payload, or set using an expression:

**Example of Header**


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Type

</th>
<th valign="top">

Data Type

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

CamelFileName

</td>
<td valign="top">

xpath

</td>
<td valign="top">

java.lang.String

</td>
<td valign="top">

/p:<XYZ\>MessageBulk/<XYZ\>Message/FileName/text\(\)

</td>
</tr>
<tr>
<td valign="top">

CamelFileName

> ### Note:  
> Be aware of the following behavior if you have configured the file name dynamically: If you have selected the *Append Timestamp* option, the timestamp overrides the file name defined dynamically via the header \(`CamelFileName`\).



</td>
<td valign="top">

expression

</td>
<td valign="top">

java.lang.String

</td>
<td valign="top">

<myapplication\>/template/out/output$\{date:now:yyyyMMddHHmmss\}.xml

</td>
</tr>
</table>

CI-PI currently supports the following ciphers for SSH \(SFTP\) communication: blowfish-cbc,3des-cbc,aes128-cbc,aes192-cbc,aes256-cbc,aes128-ctr,aes192-ctr,aes256-ctr,3des-ctr,arcfour,arcfour128,arcfour256.

> ### Caution:  
> The ciphers listed above can change in the future. New ciphers can be added and existing ones can be removed in case of security weaknesses. In such cases, you will have to change the ciphers on the SFTP server and reconfigure the integration flows that contain SFTP adapter. SAP will inform customers, if necessary.

> ### Caution:  
> If you select *Run Once* option in the *Scheduler*, you see messages triggered from all the integration flows with this setting after a software update. After the latest software is installed on a cluster, it is restarted.
> 
> This results in the integration flows getting deployed again and you see messages from these integration flows with *Run Once* setting.

**Related Information**  


[Configure the SFTP Sender Adapter](configure-the-sftp-sender-adapter-2de9ee5.md "The SFTP sender adapter connects an SAP Integration Suite tenant to a remote system using the SSH File Transfer protocol to read files from the system. SSH File Transfer protocol is also referred to as Secure File Transfer protocol (or SFTP).")

[Configure the SFTP Receiver Adapter](configure-the-sftp-receiver-adapter-4ef52cf.md "The SFTP receiver adapter connects an SAP Integration Suite tenant to a remote system using the SSH File Transfer protocol to write files to the system. SSH File Transfer protocol is also referred to as Secure File Transfer protocol (or SFTP).")

