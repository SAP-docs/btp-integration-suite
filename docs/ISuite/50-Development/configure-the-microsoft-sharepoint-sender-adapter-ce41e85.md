<!-- loioce41e85abcc140dca0b6f638ff5d0cd4 -->

# Configure the Microsoft SharePoint Sender Adapter

The Microsoft SharePoint sender adapter connects an SAP Integration Suite tenant to a remote system using the HTTP/HTTPS protocol to read files from the system.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you've created a sender channel and selected the **Microsoft SharePoint** sender adapter, you can configure the following attributes.

Select the *General* tab to access the parameters described in the following table.

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

Enter the name of the Microsoft SharePoint Storage adapter.

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type* 

</td>
<td valign="top">

Microsoft SharePoint

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol* 

</td>
<td valign="top">

HTTP/HTTPS

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol* 

</td>
<td valign="top">

REST

</td>
</tr>
<tr>
<td valign="top">

*Description* 

</td>
<td valign="top">

Add useful information to describe the adapter.

</td>
</tr>
</table>

Select the *Connection* tab and provide values in the fields as described in the following table.

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

*Site Host Name* 

</td>
<td valign="top">

Enter the hostname of the Microsoft SharePoint server, for example, `sap-my.sharepoint.com/`.

</td>
</tr>
<tr>
<td valign="top">

*Server Relative Path* 

</td>
<td valign="top">

Enter the path for site as ‘site type/site name’, for example, `/teams/MicrosoftSharePointAdapter`.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type* 

</td>
<td valign="top">

Select the authentication type. Supported types are:

-   *OAuth2 Authorization Code*

-   *OAuth2 Client Credentials*




</td>
</tr>
<tr>
<td valign="top">

*Credential Name* 

</td>
<td valign="top">

Enter the alias name of the deployed User Credentials artifact.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type* 

</td>
<td valign="top">

Select *Internet* as proxy type to connect to the SharePoint Cloud server.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)* 

</td>
<td valign="top">

Enter the maximum waiting time, in milliseconds, to contact the Microsoft SharePoint server while establishing a connection or performing a read operation. If you leave it blank, the timeout value is set to 60000 by default.

</td>
</tr>
</table>

Select the *Processing* tab and provide values in the fields as described in the following table.

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

Enter the directory path of the source file, for example, */mydirectory/mysubdirectory*.

</td>
</tr>
<tr>
<td valign="top">

*File Name* 

</td>
<td valign="top">

Enter name of the source file to be downloaded. If you leave the field blank, all the files in the specified directory are read.

> ### Note:  
> -   The adapter supports expressions such as `ab*, a.*, *a*, *a, ?b,` and so on.
> 
> -   The character \* replaces any number of arbitrary characters.
> 
>     If you specify `file*.txt` as the file name, the following files are polled by the adapter: file.txt, file1.txt, file2.txt, file.txt, file1234.txt, and so on.
> 
> -   The character ? replaces exactly one arbitrary character.
> 
>     If you specify `file?.txt` as the file name, the following files are polled by the adapter: file1.txt, file2.txt, and so on; but not the following files: file.txt or file1234.txt.

> ### Note:  
> When you use an expression to include files from subdirectories, the adapter evaluates the relative path from the root directory of the user and the actual file name.



</td>
</tr>
<tr>
<td valign="top">

*Body Size \(in MB\)* 

</td>
<td valign="top">

Enter the maximum body size in MB. 40 MB is the default value. Only positive numbers are allowed.

If the incoming file size is greater than the configured value, then the adapter doesn't execute your integration scenario and the file is ignored for post processing.

</td>
</tr>
<tr>
<td valign="top">

*Post Processing* 

</td>
<td valign="top">

Post-processing operations allow you to specify how to handle the files after processing. The available options are:

-   *Delete File*: The adapter deletes the file from the Microsoft SharePoint server after successfully processing it.

