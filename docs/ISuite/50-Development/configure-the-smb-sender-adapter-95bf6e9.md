<!-- loio95bf6e9d2f084543a4431e26c075ab76 -->

# Configure the SMB Sender Adapter

The SMB \(Server Message Block\) sender adapter connects SAP Integration Suite to a remote share drive using TCP \(Transmission Control Protocol\) to read files from the server.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio95bf6e9d2f084543a4431e26c075ab76__section_knx_1cl_tcc"/>

## How the SMB Sender Adapter Works

If you have configured a sender SMB adapter, an application \(or the user of an application\) can access files in the following manner:

The SAP Integration Suite tenant sends a read operation request to an SMB share drive server, and the data flow is in the opposite direction, from the SMB server to the tenant.

Once you have created a sender channel and selected the SMB sender adapter, you can configure the following attributes.

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

Specify the hostname or IP address of the SMB Server.

Example:

-   `51.21.73.311:445`
-   `fileserver:445`



</td>
</tr>
<tr>
<td valign="top">

*Domain*

</td>
<td valign="top">

If required, specify the domain used for authentication.

> ### Note:  
> Ensure that you provide the domain name here. Avoid mentioning domain as part of the User Credential.



</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

Select the proxy type:

-   *Internet*
-   *On-Premise*



</td>
</tr>
<tr>
<td valign="top">

*Location ID* \(Only available when *Proxy Type* is set to *On-Premise*\).

</td>
<td valign="top">

Specify the Location ID from Cloud Connector.

To learn more about Cloud Connector Connectivity, see [Configure Access Control](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-access-control-tcp).

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

Default: `Auto`

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

Select the authentication type for connecting to the SMB server. Currently only *Basic Authentication* is supported.

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

Enable SMB Signing between the client and the server..

</td>
</tr>
<tr>
<td valign="top">

*Maximum Reconnect Attempts*

</td>
<td valign="top">

Specify the maximum number of retries permissible for reconnection to the SMB server before message processing starts.

Default: 3

</td>
</tr>
</table>

**Processing**


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

*Operation*

</td>
<td valign="top">

Specify the operation to be performed.

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

Specify the filename to be read.

Default: `*`

Example: `readfile.txt`

</td>
</tr>
<tr>
<td valign="top">

*Empty File Handling*

</td>
<td valign="top">

Select option to handle empty files:

-   *Ignore*: Completely skip empty files without any processing.
-   *Proceed with Empty File*: Process Empty File.



</td>
</tr>
<tr>
<td valign="top">

*Read Lock Strategy*

</td>
<td valign="top">

Select the read lock strategy for polling:

-   *Content Change*: Detect modifications to the file for a duration specified by *Content Change Duration field.* 
-   *None*: No read lock strategy applicable.



</td>
</tr>
<tr>
<td valign="top">

*Content Change Duration \(in secs\)*

\(Only available if *Read Lock Strategy* is set to *Content Change*\)

</td>
<td valign="top">

Specify the minimum time \(in seconds\) during which the file must remain unchanged before it can be processed.

</td>
</tr>
<tr>
<td valign="top">

*Post Processing*

</td>
<td valign="top">

Specify the post processing options for the file after read operation is finished.

-   *Delete File* removes the file after read operation completion.
-   *Keep File and Process Again* retains the file after read operation completion.
-   *Move File* copies the file to an archive directory \(specified by *Archive Folder*\) after read operation completion.



</td>
</tr>
<tr>
<td valign="top">

*Archive Append Timestamp*

\(Only available if parameter *Post Processing* has option *Move File* selected\).

</td>
<td valign="top">

Enable to append timestamp to the filename.

Example: If the file name is `myfile.xml`, \(for example, Mar 2, 1999, 09:07:05\) this option generates `myfile762599225000.txt`

</td>
</tr>
<tr>
<td valign="top">

*Archive Folder*

\(Only available if parameter *Post Processing* has option *Move File* selected\).

</td>
<td valign="top">

Specify the target directory for the file to be archived.

Example: `folder\archive`

</td>
</tr>
<tr>
<td valign="top">

*Execute Post-Processing when Message Successfully Processed*

</td>
<td valign="top">

Enable to perform post processing actions after successful execution of Iflow.

</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check*

</td>
<td valign="top">

Enable to avoid same file being read twice within the expiration period.

</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check Expiration Period \(in secs\)*

\(Only available if parameter *Duplicate Check* is enabled\).

</td>
<td valign="top">

Specify the value for Duplicate Check Expiration Period \(in secs\).

</td>
</tr>
<tr>
<td valign="top">

*Max. Messages per Poll*

</td>
<td valign="top">

Specify the maximum number of messages to be polled.

</td>
</tr>
<tr>
<td valign="top">

*Maximum File Size \(in MB\)*

</td>
<td valign="top">

Specify maximum size for the file to be picked up.

Default: `40`

</td>
</tr>
</table>

**Scheduler**


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

*Schedule on Day*

</td>
<td valign="top">

Specify the frequency of file read on a specific date.

-   *On Date*: Specify the date on which you want the message processing to be triggered.
-   *On Time*: Specify the time at which you want the message processing to be triggered.
-   *Every*: Specify the time period \(for example, every hour\) at which you want the message processing to be triggered.
-   *Time Zone*: Select the time zone that you want the scheduler to use as a reference for the date and time settings.



</td>
</tr>
<tr>
<td valign="top">

*Schedule to Recur*

</td>
<td valign="top">

-   *Daily*: Select the time or interval and time zone for the schedule to recur.

-   *Weekly*: Select the checkboxes to indicate the days of the week on which the message processing should be triggered. Also, specify the time or interval and time zone for the schedule to recur.
-   *Monthly*:Select the day of the month on which the message processing should be triggered. Also, indicate the time or interval and time zone for the schedule to recur.



</td>
</tr>
</table>

