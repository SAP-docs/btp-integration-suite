<!-- loio16ef7b42f5084db28fd2644a0825ec87 -->

# Configure the Dropbox Receiver Adapter

The Dropbox receiver adapter enables SAP Integration Suite to write files and folders to the Dropbox storage.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a receiver channel and selected the Dropbox sender adapter, you can configure the following attributes.

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

Maximum waiting time \(in milliseconds\) to contact the Dropbox server while establishing a connection.

Default value: `300000`

You can use property `SAP_DropboxTimeout` to dynamically define the value. In that case value defined in the channel is overwritten.

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

-   *Copy File or Folder* 

    Copies a file or folder to a different location in the Dropbox account. If the source path is a folder, all its contents is copied.

-   *Create Folder*

    Creates a folder at a given path in the Dropbox account.

-   *Delete File or Folder*

    Deletes the file or folder at a given path. If the path is a folder, all its contents is deleted as well.

-   *Get File URL*

    Gets a temporary link to stream content of a file.

-   *Get Metadata for File or Folder*

    Returns the metadata for a file or folder.

-   *Get Storage Statistics*

    Gets the space usage information for the current user's account.

-   *List Folder*

    Starts returning the contents of a folder \(files and subfolders\).

-   *List Revisions for File and Folder*

    Returns revisions for files based on a file path or a file id. The file path or file id is identified from the latest file entry at the given file path or id.

-   *Move File or Folder*

    Moves a file or folder to a different location in the user's Dropbox account. If the source path is a folder, all its content is moved.

-   *Update Metadata for File or Folder*

    Adds, updates, or removes properties associated with the supplied file and templates.

-   *Search File or Folder*

    Searches for files and folders.

-   *Search File or Folder*

    Searches for files and folders.

-   *Upload File*

    Creates a new file with the contents provided in the request.




</td>
</tr>
<tr>
<td valign="top">

