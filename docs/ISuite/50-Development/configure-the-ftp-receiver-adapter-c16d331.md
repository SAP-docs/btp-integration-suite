<!-- loioc16d331e8ebb4a0e8c58af96bf519561 -->

# Configure the FTP Receiver Adapter

The FTP \(File Transfer Protocol\) receiver adapter connects SAP Integration Suite to a remote system using TCP \(Transmission Control Protocol\) to write files to the system.

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.





### How the FTP Receiver Adapter Works

If you’ve configured a receiver FTP adapter, message processing is performed as follows at runtime: The tenant sends a request to an FTP server \(think of this as the receiver system\), and the data flow is in the same direction, from the tenant to the FTP server. In other words, the tenant writes files to the FTP server \(from where the communication partner can read them\).

![](images/FTP_Receiver_2_8ca709e.png)

> ### Note:  
> In the following cases certain features might not be available for your current integration flow:
> 
> -   You are using a runtime profile other than the one expected. See: [Runtime Profiles](IntegrationSettings/runtime-profiles-8007daa.md).
> 
> -   A feature for a particular adapter or step was released after you created the corresponding shape in your integration flow.
> 
>     To use the latest version of a flow step or adapter – edit your integration flow, delete the flow step or adapter, add the step or adapter, and configure the same. Finally, redeploy the integration flow. See: [Updating your Existing Integration Flow](updating-your-existing-integration-flow-1f9e879.md).

[Overview of Integration Flow Editor](overview-of-integration-flow-editor-db10beb.md).

> ### Note:  
> Please consider the following when operating with the FTP Receiver Adapter:
> 
> -   Only the passive mode is supported for the FTP Receiver Adapter.
> 
> -   The FTP adapter does not support TLS session re-use.
> 
> -   The transfer mode is *BINARY*. You can set the charset by setting the `camelcharsetname` header.
> 
> -   You can establish a connection to your on-premise system by using Cloud Connector: [SAP Connectivity Service](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e933fd930039402c907d5afaa75eb0e1.html).
> 
> -   This adapter doesn’t support connections to SFTP servers. See: [Configure the SFTP Receiver Adapter](configure-the-sftp-receiver-adapter-4ef52cf.md).

Once you’ve created a receiver channel and selected the FTP receiver adapter, you can configure the following attributes. Select the *General* tab and provide values in the fields as follows.

**General**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Enter the name of the FTP channel.

</td>
</tr>
</table>

Select the *Target* tab and provide values in the fields as follows.

**Target**


<table>
<tr>
<th valign="top">

Parameters

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Directory* 

</td>
<td valign="top">

Use the relative path to write the file to a directory.

Example: `parentdirectory/childdirectory`

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*File Name* 

</td>
<td valign="top">

Name of the file to be written.

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

> ### Note:  
> If you don’t enter a file name and the parameter remains blank, the content of the `CamelFileName` header isn’tused as file name. If this header is specified, the Exchange ID is used as file name.

The endpoint URL that is actually used at runtime is displayed in the message processing log \(MPL\) in the message monitoring application \(MPL property `ProduceFile`\). Note that you can manually configure the endpoint URL using the *FileName* attribute of the FTP adapter. However, you can dynamically override the value of this attribute by using the Camel header `CamelFileName`.

*Append Timestamp* and dynamically configuring *File Name* \(through a Camel simple expression\) must not be used together. The reason is that using the *Append Timestamp* option results in generating a simple expression for the date. Both simple expressions result in an invalid expression that can’t be processed correctly.

</td>
</tr>
<tr>
<td valign="top">

*Append Timestamp* 

</td>
<td valign="top">

Appends a timestamp at the end of the file name.

If the file has an extension \(for example, .xml\), the timestamp is appended to the file extension itself. Example: If the file name is `myfile.xml`, the *Append Timestamp* option \(assuming the timestamp is ***Nov 30, 2015, 10:10:20***\) generates the following file name:

***myfile20151201170800.xml***

> ### Note:  
> Be aware of the following behavior if you’ve configured the file name dynamically: If you’ve selected the *Append Timestamp* option, the timestamp overrides the file name defined dynamically via the header \(`CamelFileName`\).
> 
> *Append Timestamp* and dynamically configuring *File Name* \(through a Camel simple expression\) must not be used together. The reason is that using the *Append Timestamp* option results in generating a simple expression for the date. Both simple expressions result in an invalid expression that can’t be processed correctly.

> ### Caution:  
> Note that in case files are processed quickly, the *Append Timestamp* option might not guarantee unique file names.



</td>
</tr>
<tr>
<td valign="top">

*Address* 

</td>
<td valign="top">

Host name or IP address of the FTP server and an optional port, for example, `my.host.org:21`.

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

The type of proxy that you’re using to connect to the target system.

-   Select *Internet* if you’re connecting directly to the FTP server.

