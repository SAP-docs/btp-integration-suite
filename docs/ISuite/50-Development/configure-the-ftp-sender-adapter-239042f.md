<!-- loio239042f2328a406a8647b93b937921a3 -->

# Configure the FTP Sender Adapter

The FTP \(File Transfer Protocol\) sender adapter connects SAP Integration Suite to a remote system using TCP \(Transmission Control Protocol\) to receive files from the system.

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



> ### Note:  
> Consider the following when operating with the FTP sender adapter:
> 
> -   This adapter does not support connections to SFTP servers. See: [Configure the SFTP Sender Adapter](configure-the-sftp-sender-adapter-2de9ee5.md).

> ### Note:  
> Consider the following when using the FTP sender adapter:
> 
> -   Only the passive mode is supported for the FTP sender adapter.
> 
> -   The FTP adapter does not support TLS session re-use.
> 
> -   The transfer mode is *BINARY*.
> 
> -   You can establish a connection to your on-premise system by using Cloud Connector: [SAP Connectivity Service](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e933fd930039402c907d5afaa75eb0e1.html).

Once you have created a sender channel and selected the FTP sender adapter, you can configure the following attributes. Select the *General* tab and provide values in the fields as follows.

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

Select the *Source* tab and provide values in the fields as follows.

**Source**


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

*Directory*

</td>
<td valign="top">

Use the relative path to read the file from a directory.

Example:`parentdirectory/childdirectory`

</td>
</tr>
<tr>
<td valign="top">

*File Name*

</td>
<td valign="top">

Name of the file to be read.

> ### Note:  
> If you do not enter a file name and the parameter remains blank, all the files in the specified directory are read.

> ### Note:  
> **Usage of file name pattern:**
> 
> Expressions, such as `ab*`, `a.*`, `*a*`, `?b`, and so on, are supported.
> 
> The expression `*` replaces no character or an arbitrary number of characters.
> 
> The expression `?` replaces exactly one arbitrary character.
> 
> Examples:
> 
> If you specify `file*.txt` as the *File Name*, the following files are polled by the adapter: `file1.txt`, `file2.txt`, as well as `file.txt`Example: and `file1234.txt`, and so on.
> 
> If you specify `file?.txt` as the *File Name*, the following files are polled by the adapter: `file1.txt`, `file2.txt`, and so on, but **not** the files `file.txt` or `file1234.txt`.
> 
> Although you can configure this feature, it is not supported when using the corresponding integration content with the SAP Process Orchestration \(SAP PO\) runtime in releases lower than SAP PO 7.5 SP5.

> ### Caution:  
> Files with file names longer than 100 characters will be processed with the following limitations:
> 
> -   If two files with names longer than 100 characters are available for processing, only one of these files is processed at a time. This means that both files are processed, but not in parallel. This is also the case if two runtime nodes/workers are available. If the node/worker fails multiple times while processing a file with a file name longer than 100 characters, none of the files sharing the first 100 characters with that file can be executed without manual intervention from the administrator.
> 
> -   The option *Keep File and Mark as Processed in Idempotent Repository* \(for sender channels under *Processing*\) will not work for these files.



</td>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Host name or IP address of the FTP server and an optional port, for example, `wdfd00213123:21`.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

The type of proxy that you are using to connect to the target system.

-   Select *Internet* if you are connecting directly to the FTP server.

-   Select *On-Premise* if you are connecting to an on-premise system.

    See [Using SAP Cloud Connector with Cloud Integration Adapters](../40-RemoteSystems/using-sap-cloud-connector-with-cloud-integration-adapters-65a60e7.md).




</td>
</tr>
<tr>
<td valign="top">

*Location ID*

\(only if *On-Premise* is selected for *Proxy Type*\)

</td>
<td valign="top">

To connect to an SAP Cloud Connector instance associated with your account, enter the location ID that you defined for this instance in the destination configuration of SAP BTP cockpit.

</td>
</tr>
<tr>
<td valign="top">

*Encryption*

</td>
<td valign="top">

Specify the transport encryption. You can choose between the following options:

-   *Explicit FTPS*: After an initial connection, the client with send `AUTH TLS` command to the server and initial the handshake this way. Afterwards, the communication will be encrypted. Unless you specified a port in the address, the default port will be 21.

-   *Implicit FTPS*: The client will connect to the server with an TLS connection. This means the client starts the handshake at the beginning of the communication. Unless you specified a port in the address, the default port is 990.

-   *Plain FTP - no encryption*: No encryption will be applied, for productive use \(not recommended\). Unless you specified a port in the address, the default port is 21.




</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

</td>
<td valign="top">

Name of the *User Credentials* artifact that contains the user name and password.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)*