*Source Path* \(only if *Copy File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

Path of the file to be copied.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Destination Path* \(only if *Download File* is selected for *Operation*\)

</td>
<td valign="top">

Path of the destination filename or ID.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Handling of Existing Files* \(only if *Copy File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

Defines how to proceed if the file already exists. There are the following options:

-   *Auto Rename* 

    Renames the file automatically. This feature is provided by Dropbox.

-   *Fail* 

    Throws an exception if a file with same name exists.

-   *Ignore* 

    Doesn't perform the operation if a file already exists. The message status is set to *Completed*.

-   *Dynamic* 

    Select this option to dynamically specify this parameter using a property.

    You can use property `SAP_DropboxHandling` to dynamically define the value by using the *Dynamic* option. In that case, the value defined in the channel is overwritten.

    Allowed values for `SAP_DropboxHandling`: `Auto Rename`, `Fail`, `Ignore`




</td>
</tr>
<tr>
<td valign="top">

*Folder Path* \(only if *Create Folder* is selected for *Operation*\)

</td>
<td valign="top">

Path in the Dropbox account where to create the folder. The folder ID is also accepted as an input.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Handling of Existing Folder* \(only if *Create Folder* is selected for *Operation*\)

</td>
<td valign="top">

Defines how to proceed if the file already exists. There are the following options:

-   *Auto Rename* 

    Renames the file automatically. This feature is provided by Dropbox.

-   *Fail* 

    Throws an exception if a file with same name exists.

-   *Ignore* 

    Doesn't perform the operation if a file already exists. The message status is set to *Completed*.

-   *Dynamic* 

    Select this option to dynamically specify this parameter using a property.

    You can use property `SAP_DropboxAfterProc` to dynamically define the value by using the *Dynamic* option. In that case, the value defined in the channel is overwritten.

    Allowed values for `SAP_DropboxAfterProc`: `Auto Rename`, `Fail`, `Ignore`




</td>
</tr>
<tr>
<td valign="top">

*Path* \(only if *Delete* is selected for *Operation*\)

</td>
<td valign="top">

Path in the Dropbox account to delete the file/folder.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*File Path* \(only if *Get File URL* is selected for *Operation*\)

</td>
<td valign="top">

Path to the file for which you like to define a temporary link.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

> ### Note:  
> This link expires within 4 hours. Afterwards, you get a `410 Gone` error. Don't use this URL to display content directly in the browser.



</td>
</tr>
<tr>
<td valign="top">

*Path* \(only if *Get Metadata for File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

The path of a file or folder on Dropbox.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Include Deleted* \(only if *Get Metadata for File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

If true, `Deleted Metadata` is returned for deleted file or folder. If false, a `LookupError.not_found` is returned.

Metadata for the root folder isn't supported.

You can use property `SAP_DropboxIncludeDeleted` to dynamically define the value. Allowed Values for `SAP_DropboxIncludeDeleted` are `true` and `false`.

</td>
</tr>
<tr>
<td valign="top">

*Folder Path* \(only if *List Folder* is selected for *Operation*\)

</td>
<td valign="top">

Scope of the search to a path in the Dropbox account. Accepts dynamic values.

Examples:

`/Homework/math`

`id: a4ayc_80_OEAAAAAAAAAXw`

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Recursive* \(only if *List Folder* is selected for *Operation*\)

</td>
<td valign="top">

If true, the system returns the list of files and folders inside the subfolders.

You can use property `SAP_DropboxRecursive` to dynamically define the value. Allowed Values for `SAP_DropboxRecursive` are `true` and `false`.

</td>
</tr>
<tr>
<td valign="top">

*Limit* \(only if *List Folder* is selected for *Operation*\)

</td>
<td valign="top">

Specify the number of entries returned.

You can use property `SAP_DropboxLimit` to dynamically define the value.

Default value is 1000. Maximum value is 2000.

</td>
</tr>
<tr>
<td valign="top">

*Mode* \(only if *List Revisions for File and Folder* is selected for *Operation*\)

</td>
<td valign="top">

Determines the behavior of the API in listing the revisions for a given file path or file id.

</td>
</tr>
<tr>
<td valign="top">

*Path/ID* \(only if *List Revisions for File and Folder* is selected for *Operation*\)

</td>
<td valign="top">

The path to the file for which you like to see the revisions.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Limit* \(only if *List Revisions for File and Folder* is selected for *Operation*\)

</td>
<td valign="top">

The maximum number of revision entries returned.

Maximum value is 100.

You can use property `SAP_DropboxLimit` to dynamically define the value.

</td>
</tr>
<tr>
<td valign="top">

*Source Path* \(only if *Move File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

Path of the File to be moved.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Destination Path* \(only if *Move File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

Path of the destination filename or ID.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Handling of Existing Folder* \(only if *Move File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

Defines how to proceed if the file already exists. There are the following options:

-   *Auto Rename* 

    Renames the file automatically. This feature is provided by Dropbox.

-   *Fail* 

    Throws an exception if a file with same name exists.

-   *Ignore* 

    Doesn't perform the operation if a file already exists. The message status is set to *Completed*.

-   *Dynamic* 

    Select this option to dynamically specify this parameter using a property.

    You can use property `SAP_DropboxHandling` to dynamically define the value by using the *Dynamic* option. In that case, the value defined in the channel is overwritten.

    Allowed values for `SAP_DropboxHandling`: `Auto Rename`, `Fail`, `Ignore`




</td>
</tr>
<tr>
<td valign="top">

*Query* \(only if *Search File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

The file or folder to search for.

May match across multiple fields based on the request arguments.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

Examples:

`Filename*`

`Foldername*`

</td>
</tr>
<tr>
<td valign="top">

*Path* \(only if *Search File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

Scope of the search to a path in the Dropbox account.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Max Results* \(only if *Search File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

Maximum number of results to be returned from Dropbox.

</td>
</tr>
<tr>
<td valign="top">

*Order By* \(only if *Search File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

Specified property of the order of search results.

It can be the case that recent changes are not immediately reflected in search results due to a short delay in indexing. Duplicate results can be returned across pages.

You can dynamically set the values using the property `SAP_DropboxOrderBy` by choosing the *Dynamic* option.

Allowed values for `SAP_DropboxOrderBy` are `modifiedTime` and `relevance`.

</td>
</tr>
<tr>
<td valign="top">

*Path* \(only if *Update Metadata for File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

A unique identifier for the file or folder.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Template ID* \(only if *Update Metadata for File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

A unique identifier for a property template.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Add or update fields* \(only if *Update Metadata for File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

Property fields to update. If the property field already exists, it is updated. If the property field doesn't exist, the property group is added.

</td>
</tr>
<tr>
<td valign="top">

*Remove fields* \(only if *Update Metadata for File or Folder* is selected for *Operation*\)

</td>
<td valign="top">

Property fields to remove \(by name\), provided they exist.

</td>
</tr>
<tr>
<td valign="top">

*File Path* \(only if *Upload File* is selected for *Operation*\)

</td>
<td valign="top">

Path in the Dropbox account where to save the file.

You can configure this parameter by entering a dynamic expression such like `${property. property_name}` or `${header.header_name}`.

</td>
</tr>
<tr>
<td valign="top">

*Handling of Existing Folder* \(only if *Upload File* is selected for *Operation*\)

</td>
<td valign="top">

Defines how to proceed if the file already exists. There are the following options:

-   *Auto Rename* 

    Renames the file automatically. This feature is provided by Dropbox.

-   *Fail* 

    Throws an exception if a file with same name exists.

-   *Ignore* 

    Doesn't perform the operation if a file already exists. The message status is set to *Completed*.

-   *Overwrite* 

    Overwrites the existing file with the new one.

-   *Dynamic* 

    Select this option to dynamically specify this parameter using a property.

    You can use property `SAP_DropboxAfterProc` to dynamically define the value by using the *Dynamic* option. In that case, the value defined in the channel is overwritten.

    Allowed values for `SAP_DropboxAfterProc`: `Auto Rename`, `Fail`, `Ignore`, `Overwrite`




</td>
</tr>
<tr>
<td valign="top">

*Response Format* 

</td>
<td valign="top">

There are the following options:

-   *JSON*

    Response displayed in JSON format.

-   *XML*

    Response displayed in XML format \(converted to XML by the adapter\).




</td>
</tr>
<tr>
<td valign="top">

*Request Headers* 

</td>
<td valign="top">

Pipe-separated value list of request headers to be sent to Dropbox.

If the value `*` is entered, all message headers are converted to request headers and forwarded.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers* 

</td>
<td valign="top">

Pipe-separated value list of response headers. The specified headers from Dropbox are converted to message/exchange headers.

If the value `*` is entered, all response header values are converted to message/exchange headers.

</td>
</tr>
<tr>
<td valign="top">

*Mute* 

</td>
<td valign="top">

In general, users are made aware of any file modifications in their Dropbox account via notifications in the client software. If true, this tells the clients that this modification shouldn't result in a user notification. You can use property `SAP_DropboxMute` to dynamically define the value. In that case value defined in the channel is overwritten.

Allowed Values for `SAP_DropboxMute` are `true` or `false`.

> ### Note:  
> Do not use this option to upload a file larger than 150 MB.



</td>
</tr>
</table>