-   Select *On-Premise* if you are connecting to an on-premise system.

    For more information, see: [Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md).

    For more information on how to use the *On-Premise* option to connect to an on-premise FTP server, check out the SAP Community blog [Cloud Integration – How to Connect to an On-Premise sftp server via Cloud Connector](https://blogs.sap.com/2018/11/16/cloud-integration-how-to-connect-to-an-on-premise-sftp-server-via-cloud-connector/).

-   Select *Dynamic* to let the system determine at runtime which proxy type to use. The value of property `SAP_FtpProxyType` is used for that purpose \(possible values `internet` or `onPremise`\).

    If you’ve selected this option and if the property is not defined \(for example, in a preceding step\), an error is raised at runtime.




</td>
</tr>
<tr>
<td valign="top">

*Location ID*

\(only if *On-Premise* or *Dynamic* is selected for *Proxy Type*

</td>
<td valign="top">

To connect to an SAP Cloud Connector instance associated with your account, enter the location ID that you defined for this instance in the destination configuration on the cloud side.

You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Encryption* 

</td>
<td valign="top">

Specify the transport encryption. You can choose between the following options:

-   *Dynamic*: Select this option to let the system determine at runtime which encryption to use. The value of property `SAP_FtpEncryption` is used for that purpose. Possible values are `ftp`, `ftps` or `ftpes`.

    -   ftp: Plain FTP – no encryption

    -   ftps: Implicit FTPS

    -   ftpes: Explicit FTPS


    If you’ve selected this option and if the property isn’t defined \(for example, in a preceding step\), an error is raised at runtime.

-   *Explicit FTPS*: After an initial connection, the client with send `AUTH TLS` command to the server and initial the handshake this way. Afterwards, the communication will be encrypted. Unless you specified a port in the address, the default port will be 21.

-   *Implicit FTPS*: The client will connect to the server with a TLS connection. This means the client starts the handshake at the beginning of the communication. Unless you specified a port in the address, the default port is 990.

-   *Plain FTP - no encryption*: No encryption will be applied, for productive use \(not recommended\). Unless you specified a port in the address, the default port is 21.




</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)* 

</td>
<td valign="top">

Maximum time to wait for the FTP server to be contacted while establishing a connection. The default is set to 10000 ms.

If the property `SAP_FtpTimeout` is defined, its value is used to specify this parameter at runtime.

> ### Note:  
> There’s another fix timeout which is relevant when the client is waiting for the server to respond to commands. It is set to 5 min.



</td>
</tr>
<tr>
<td valign="top">

*Maximum Reconnect Attempts* 

</td>
<td valign="top">

Maximum number of attempts allowed to reconnect to the FTP server.

Default value: 3

Use 0 to disable this behavior.

If the property `SAP_FtpMaxReconnect` is defined, its value is used to specify this parameter at runtime.

</td>
</tr>
<tr>
<td valign="top">

*Reconnect Delay \(in ms\)* 

</td>
<td valign="top">

The amount of time the system waits before attempting to reconnect to the FTP server.

Default Value: 1000ms

If the property `SAP_FtpMaxReconDelay` is defined, its value is used to specify this parameter at runtime.

</td>
</tr>
<tr>
<td valign="top">

*Automatically Disconnect* 

</td>
<td valign="top">

Disconnect from the FTP server after each message processing.

If the property `SAP_FtpDisconnect` is defined, its value is used to specify this parameter at runtime \(possible values: `true` and `false`\).

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

**Processing**


<table>
<tr>
<th valign="top">

Parameters

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Change Directories Stepwise* 

</td>
<td valign="top">

If selected, changes directory levels step by step \(selected by default\).

If the property `SAP_FtpStepwise` is defined, its value is used to specify this parameter at runtime \(possible values: `true` and `false`\).

</td>
</tr>
<tr>
<td valign="top">

*Create Directories*

</td>
<td valign="top">

If selected, creates missing directory levels as provided in the file's pathname \(selected by default\).

If the property `SAP_FtpCreateDir` is defined, its value is used to specify this parameter at runtime \(possible values: `true` and `false`\).

</td>
</tr>
<tr>
<td valign="top">

*Flatten File Names* 

</td>
<td valign="top">

Flatten the file path by removing the directory levels so that only the file names are considered and they are written under a single directory.

If the property `SAP_FtpFlattenFileName` is defined, its value is used to specify this parameter at runtime \(possible values: `true` and `false`\).

</td>
</tr>
<tr>
<td valign="top">

*Prevent Directory Traversal* 

</td>
<td valign="top">

If the file contains any backward path traversals such as `\..\` or `/../..`, this carries a potential risk of directory traversal. In such a case, message processing is stopped with an error. The unique message ID is logged in the message processing log.

> ### Note:  
> We recommend that you specify the *Directory* and *File Name* fields to avoid any security risks. If you provide these fields, the header is not considered.



</td>
</tr>
<tr>
<td valign="top">

*Handling for Existing Files*

</td>
<td valign="top">

Define how existing files should be treated.

-   *Append*: adds message to existing files

-   *Fail*: sends an error message in case files already exists

-   *Ignore*: ignores the existing file and doesn't send an error message

-   *Override*: replaces existing file and saves it under existing name


You can configure this parameter by entering a dynamic expression such like `${property.property_name}` or `${header.header_name}` \(see: [Dynamically Configure Integration Flow Parameters](dynamically-configure-integration-flow-parameters-fff5b2a.md)\).

</td>
</tr>
<tr>
<td valign="top">

*Use Temporary File* \(only if *Override* is selected for *Handling for Existing Files\)*

</td>
<td valign="top">

This option is used to write a file by using a temporary name and then, after the process has been completed, rename it to the actual name. It can be used to identify files which are being written. It also blocks consumers \(not using exclusive read locks\) from reading files in progress. It’s often used by the FTP server when uploading big files.

</td>
</tr>
</table>

