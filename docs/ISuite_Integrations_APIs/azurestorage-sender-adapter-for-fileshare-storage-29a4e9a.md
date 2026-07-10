<!-- loio29a4e9a64fc7490a80211f08621ad435 -->

# AzureStorage Sender Adapter for Fileshare Storage

The AzureStorage sender adapter enables SAP Integration Suite to receive files from Azure Storage.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a sender channel and selected the *AzureStorage* sender adapter and the *Fileshare Storage* message protocol, you can configure the following attributes.

Select the *General* tab to access the following parameters.

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

Enter the name of the channel.

</td>
</tr>
<tr>
<td valign="top">

*Direction* 

</td>
<td valign="top">

Sender

</td>
</tr>
<tr>
<td valign="top">

*System* 

</td>
<td valign="top">

Sender

</td>
</tr>
<tr>
<td valign="top">

*Adapter Type* 

</td>
<td valign="top">

AzureStorage

</td>
</tr>
<tr>
<td valign="top">

*Transport Protocol* 

</td>
<td valign="top">

HTTPS

</td>
</tr>
<tr>
<td valign="top">

*Message Protocol* 

</td>
<td valign="top">

*Fileshare Storage*

Shows the message protocol selected when creating the channel.

</td>
</tr>
</table>

You can provide more information in the *Description* field.

Select the *Connection* tab and provide values in the fields as follows.

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

*Authentication* 

</td>
<td valign="top">

Select authentication option to use to connect to Azure Storage server. There are the following options:

-   *SAS Token*

-   *Shared Access Key*




</td>
</tr>
<tr>
<td valign="top">

*Token Alias*

\(Only if for *Authentication* the option *SAS Token* is selected\)

</td>
<td valign="top">

Alias name of token used to communicate with Azure Storage.

</td>
</tr>
<tr>
<td valign="top">

*Key Alias*

\(Only if for *Authentication* the option *Shared Access Key* is selected\)

</td>
<td valign="top">

Alias name of key used to communicate with Azure Storage.

</td>
</tr>
<tr>
<td valign="top">

*Timeout* 

</td>
<td valign="top">

Maximum waiting time, in milliseconds, to contact Azure Storage while establishing a connection or performing a read operation \(default value: 60000\).

Setting a timeout is mandatory for both token and key aliases.

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

*Storage Account Name* 

</td>
<td valign="top">

Enter name of the storage account.

> ### Note:  
> The storage account name has been predefined already in Azure Storage. If you enter a wrong name, an error message is shown.



</td>
</tr>
<tr>
<td valign="top">

*Share Name* 

</td>
<td valign="top">

Enter name of the share.

</td>
</tr>
<tr>
<td valign="top">

*Directory* 

</td>
<td valign="top">

Enter name of the file to be read. Blank field indicates all files in the specified directory are read.

</td>
</tr>
<tr>
<td valign="top">

*Body Size \(in MB\)* 

</td>
<td valign="top">

Enter maximum file size \(in MB\).

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing* 

</td>
<td valign="top">

Select the action to be performed after successful processing of the file:

-   *Keep File and Process Again*

    Keeps file in the storage and reprocesses it as specified by the scheduler. If you choose this option, the file is processed with every message processing run, even if it hasn't been changed.

-   *Keep File and Mark as Processed in Idempotent Repository*

    Prevents file from being consumed again within the configured duration. For that purpose, an idempotent database is activated with the configured persist duration.

    > ### Note:  
    > The idempotent repository contains information on files already been consumed from Azure Storage. It stores the file names in a database to synchronize between multiple worker nodes and to prevent the files from being read again when the runtime node is restarted. File name entries are deleted by default after 90 days.

-   *Delete File*

    File is deleted from Azure Storage after it has been processed successfully.

-   *Move File*

    File is moved to another directory/container. If you select this option, you need to specify the target directory/container. For *Download File* operation, this post-processing option requires an existing folder path where to move the file. If the given folder doesn't exist, post-processing operation fails and the file remains in the source folder.




</td>
</tr>
<tr>
<td valign="top">

*Persist Duration \(in Days\)*

\(Only if for *Post-Processing* the option *Keep File and Mark as Processed in Idempotent Repository* is selected\)

</td>
<td valign="top">

Enter the time \(in days\), for which file name is to be stored in idempotent repository to avoid processing again within the given duration \(default: 90 days\).

</td>
</tr>
<tr>
<td valign="top">

*Raise Exception on Post-Processing Failure*

Only if for *Post-Processing* one of the following options is selected:

-   *Delete File*

-   *Move File*

-   *Keep File and Mark as Processed in Idempotent Repository*




</td>
<td valign="top">

Select this option to raise error in the message processing log if post processing fails.

Using this option, if post-processing fails, the message gets *Failed* status. Otherwise, the message gets status *Successful*. In both cases, the post-processing operation status is stored in message property log.

-   If post-processing operation fails and *Move File* is selected, status is stored in property `SAP_AzureStorage_Move_Response`.

-   If post-processing operation fails and *Delete File* is selected, status is stored in property `SAP_Azurestorage_Delete_Response`.

-   If post-processing operation fails and *Keep File and Mark as Processed in Idempotent Repository* is selected, status is stored in property `SAP_Azurestorage_Keepfile_Response`.




</td>
</tr>
<tr>
<td valign="top">

*Archive Directory*

\(Only if for *Post-Processing* the option *Move File* is selected\)

</td>
<td valign="top">

File is moved to another directory. If you select this option, you need to specify the target directory.

</td>
</tr>
<tr>
<td valign="top">

*Key* 

</td>
<td valign="top">

Select a request parameter.

</td>
</tr>
<tr>
<td valign="top">

*Value* 

</td>
<td valign="top">

Specify the value of the argument. You can also enter`${header.headername}` or `${property.propertyname}` to dynamically read the value from the message exchange.

</td>
</tr>
</table>



Select the *Scheduler* tab and provide values in the fields as follows. The scheduler helps you to download the blobs on regular intervals as per the timer:

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

There are the following options:

-   *On Date*: Select the date of the scheduling day.

-   *On Time*: Set the time of scheduling.

-   *Every*: Set the polling interval for the Azure Storage sender adapter.

-   *Time Zone*: Set the time zone.




</td>
</tr>
<tr>
<td valign="top">

*Schedule to Recur* 

</td>
<td valign="top">

There are the following options:

-   *Daily*: Select if scheduling needs to recur daily.

-   *Weekly*: Select if scheduling needs to recur weekly.

-   *Monthly*: Select if scheduling needs to recur monthly.

-   *On Time*: Set the time of scheduling.

-   *Every*: Polling interval for the Azure Storage sender adapter.

-   *Time Zone*: Set the time zone.




</td>
</tr>
</table>

