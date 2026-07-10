<!-- loio07241361eb154e999a16b5abe49c6d5c -->

# Configure the Microsoft OneDrive Sender Adapter

The Microsoft OneDrive sender adapter connects a SAP Integration Suite tenant to a remote system using HTTP protocol.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you've created a sender channel and selected the **Microsoft OneDrive** sender adapter, you can configure the following attributes.

Select the *General* tab and provide values in the fields as follows:

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

Enter the name of the Microsoft OneDrive Storage adapter.

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type* 

</td>
<td valign="top">

Microsoft OneDrive

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

Select the *Connection* tab and provide values in the fields as follows.

**Connection**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Connection

</th>
</tr>
<tr>
<td valign="top">

*Drive ID* 

</td>
<td valign="top">

1.  Enter the Drive ID of the Microsoft OneDrive account, for example, `b!W7L40Gm3jEyioP6SoHB_EIw5wO4ap1lKol0ZgNFVlMsTRC_J6jpzSbi19fJMiM7I`.

2.  Get Drive ID information for the account using below Microsoft API `GET https://graph.microsoft.com/v1.0/users/{idOrUserPrincipalName}/drive` 




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

Enter the alias name of the deployed user credentials artifact.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)* 

</td>
<td valign="top">

Enter the maximum waiting time, in milliseconds, to contact the Microsoft OneDrive server while establishing a connection or performing a read operation. If you leave it blank, the timeout value is set to 60000 by default.

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

*Directory* 

</td>
<td valign="top">

Enter the directory path of the source file, for example,*/mydirectory/mysubdirectory*.

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

If the incoming file size is greater than the configured value, then the adapter doesn't execute the integration scenario and the file is ignored for post processing.

</td>
</tr>
<tr>
<td valign="top">

*Post Processing* 

</td>
<td valign="top">

Post-processing operations allow you to specify how to handle the files after processing. The available options are:

-   *Delete File*: The adapter deletes the file from the Microsoft OneDrive server after successfully processing it.

-   *Keep File and Mark as Processed in Idempotent Repository*: Prevents a file from being consumed again within the configured duration. For that purpose, an idempotent database is activated with the configured persist duration.

    The idempotent repository contains information about files already been consumed from the Microsoft OneDrive server. Being stored in the idempotent repository, a file can be identified by the file name. When SAP Integration Suite tries to process the file, the system detects if the file was already consumed \(based on its idempotent repository entry\). This way, the adapter prevents the file consumption second time from the Microsoft OneDrive server.

    Select this option for Microsoft OneDrive servers that don't allow deleting or moving files, but the files are to be read only once.

    > ### Note:  
    > When you choose this option, the system only considers the file name to decide whether it's the same file or not. Other attributes like, for example – file size, timestamp, hash value are ignored.

-   *Keep File and Process Again*: Keeps a file in the storage and reprocesses it as specified by the scheduler. If you choose this option, the adapter processes the file with every message processing run, even if it hasn't been changed.

-   *Move File*: Moves the file to another directory. If you select this option, you must specify a target directory.


> ### Note:  
> Only successfully processed messages can be post-processed. If message processing fails, the Post Processing settings aren't effective.



</td>
</tr>
<tr>
<td valign="top">

*Throw Exception on Post-Processing Failure* 

</td>
<td valign="top">

If you enable this option, upon post-processing operation failure, the adapter throws exception and logs the failure information in the message processing logs.

</td>
</tr>
<tr>
<td valign="top">

*Persist Duration \(in days\)*

Only if you select *Post Processing* as *Keep File and Mark as Processed in Idempotent Repository*.

</td>
<td valign="top">

Specify the number of days for which the file should be in the idempotent repository.

</td>
</tr>
<tr>
<td valign="top">

*Archive Directory*

Only if you select *Post Processing* as *Move File*.

</td>
<td valign="top">

Specify the directory and a file name to use when moving the file into an archive directory after processing. It must be in the following format: *<archive-directory/folder-name/filename\>*.

</td>
</tr>
<tr>
<td valign="top">

*Response Format*

</td>
<td valign="top">

Specify the response for the operation. Following formats are valid:

-   None
-   PDF
-   HTML
-   JPG
-   GLB

If any of the options is not selected, the default response format is set to *None*.

</td>
</tr>
</table>

Select the *Scheduler* tab and provide values in the fields as follows.

**Schedule**


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

*Select if you want the message processing to be triggered on a specific date and time.*

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

