<!-- loioc25507427c5449e589d2623e15e71aea -->

# Configure the NFS Sender Adapter

NFS Sender Adapter provides the ability to read files from the NFS Server.

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loioc25507427c5449e589d2623e15e71aea__secction_3j4_rdc"/>

## Configure the NFS Sender Adapter

Once you have created a sender channel and selected the NFS Sender Adapter, you can configure the parameters as shown below:

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

Specify the hostname or IP address of the NFS server.

Example: `12.123.12.123`

> ### Note:  
> Ensure that NFS sharing is enabled for the drive.



</td>
</tr>
<tr>
<td valign="top">

*Drive Name*

</td>
<td valign="top">

Specify the name of the drive.

Example: `NFSShareDrive`

</td>
</tr>
<tr>
<td valign="top">

*User ID \(UID\)*

</td>
<td valign="top">

Specify the Secure Parameter alias that stores the User ID associated with the NFS client.

> ### Note:  
> File ownership and permissions on the NFS server depend on the UID and GID mapping of the user performing the operation.



</td>
</tr>
<tr>
<td valign="top">

*Group ID \(GID\)*

</td>
<td valign="top">

Specify the Secure Parameter alias that stores the Group ID associated with the NFS client.

> ### Note:  
> File ownership and permissions on the NFS server depend on the UID and GID mapping of the user performing the operation



</td>
</tr>
<tr>
<td valign="top">

*Maximum Connection Attempts*

</td>
<td valign="top">

Specify the maximum number of connection attempts to the NFS server. The default is 3 attempts.

Example: `5`

</td>
</tr>
<tr>
<td valign="top">

*Reconnect Delay \(in ms\)*

</td>
<td valign="top">

Specify the waiting time in milliseconds before attempting to reconnect to the NFS server. The default is `1000`.

Example: `300000`

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

*Directory*

</td>
<td valign="top">

Specify the directory to read the files. Use `/` to specify the root folder.

Example: `/Records/Day1`

> ### Note:  
> The camel expressions like `${date:now:yyyyMMdd}` are supported.



</td>
</tr>
<tr>
<td valign="top">

*File Name*

</td>
<td valign="top">

Specify the name of the file to be read. You can also specify a pattern using regex. If left blank, all files in the specified directory will be read.

Example: `*_2026.txt`

> ### Note:  
> The camel expressions like `${date:now:yyyyMMdd}` are supported.



</td>
</tr>
<tr>
<td valign="top">

*Include Subdirectories*

</td>
<td valign="top">

Enable to search for files in the directory and all its subdirectories.

> ### Note:  
> The system will scan all nested folders, ensuring that files within subdirectories are included in the operation.



</td>
</tr>
<tr>
<td valign="top">

*Maximum Messages Per Poll*

</td>
<td valign="top">

Specify the maximum number of messages to gather for each poll.

</td>
</tr>
<tr>
<td valign="top">

*Maximum File Size \(in MB\)*

</td>
<td valign="top">

Specify the maximum file size in MB that can be read.

> ### Note:  
> -   The acceptable range is between 1 and 500.
> -   NFS Sender reads a file based on the configuration dictated by the NFS server. This sometimes means that a file would take a longer time to be completely read and available for processing.



</td>
</tr>
<tr>
<td valign="top">

*Duplicate Check*

</td>
<td valign="top">

Enable to prevent the reprocessing of files that were already handled within the time period defined by the *Duplicate Expiry* field. The configured duration is used to identify and skip duplicates.

</td>
</tr>
<tr>
<td valign="top">

*Duplicate Expiry \(in ms\)*

\(Only available when *Duplicate Check* is enabled.\)

</td>
<td valign="top">

Specify the expiry time in milliseconds while handling the duplicate check.

The default value is `300000`.

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing*

</td>
<td valign="top">

Select the action to be performed after successful iFlow processing:

-   *Move File*: Transfers the processed file to a target folder.
-   *Delete File*: Removes the files from the source.
-   *Keep File and Process Again*: Retains file in place and process is repeated again.

> ### Note:  
> The Post-Processing actions are performed only when the iFlow execution is successfully completed.



</td>
</tr>
<tr>
<td valign="top">

*Archive Directory*

\(Only available when *Post-Processing* is selected as *Move File*\)

</td>
<td valign="top">

Specify the directory to archive a file.

> ### Note:  
> The camel expressions like `${date:now:yyyyMMdd}` are supported.



</td>
</tr>
<tr>
<td valign="top">

*Archive File Name*

\(Only available when *Post-Processing* is selected as *Move File*\)

</td>
<td valign="top">

Specify the name for the archived file.

> ### Note:  
> The camel expressions like `${date:now:yyyyMMdd}` are supported.



</td>
</tr>
<tr>
<td valign="top">

*Append Timestamp*

\(Only available when *Post-Processing* is selected as *Move File*\)

</td>
<td valign="top">

Enable to append the timestamp to the file name. The format for Timestamp is `yyyyMMdd-HHmmss-SSS.`

> ### Note:  
> For custom formats, camel expressions can be used in the *Archive File Name* field.



</td>
</tr>
</table>

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

On Time

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
<td valign="top" rowspan="4">

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
<tr>
<td valign="top">

Time Zone

</td>
<td valign="top">

Select the time zone that you want the scheduler to use as a reference for the date and time settings.

</td>
</tr>
</table>

