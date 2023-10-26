<!-- loiode619914e2a24c53a1253d90b79b814f -->

# Configure the Dropbox Sender Adapter

The Dropbox sender adapter enables SAP Integration Suite to receive files from the Dropbox storage.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> The Download archive file will be a part of sender Dropbox adapter only. These files aren't part of the Dropbox receiver adapter.

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a sender channel and selected the Dropbox sender adapter, you can configure the following attributes.

Select the *General* tab and provide values in the fields as follows.

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

Enter the name of the Dropbox channel.

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

Description

</th>
</tr>
<tr>
<td valign="top">

*OAuth Credential Name* 

</td>
<td valign="top">

Name of the credential artifact deployed on the tenant and used to connect to Dropbox account.

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(in ms\)* 

</td>
<td valign="top">

Maximum waiting time \(in milliseconds\) to contact the Dropbox server while establishing a connection or performing a read operation.

Default value: `300000`

SAP Cloud Integration is connected to Dropbox account trying to perform the operation for the stipulated time before throwing an error.

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

*Operation* 

</td>
<td valign="top">

Select one of the following options depending on the operation to be performed in the Dropbox account.

-   *Download Archive File* \(Default\)

    Download a folder from the user's Dropbox account as a zip file.

    The folder must be less than 20 GB in size and any single file within must be less than 4 GB in size. The resulting zip file must contain less than 10,000 files and folder entries in total, including the top-level folder. The input can't be a single file.

-   *Download File*

    Download a file from a Dropbox account. It is also supported to download files using wildcards.




</td>
</tr>
<tr>
<td valign="top">

*Folder Path* \(only if *Download Archive File* is selected for *Operation*\)

</td>
<td valign="top">

The path of the folder where to download as zip file.

Examples:

`/Homework/math`

`id:a4ayc_80_OEAAAAAAAAAXw`

</td>
</tr>
<tr>
<td valign="top">

*File Path* \(only if *Download File* is selected for *Operation*\)

</td>
<td valign="top">

The Path to the file which needs to be downloaded.

Examples:

`/Homework/math/Prime_Numbers.txt`

`id:a4ayc_80_OEAAAAAAAAAXw`

</td>
</tr>
<tr>
<td valign="top">

*Post-Processing* \(only if *Download File* is selected for *Operation*\)

</td>
<td valign="top">

Select the action to be performed after successful processing of the file.

-   *Delete File*

    The file is deleted after it has been processed successfully.

-   *Keep File and Process again*

    Keep the file for testing, and reprocess as specified by the scheduler. If you choose this option, the file is processed with every message processing run, even if it has not been changed.

-   *Move File* 

    Move the file to an Archive Directory \(Specified by the user in *Archive Directory* field\).

-   *Keep file and mark as processed in Idempotent repository* \(default\)

    Prevents a file from being consumed twice per integration flow. For that purpose, an idempotent repository \(database\) is activated.


> ### Note:  
> The idempotent repository contains information about files already been consumed from the Dropbox server. It stores the filenames in a database to synchronize between multiple worker nodes and to prevent the files from being read again when the runtime node is restarted. Filename entries are deleted by default after 90 days.



</td>
</tr>
<tr>
<td valign="top">

*Archive Directory* \(only if *Download File* is selected for *Operation* and *Move File* is selected for *Post-Processing*\)

</td>
<td valign="top">

Specifies the directory and the filename when moving the file after processing. The specified file path is defined relative to the directory specified with the *Directory* parameter.

> ### Note:  
> : The folder must be less than 20 GB in size and any single file within must be less than 4 GB in size. The resulting zip must have less than 10,000 file and folder entries in total, including the top-level folder. The input can't be a single file



</td>
</tr>
<tr>
<td valign="top">

*Raise Exception on Post-Processing Failure*

This option is available only with the following *Post-Processing* settings:

-   *Delete File* 

-   *Archive File* 

-   *Keep file and mark as processed in Idempotent repository* 




</td>
<td valign="top">

Select this option to raise error in the message processing log if post-processing fails.

> ### Note:  
> If the user checks the option, the message gets *Failed* status if post-processing fails. Otherwise, the message gets status *Successful*. In both cases, the post-processing operation status is stored as exchange property:
> 
> -   If post-processing operation fails and *Archive File* has been selected: The response status is stored in property `SAP_Dropbox_Archive_Response`.
> 
> -   If post-processing operation fails and *Delete File* has been selected: The response status is stored in property `SAP_Dropbox_Delete_Response`.
> 
> -   If post-processing operation fails and *Keep file and mark as processed in Idempotent repository* has been selected: The response status is stored in property `SAP_Dropbox_Keepfile_Response`.



</td>
</tr>
</table>

Select the *Scheduler* tab and provide values in the fields as follows.

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

*Every* 

</td>
<td valign="top">

Specify a time period \(for example, every hour\) in a dedicated time window.

</td>
</tr>
</table>