</td>
<td valign="top">

Maximum time \(in milliseconds\) to wait for the FTP server to be contacted while establishing connection or performing a read operation.

Default value: `10000`

</td>
</tr>
<tr>
<td valign="top">

*Maximum Reconnect Attempts*

</td>
<td valign="top">

Maximum number of attempts allowed to reconnect to the FTP server.

Default value: `3`

Enter `0` to disable this behavior.

</td>
</tr>
<tr>
<td valign="top">

*Reconnect Delay \(in ms\)*

</td>
<td valign="top">

Time \(in milliseconds\) the system waits before attempting to reconnect to the FTP server.

Default Value: `1000`

</td>
</tr>
<tr>
<td valign="top">

*Automatically Disconnect*

</td>
<td valign="top">

Disconnect from the FTP server after each message processing.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as follows.

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

*Read Lock Strategy*

</td>
<td valign="top">

Prevents files that are in the process of being written from being read from the FTP server. The endpoint waits until it has an exclusive read lock on a file before reading it.

Select one of the following options based on the capabilities of the FTP server:

-   *Content Change*: Monitors changes in the file length/modification timestamp to determine if the write operation on the file is complete and the file is ready to be read. If you have selected this option, the system waits for at least one second until there are no more file changes. Therefore, if you select this option, files cannot be read as quickly as with the other two options.

-   *Done File Expected*: Uses a specific file to signal that the file to be processed is ready for consumption.

    If you have selected this option, enter the name of the done file. The done file signals that the file to be processed is ready for consumption. This file must be in the same folder as the file to be processed. Placeholders are allowed.

    Default:

    `${file:name}.done`

-   *None* \(default\): Does not use a read lock, which means that the endpoint can immediately read the file. *None* is the simplest option if the FTP server guarantees that a file only becomes visible on the server once the process of writing it to the server has been finished.

-   *Rename*: Renames the file on the FTP server before reading it.




</td>
</tr>
<tr>
<td valign="top">

*Sorting*

</td>
<td valign="top">

Select the type of sorting to use to poll files from the FTP server:

Choose between the following options:

-   *None* \(default\): The sorting is specified by the TFP server.

-   *File Name*: Files are polled sorted by file name.

-   *File Size*: Files are polled sorted by file size.

-   *Time Stamp*: Files are polled sorted by the modification time stamp of the file.




</td>
</tr>
<tr>
<td valign="top">

*Sorting Order*

\(only if *File Name*, *File Size*, or *File Stamp* is selected for *Sorting*\)

</td>
<td valign="top">

Choose from the following options:

-   *Ascending*

-   *Descending*




</td>
</tr>
<tr>
<td valign="top">

*Max. Messages per Poll*

</td>
<td valign="top">

Maximum number of messages to gather in each poll. Enter any value between `1` and `500`. The default is set to `20`.

Consider how long it will take to process this number of messages, and make sure that you set a higher value for *Lock Timeout \(in min\)*. The messages are picked up sequentially.

> ### Note:  
> The adapter processes the complete list of messages specified by this parameter before the subsequent poll \(according to the settings under *Scheduler*\) starts.

> ### Note:  
> If you are using the sender FTP adapter in combination with an Aggregator step and you expect a high message load, consider the following recommendation:
> 
> Set the value for *Max. Messages per Poll* to a small number larger than `0` \(for example, `20`\). This ensures proper logging of the message processing status at runtime.



</td>
</tr>
<tr>
<td valign="top">

*Lock Timeout \(in min.\)*

</td>
<td valign="top">

Specify how long to wait before trying to process the file again in the event of a Cloud Integration outage. If it takes a very long time to process the scenario, you may need to increase the timeout to avoid parallel processing of the same file. This value should be higher than the processing time required for the number of messages specified by *Max. Messages per Poll* in the *Processing* tab. The default is set to 15 minutes.

</td>
</tr>
<tr>
<td valign="top">

*Change Directories Stepwise*

</td>
<td valign="top">

Select this option to change directory levels step by step.

</td>
</tr>
<tr>
<td valign="top">

*Include Subdirectories*

</td>
<td valign="top">

Select this option to look for files in all subdirectories of the directory.

</td>
</tr>
<tr>
<td valign="top">

*Flatten File Names* 

\(only if *Include Subdirectories* is selected\)

</td>
<td valign="top">

Flatten the file path by removing the directory levels so that only the file names are considered.

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing*

</td>
<td valign="top">

Allows you to specify how files are to be handled after processing.

> ### Note:  
> Note that only successfully processed messages can be post-processed. If message processing fails, the *Post-Processing* settings are not effective.

You can select one of the following options from the dropdown list:

