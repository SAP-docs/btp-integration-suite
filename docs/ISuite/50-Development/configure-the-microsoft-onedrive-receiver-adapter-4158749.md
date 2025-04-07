<!-- loio4158749080004a2db7d7005b059b06c1 -->

# Configure the Microsoft OneDrive Receiver Adapter

The Microsoft OneDrive receiver adapter connects a SAP Integration Suite tenant to a remote system using HTTP protocol.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you've created a receiver channel and selected the **Microsoft OneDrive** receiver adapter, you can configure the following attributes.

Select the *General* tab to provide the values in the fields as follows:

****


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

****


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

-   *Dynamic* : If you select **Dynamic**, the properties are set in content modifier and defined under ‘SAP\_OneDriveAuthMethod’




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

****


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
<td valign="top" rowspan="4">

*Operation Group* 

</td>
<td valign="top">

Batch

JSON batching allows you to optimize your application by combining multiple requests \(up to 20\) into a single JSON object.

Combining these ‘n’ individual requests into a single batch request can save the application significant network latency.

> ### Note:  
> You can only combine upto 20 calls only in request body.



</td>
</tr>
<tr>
<td valign="top">

Drives

Select one of the operations:

-   *Get Drive metadata of another Drive*: Retrieve the properties and relationships of a Drive resource.

-   *Get root folder for user’s default Drive*: Retrieve the metadata for a DriveItem in a Drive by file system path or ID.

-   *List available Drives*: Retrieve the list of Drive resources available for a target user, Group, or Site.

-   *List Shared Files*: Retrieve a collection of DriveItem resources that have been shared with the owner of the Drive.

-   *List recent Files*: List a set of items that have been recently used by the signed in user. This collection includes items that are in the user’s drive as well as items that have access to from other drives.
-   *List activities under the Drive*: List recent activities that took place on an item or under a hierarchy.

-   *List children under the Drive*: Return a collection of DriveItems in the children relationship of a DriveItem

-   *Search for Items in the Drive*: Search the hierarchy of items for items matching a query. You can search with a folder hierarchy, a whole drive, or files shared within the current user.
-   *Get Special Folder*: Use the special collection to access a special folder by name.



</td>
</tr>
<tr>
<td valign="top">

Drive Items

Select one of the operations:

-   *Get item*: Retrieve the metadata for a DriveItem in a Drive by file system path or ID.

-   *List activities*: List the recent activities that took place on an item or under a hierarchy.

-   *List children*: Return a collection of DriveItems in the children relationship of a DriveItem.

-   *List versions*: OneDrive can be configured to retain the history for files.

-   *Get version*: Retrieve the metadata for specific version of a DriveItem.

-   *Create item*: Create a new folder or DriveItem in a Drive with a specified parent item or path.

-   *Restore version*: Restore a previous version of a DriveItem to be the current version.

-   *Sync changes*: This method allows to track changes to a drive and its children over time.

-   *Check in*: Check-in a checked out DriveItem resource, which makes the version of the document available to others.

-   *Check out*: Check out a DriveItem resource to prevent others from editing the document, and your changes from being visible until the documented is checked-in.

-   *Update item*: Update the metadata for a DriveItem by ID or path.

-   *Upload file*: The simple upload API allows you to provide the contents of a new file or update the contents of an existing file in a single API call.

    > ### Note:  
    > Exit API capability is 4MB. CPI/ADK can support the same.

-   *Delete item*: Delete a DriveItem by using its ID or path.

    > ### Note:  
    > Deleting items using this method will move the items to the recycle bin instead of permanently deleting the item.

-   *Move item*: To move a DriveItem to a new parent item, the request is made to update the parentReference of the DriveItem to move.

-   *Copy item*: Asynchronously creates a copy of a driveitem \(including any children\), under a new parent item or with a new name.

-   *Search items*: Search the hierarchy of items for items matching the query. You can search within a folder hierarchy, a whole drive, or files shared with the current user.

-   *List changes in a Drive*: This method allows to track changes to a drive and its children over time.

-   *Download a file in another format*: Use this API to retrieve the contents of an item in a specific format. Not all files can be converted into given formats.




</td>
</tr>
<tr>
<td valign="top">

Permissions

Select one of the operations:

-   *Add permissions*: Sends a sharing invitation for a DriveItem. A sharing invitation provides permissions to the recipients and optionally sends them an email with a sharing link.

-   *Delete Permission*: Removes access to a DriveItem.

-   *Get Permissions*: Return the effective sharing permission for a particular permission resource.

-   *Update Permission*: Update the properties of a sharing permission by patching the permission resource. Only the roles property can be modified this way.

-   *Create a sharing Link*: You can use createLink to share a DriveItem via sharing link.

-   *List Permissions*: List the effective sharing permissions of on a DriveItem.

-   *Get shared item*: Access a shared DriveItem or collection of shared items by using a shareId of sharing URL. To use a sharing URL with this API, your app needs to transform the URL into sharing token.




</td>
</tr>
<tr>
<td valign="top">

*Operation Name* 

</td>
<td valign="top">

