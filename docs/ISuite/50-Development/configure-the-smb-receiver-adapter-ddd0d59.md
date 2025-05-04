<!-- loioddd0d599610a421e9670f08cfe624fcb -->

# Configure the SMB Receiver Adapter

The SMB \(Server Message Block\) receiver adapter connects SAP Integration Suite to a remote share drive using TCP \(Transmission Control Protocol\) to perform read and write operations including create, delete, rename etc.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loioddd0d599610a421e9670f08cfe624fcb__section_ib4_gbz_5cc"/>

## How the SMB Receiver Adapter Works

If you have configured a receiver SMB adapter, an application \(or the user of an application\) can access files in the following manner:

The SAP Integration Suite tenant sends a file or folder operation request to an SMB share drive and the data flow is in the same direction, from the tenant to the SMB server.

Once you have created a receiver channel and selected the SMB receiver adapter, you can configure the following attributes.

Select the *Connection* tab. The *Connection* tab contains the connection and the authentication parameters required to connect to SMB Server.

**Connection**


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

*Address*

</td>
<td valign="top">

Specify the hostname of the SMB Server.

Example: `smb1.servershare.com:445`

</td>
</tr>
<tr>
<td valign="top">

*Domain*

</td>
<td valign="top">

If required, specify the domain used for authentication.

> ### Note:  
> This is an optional field.



</td>
</tr>
<tr>
<td valign="top">

*SMB Dialect*

</td>
<td valign="top">

Select the SMB dialect or version to be used for communication.

> ### Note:  
> For SMB Dialect selection, take into consideration that SMB 2.x versions do not support encryption.

Default: *Auto*

</td>
</tr>
<tr>
<td valign="top">

*Share*

</td>
<td valign="top">

Specify the SMB share folder which represents the network resource.

Example: Assuming the mount path is `\\ServerName\ShareName`, you must specify *Share* as `ShareName`.

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the authentication type for connecting to the SMB server.

-   *Basic Authentication*




</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the name of the security artifact used for authentication.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in secs\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in seconds\) for a response message from the SMB Server. .

Default: `180`

</td>
</tr>
<tr>
<td valign="top">

*Enable Encryption*

</td>
<td valign="top">

Enable to turn on encrypted communication between the client and server.

> ### Note:  
> For any SMB 3.x dialect, this is a request to the server to turn on encryption if the server also supports it.



</td>
</tr>
<tr>
<td valign="top">

*Enable DFS*

</td>
<td valign="top">

Enable Distributed File System Share between the client and the server.

</td>
</tr>
<tr>
<td valign="top">

*Enable Signing*

</td>
<td valign="top">

Enable SMB Signing between the client and the server.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Reconnect Attempts*

</td>
<td valign="top">

Specify the maximum number of retries permissible for reconnection to the SMB server before message processing starts.

Default: `3`

</td>
</tr>
</table>

Switch to the *Processing* tab. The *Processing* tab contains all operation related configurations for the SMB Receiver adapter.

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

*Operation*

</td>
<td valign="top">

Select an operation to be executed.

</td>
</tr>
<tr>
<td valign="top">

*Directory*

</td>
<td valign="top">

Specify the target directory. Use `\` for the root directory.

Default: `\`

Example: `folder\subfolder1`

</td>
</tr>
<tr>
<td valign="top">

*File Name*

</td>
<td valign="top">

Specify the filename including the extension.

Example: `read.txt`

> ### Note:  
> The filename from Sender is available via the property `${property.CamelFileNameOnly}` for use through the iflow lifecycle and can be used in the Receiver.



</td>
</tr>
<tr>
<td valign="top">

*Object Type*

\(Only available if parameter *Operation* has option *List Objects* selected\).

</td>
<td valign="top">

Select the type of object to be listed.

Acceptable Values:

-   *All*
-   *File*
-   *Directory*



</td>
</tr>
<tr>
<td valign="top">

*Maximum File Size \(in MB\)*

\(Only available if parameter *Operation* has option *Read File* selected\).

</td>
<td valign="top">

Specify maximum size for the file to be picked up.

Example: `40`

</td>
</tr>
<tr>
<td valign="top">

*Append Timestamp*

</td>
<td valign="top">

Enable to append timestamp to the filename.

Example: If the file name is `myfile.xml`, the Append Timestamp \(for instance, `Mar 2, 1999, 09:07:05`\) option generates `myfile762599225000.xml` 

</td>
</tr>
<tr>
<td valign="top">

*Append MessageId*

</td>
<td valign="top">

Enable to append Messageid to the filename.

Example: If the file name is`myfile.xml`, the Append MessageId \(for instance, `313214755`\) option generates `myfile313214755.xml` 

</td>
</tr>
<tr>
<td valign="top">

*Existing File Handling*

</td>
<td valign="top">

Select to specify behaviour in case the file to be created already exists.

-   *Append* adds the payload to an existing file.

    > ### Note:  
    > Don't use the *Append* mode if more than one process is appending to an existing file in parallel as this might cause inconsistencies.

-   *Fail* sends an error message in case the file already exists.
-   *Ignore* disregards the file creation operation without sending any error message.
-   *Override* replaces existing file by overwriting content with new payload.



</td>
</tr>
<tr>
<td valign="top">

*Empty File Handling* 

</td>
<td valign="top">

Select to specify behaviour in case the file to be created is empty.

-   *Ignore* disregards the empty file and does not send an error message.
-   *Proceed with Empty File* creates a file even if payload is empty.

    Default: *Proceed with Empty File*




</td>
</tr>
<tr>
<td valign="top">

*Read Lock Strategy*

\(Only available if parameter *Existing File Handling* has option *Override* selected\).

</td>
<td valign="top">

Select read lock strategy for file creation operation.

-   *None* does not employ any read lock strategy during file creation.
-   *Rename* writes to a temporary file if the file is locked. Once file write is completed, the file is saved under the original name.

Example: If the file name is `myfile.xml`, Rename enables writes to the `myfile_temp.xml`

Once write is completed, it is saved as `myfile.xml`

Default:*None*

</td>
</tr>
<tr>
<td valign="top">

*Temporary File Name*

\(Only available if parameter *ReadLock Strategy* has option *Rename* selected\).

</td>
<td valign="top">

Select the unique temporary filename pattern.

> ### Note:  
> The filename has to be unique so that the temporary file is not overwritten by messages running in parallel. This can be achieved by using variable parts in the filename.

-   *$\{file:name\}.temp*

-   *target\_$\{exchangeId\}.temp*




</td>
</tr>
<tr>
<td valign="top">

*Original Object Name*

</td>
<td valign="top">

Specify the original name of the file to be renamed.

Example: `new.txt`

</td>
</tr>
<tr>
<td valign="top">

*New Object Name*

</td>
<td valign="top">

Specify the updated name of the file to be renamed.

Example: `updated.txt`

</td>
</tr>
</table>