-   *Keep File and Mark as Processed in Idempotent Repository*: Prevents a file from being consumed again within the configured duration. For that purpose, an idempotent database is activated with the configured persist duration.

    The idempotent repository contains information about files already been consumed from the Microsoft SharePoint server. Being stored in the idempotent repository, a file can be identified by the file name. When SAP Integration Suite tries to process the file, the system detects if the file was already consumed \(based on its idempotent repository entry\). This way, the adapter prevents the file it from being consumed a second time from the Microsoft SharePoint server.

    Select this option for Microsoft SharePoint servers that don't allow deleting or moving files, but the files are to be read only once.

    When you choose this option, the system only considers the file name to decide whether it's the same file or not. Other attributes like, for example – file size, timestamp, hash value are ignored.

-   *Keep File and Process Again*: Keeps a file in the storage and reprocesses it as specified by the scheduler. If you choose this option, the adapter processes the file with every message processing run, even if it hasn't been changed.

-   *Move File*: Moves the file to another directory. If you select this option, you must specify a target directory.


Only successfully processed messages can be post-processed. If message processing fails, the Post Processing settings aren't effective.

</td>
</tr>
<tr>
<td valign="top">

*Raise Exception on Post-Processing Failure* 

</td>
<td valign="top">

If you enable this check box, upon post-processing operation failure, the adapter throws exception and logs the failure information in the message processing logs.

</td>
</tr>
<tr>
<td valign="top">

*Persist Duration \(in days\)*

Only if for *Post Processing* you select *Keep File and Mark as Processed in Idempotent Repository*.

</td>
<td valign="top">

Enter the number of days for which the file must be stored in idempotent repository for duplicate check.

</td>
</tr>
<tr>
<td valign="top">

*Archive Directory*

Only if for *Post Processing* you select *Move File*.

</td>
<td valign="top">

Specify the directory and a file name to use when moving the file into an archive directory after processing. The format must be in the following format: *<archive-directory/folder-name/filename\>*.

</td>
</tr>
</table>

Select the *Scheduler* tab and provide values in the fields as specified in the following table.


<table>
<tr>
<th valign="top">

Option

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

Select if you want the message processing to be triggered on a specific date and time.

The fields *On Date* and *Time Zone* are mandatory. Choose between *On Time* and *Every* based on your use case.

</td>
<td valign="top">

On Date

</td>
<td valign="top">

Select the date on which you want the message processing to be triggered.

</td>
</tr>
<tr>
<td valign="top">

On Time

</td>
<td valign="top">

Select the time at which you want the message processing to be triggered.

</td>
</tr>
<tr>
<td valign="top">

Every

</td>
<td valign="top">

Select this option if you want to trigger message processing repeatedly in a specific time interval.

</td>
</tr>
<tr>
<td valign="top">

Time Zone

</td>
<td valign="top">

The time zone that you want to be used as reference for the configured date and time.

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

*Schedule to Recur*

Select if you want to repeatedly trigger message processing according to a specific schedule.

The fields *Schedule to Recur* and *Time Zone* are mandatory. Choose between *On Time* and *Every* based on your use case.

</td>
<td valign="top">

Schedule to Recur

</td>
<td valign="top">

From the list of recurrence pattern, choose *Daily*, *Weekly*, or *Monthly*.

Accordingly, if you choose

-   *Weekly*, choose the days of the week.

-   *Monthly*, choose the day of the month from the list.



</td>
</tr>
<tr>
<td valign="top">

On Time

</td>
<td valign="top">

Select the time at which you want the message processing to be triggered.

</td>
</tr>
<tr>
<td valign="top">

Every

</td>
<td valign="top">

Select this option if you want to trigger message processing repeatedly in a specific time interval.

</td>
</tr>
<tr>
<td valign="top">

Time Zone

</td>
<td valign="top">

The time zone that you want to be used as reference for the configured date and time.

</td>
</tr>
</table>