Enter the name of the operation from the given options.

</td>
</tr>
<tr>
<td valign="top">

*Query* 

</td>
<td valign="top">

Enter the search term, for example, `searchindex=indexname`.

</td>
</tr>
<tr>
<td valign="top">

*Page Size* 

</td>
<td valign="top">

Specify maximum number of results to be retrieved per page.

</td>
</tr>
<tr>
<td valign="top">

*Process in Pages* 

</td>
<td valign="top">

Message is processed in batches with size as specified in Page Size. Select only when used together with Looping Process Call.

The Looping Process call has fields as below:

-   *Expression Type – XML or Non-XML*

-   *Condition Expression* – The condition that OneDrive has more records needs to be given in this field, `${property.SAP_OneDrive_HasMoreRecords} contains true`.

-   *Max. number of Iterations*– The number of times a looping process will be called..

-   *Action when Max. Iterations* – End Loop/Throw Exception




</td>
</tr>
<tr>
<td valign="top">

*Directory* 

</td>
<td valign="top">

Enter directory path to where the file must be written, for example, `/mydirectory/mysubdirectory`.

</td>
</tr>
<tr>
<td valign="top">

*File Name* 

</td>
<td valign="top">

Enter name of the file to be written.

The file name can be mandatory or optional based on the operation selected.

</td>
</tr>
<tr>
<td valign="top">

*Comment* 

</td>
<td valign="top">

Specify the comment associated with the version.

</td>
</tr>
<tr>
<td valign="top">

*ExpirationDateTime* 

</td>
<td valign="top">

Enter the DateTime format of `yyyy-MM-ddTHH:mm:ss` as the expiration time of the permission.

</td>
</tr>
<tr>
<td valign="top">

*Type* 

</td>
<td valign="top">

Select one of the types of sharing link:

-   *View*
-   *Edit*
-   *Dynamic* : You must dynamically define the value in the message exchange using the property `SAP_OneDriveOutboundType`. Supported values are:

    -   View
    -   Edit




</td>
</tr>
<tr>
<td valign="top">

*Scope* 

</td>
<td valign="top">

Select one of the scopes:

-   *Anonymous*
-   *None*
-   *Organization*
-   *Dynamic* : You must dynamically define the value in the message exchange using the property `SAP_OneDriveOutboundScope`. Supported values are:

    -   Anonymous
    -   None
    -   Organization




</td>
</tr>
<tr>
<td valign="top">

*Folder Name* 

</td>
<td valign="top">

Enter folder name to create it under specified directory.

</td>
</tr>
<tr>
<td valign="top">

*Permission ID* 

</td>
<td valign="top">

Enter the Permission ID, which is received when the permission was created.

</td>
</tr>
<tr>
<td valign="top">

*Source Directory* 

</td>
<td valign="top">

Enter directory path from where the file must be read, for example, `/mydirectory/mysubdirectory`.

</td>
</tr>
<tr>
<td valign="top">

*Source File Name* 

</td>
<td valign="top">

Enter name of the file to be read. Source filename is available in source directory.

</td>
</tr>
<tr>
<td valign="top">

*Target Directory* 

</td>
<td valign="top">

Enter directory path to where the file must be written, for example, `/mydirectory/mysubdirectory`.

</td>
</tr>
<tr>
<td valign="top">

*Target File Name* 

</td>
<td valign="top">

Enter name of the file that must be placed in the target directory.

</td>
</tr>
<tr>
<td valign="top">

*Search For Item* 

</td>
<td valign="top">

Enter any search keyword to get the available list of drive items.

</td>
</tr>
<tr>
<td valign="top">

*Existing File Name* 

</td>
<td valign="top">

Enter the existing file name that is being renamed.

</td>
</tr>
<tr>
<td valign="top">

*New File Name* 

</td>
<td valign="top">

Enter the new file name.

</td>
</tr>
<tr>
<td valign="top">

*Version ID* 

</td>
<td valign="top">

Enter the version ID to get the specific version details of the item.

</td>
</tr>
<tr>
<td valign="top">

*Response Format* 

</td>
<td valign="top">

Select one of the values:

-   *JSON*
-   *XML*
-   *Dynamic* : You must dynamically define the value in the message exchange using the property `SAP_OneDriveOutboundResponseFormat`:

    -   JSON
    -   XML




</td>
</tr>
<tr>
<td valign="top">

*Request Header* 

</td>
<td valign="top">

Pipe separated list of HTTP request headers to be sent to the Microsoft SharePoint target system.

</td>
</tr>
<tr>
<td valign="top">

*Response Header* 

</td>
<td valign="top">

Pipe separated list of HTTP response headers. The specified headers from Microsoft SharePoint target system are received in the message exchange.

</td>
</tr>
</table>

> ### Note:  
> The OneDrive adapter supports dynamic configurations of fields with the help of Content Modifier. The fields can be set with syntax `${header.fieldname}` or `${property.fieldname}` and the values can be set under the Content Modifier under message headers or exchange properties section.
> 
> If the receiver side makes a post call, the request body has to be passed under the message body section.