-   *Delete File* \(default\): The file is deleted after it has been read.

    If you have also selected *Done File Expected* as *Read Lock Strategy*, the file to be processed as well as the done file is deleted.

-   *Keep File and Mark as Processed in Idempotent Repository*: Prevents a file from being consumed twice. For that purpose, an idempotent repository is activated.

    The idempotent repository contains information about files already been consumed from the SFTP server. Being stored in the idempotent repository, a file can be identified by the file name. When Cloud Integration tries to process the file, the system can detect if the file has already been consumed \(based on its idempotent repository entry\) and that way can prevent it from being consumed a second time from the FTP server.

    Select this option for FTP servers that do not allow deletion or moving of files, but the files are to be read only once.

    Note that when you choose this option, the system only takes into account the file name to decide whether it is the same file or not. Attributes such like file size, timestamp, hash value, for example, are ignored.

    If you have also selected *Done File Expected* as *Read Lock Strategy*, an entry will be created in the idempotent repository; the done file will not be deleted.

-   *Keep File and Process Again*: The file is kept on the FTP server and file processing is repeated. You can use this option for testing purposes, for example.

    If you choose this option, the file is processed with every message processing run, even in case it has not be changed.

-   *Move File*: The file is moved to another directory.

    If you select this option, you need to specify the target directory.

    Make sure that you specify a relative file path for the target directory. Note that the specified file path is defined relative to the directory specified with the *Directory* parameter.

    > ### Note:  
    > If you specify an absolute file path, it may occur that the file cannot be stored correctly at runtime.

    You can also specify the target directory dynamically, for example, using the timestamp of the message. The following example uses backup folders with timestamps and replaces the file extension with `bak: backup/${date:now:yyyyMMdd}/${file:name.noext}.bak`

    If you have also selected *Done File Expected* as *Read Lock Strategy*, only the file to be processed is moved and the done file will be deleted.




</td>
</tr>
<tr>
<td valign="top">

*Idempotent Repository*

\(only if *Keep File and Mark as Processed in Idempotent Repository* is selected for *Post-Processing*\)

</td>
<td valign="top">

You can select one of the following idempotent repository options:

-   *Database* \(default\): Stores the file names in a database to synchronize between multiple worker nodes and to prevent the files from being read again when the runtime node is restarted. File name entries are deleted by default after 90 days.

    > ### Note:  
    > The idempotent repository uses the username, host name, and file name as key values to identify files uniquely across integration flows of a tenant.

-   *In Memory*: Keeps the file names in the memory. Files are read again from the FTP server when the runtime node is restarted. It is not recommended to use the *In Memory* option if multiple runtime nodes are used. In this case the other nodes would pick the file and process it because the memory is specific to the runtime node.




</td>
</tr>
<tr>
<td valign="top">

*Archive Directory*

\(only if *Move File* is selected for *Post-Processing*\)

</td>
<td valign="top">

Specifies the target directory where to move the file.

</td>
</tr>
</table>

Select the *Scheduler* tab and provide values in the fields as follows.

> ### Caution:  
> How you specify the *Scheduler* settings depends on the constraints and requirements of your integration scenario. However, make sure to use the *Scheduler* parameters advisedly: Specify the scheduler settings in such a way that messages are not polled with too high frequency. Use intervals below 1 minute only if really required. Otherwise, there’s the risk to overload the FTP server.

**Scheduler**


<table>
<tr>
<th valign="top">

Scheduler Option

</th>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="4">

*Schedule on Day* 

</td>
<td valign="top">

On Date

</td>
<td valign="top">

Specify the date on which you want the operation to be executed.

</td>
</tr>
<tr>
<td valign="top">

At Time

</td>
<td valign="top">

Specify the time at which you want the operation to be executed.

</td>
</tr>
<tr>
<td valign="top">

Every

</td>
<td valign="top">

Specify a time period \(for example, every hour\) in a dedicated time window.

</td>
</tr>
<tr>
<td valign="top">

Time Zone

</td>
<td valign="top">

Select the time zone that you want the scheduler to use as a reference for the date and time settings.

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

*Schedule to Recur* 

</td>
<td valign="top">

Daily

</td>
<td valign="top">

Select the time or interval and time zone for the schedule to recur.

</td>
</tr>
<tr>
<td valign="top">

Weekly

</td>
<td valign="top">

Select the checkboxes to indicate the days of the week on which the operation has to be executed. Also, specify the time or interval for the schedule to recur.

</td>
</tr>
<tr>
<td valign="top">

Monthly

</td>
<td valign="top">

Select the day of the month on which the operation has to be executed. Also indicate the time or the interval for the schedule to recur.

</td>
</tr>
</table>

