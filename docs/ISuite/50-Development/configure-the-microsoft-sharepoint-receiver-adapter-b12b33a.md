<!-- loiob12b33a903ac4e388d1892a2febdc732 -->

# Configure the Microsoft SharePoint Receiver Adapter

The Microsoft SharePoint receiver adapter connects an SAP Integration Suite tenant to a remote system using HTTP protocol to write files to the system.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you've created a receiver channel and selected the **Microsoft SharePoint** receiver adapter, you can configure the following attributes.

Select the *General* tab to access the following parameters.

**General**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

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

HTTP

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

Value

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

Enter the path for site as *<site type/site name\>*, for example, `/teams/MicrosoftSharePointAdapter`.

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type* 

</td>
<td valign="top">

Select the authentication type. Supported types are:

-   *OAuth2 Client Credentials*

-   *OAuth2 Authorization Code*

-   *Dynamic*

    You must define the authentication method in the message exchange using the property `SAP_SharePointAuthMethod`. Supported values are:

    -   OAuth2AuthorizationCode

    -   OAuth2ClientCredentials


    If you select *Dynamic* and don't define the property, a runtime error occurs.




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

Select the *Processing* tab and access the following parameters.

**Processing**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Sub Parameter

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

*Product Type* 

</td>
<td valign="top">

Not Applicable

</td>
<td valign="top">

*SharePoint On-Cloud* 

</td>
</tr>
<tr>
<td valign="top" rowspan="7">

*Operation Group* 

</td>
<td valign="top">

Batch

</td>
<td valign="top">

JSON batching allows you to optimize your application by combining multiple requests \(up to 20\) into a single JSON object.

For example, you want to compose a view of unrelated data such as:

-   An image stored in OneDrive

-   A list of Planner tasks

-   The calendar for a group


Combining these three individual requests into a single batch request can save the application significant network latency.

</td>
</tr>
<tr>
<td valign="top">

Columns

</td>
<td valign="top">

Select one of the operations:

-   *List Columns in a Content type*: Get the collection of columns represented as columnDefinition resources in a Content type.

-   *List Columns in a List*: Get the collection of columns represented as columnDefinition resources in a list.

-   *List Columns in a Site*: Get the collection of columns represented as columnDefinition resources in a site.




</td>
</tr>
<tr>
<td valign="top">

Content types

</td>
<td valign="top">

Select one of the operations:

-   *Create column in a Content type*: Add a column to a content type in a site, or a list with a request that specifies a columnDefinition.

-   *Create Content Type*: Create a new Content type object in a site.

-   *Delete Content type*: Remove a Content type from a list or a site.

-   *Get Content type*: Retrieve the metadata for a Content type in a site or a list.

-   *List Content types in a list*: Get a list of the Content type objects and their properties in a list.

-   *List Content types in a site*: Get a list of the Content type objects and their properties in a site.

-   *Update Content type*: Update the properties of a Content type object.


To get the details of all content types, navigate to the following path: *SharePoint Application Home Screen* \> *Documents* \> *All Documents* \> *Settings* \> *Site Contents* \> *Site Settings* \> *Site content types*.

</td>
</tr>
<tr>
<td valign="top">

Files

</td>
<td valign="top">

Select one of the operations:

-   *Add permissions*: Sends a sharing invitation for a DriveItem. A sharing invitation provides permissions to the recipients and optionally sends them an email with a sharing link.

-   *Checkin:DriveItem*: Checks in a checked out DriveItem resource, which makes the version of the document available to others. This is used to unlock the file

-   *Checkout:DriveItem*: Checks out a DriveItem resource to prevent others from editing the document, and prevent your changes from being visible until the documented is checked in. This is used to lock the file.

-   *Create a sharinglink*: Shares a DriveItem via a sharing link using createLink if the specified link type doesn't already exist for the calling application. If a sharing link of the specified type already exists for the app, the existing sharing link is returned.

-   *Create New Folder*: Creates a new folder or DriveItem in a Drive with a specified parent item or path.

-   *Delete DriveItem*: Deletes a DriveItem by using its path. Note that deleting items using this method moves the items to the recycle bin instead of permanently deleting the item.

-   *Delete Permission*: Removes access to a DriveItem.

    Only sharing permissions that aren't inherited can be deleted. The InheritedFrom property must be null.

-   *DriveItem:Copy*: Asynchronously creates a copy of an DriveItem \(including any children\), under a new parent item or with a new name.

-   *DriveItem:Preview*: Allows you to obtain a short-lived embeddable URL for an item in order to render a temporary preview.

    If you want to obtain long-lived embeddable links, use the createLink API instead.

-   *Get Drive for Site*: Retrieve the properties and relationships of a Drive resource of SharePoint document libraries.

-   *Get Drive item resource*: Retrieve the metadata for a DriveItem in a drive by file system path or ID. item-id is the ID of a DriveItem. It may also be the unique ID of a SharePoint list item.

-   *Get Permissions*: Return the effective sharing permission for a particular permission resource.

    Effective permissions of an item can come from two sources: permissions set directly on the item itself or permissions that are inherited from the item's ancestors.

    Callers can differentiate if the permission is inherited or not by checking the inheritedFrom property. This property is an ItemReference resource referencing the ancestor that the permission is inherited from.

-   *List available drives*: Retrieve the list of Drive resources available for a target User, Group, or Site. To list the document libraries for a site, your app requests the drives relationship on the Site.

-   *List children of a DriveItem*: Return a collection of DriveItems in the children relationship of a DriveItem. DriveItems with a non-null folder or package facet can have one or more child DriveItems.

-   *List Permissions*: List the effective sharing permissions on a DriveItem. Retrieves the collection of permissions on an DriveItem.

-   *List Versions*: SharePoint can be configured to retain the history for files. Depending on the service and configuration, a new version can be created for each edit, each time the file is saved, manually, or never.

    Previous versions of a document are retained for a finite period of time depending on admin settings that may be unique per user or location.

-   *Move DriveItem*: To move a DriveItem to a new parent item, your app requests to update the parentReference of the DriveItem to move.

    This operation is a special case of the Update method. Your app can combine moving an item to a new container and updating other properties of the item into a single request.

    Items can't be moved between Drives using this request.

-   *Search for DriveItems*: Search the hierarchy of items for items matching a query. You can search within a folder hierarchy, a whole drive, or files shared with the current user.

-   *Track changes*: Track changes in a DriveItem and its children over time.

-   *Update DriveItem*: Update the metadata for a DriveItem by path.

-   *Update Permission*: Update the properties of a sharing permission by patching the permission resource. Only the roles property can be modified this way.

-   *Upload File*: Upload files up to 250 MB in size.

    > ### Note:  
    > The adapter uploads files to the `Documents` folder only. For example, when you define the directory path as `/ABC/XYZ` then the directory path redirects to `Documents/ABC/XYZ`.




</td>
</tr>
<tr>
<td valign="top">

List

</td>
<td valign="top">

Select one of the operations:

-   *Create List*: Creates a new list in a site.

-   *Enumerate List Items*: Gets the collection of items in a list.

-   *Get List*: Returns the metadata for a list.




</td>
</tr>
<tr>
<td valign="top">

ListItems

</td>
<td valign="top">

Select one of the operations:

-   *Create List Item*: Creates a new list item in a list.

-   *Delete List Item*: Removes an item from a list.

-   *Get List Items*: Returns the metadata for an item in a list.

-   *Listing Versions*: SharePoint can be configured to retain the history for files. Depending on the service and configuration, a new version can be created for each edit, each time the file is saved, manually, or never.

-   *Update List Item*: Update the properties of a list item.




</td>
</tr>
<tr>
<td valign="top">

Sites

</td>
<td valign="top">

Select one of the operations:

-   *Create Permissions*: Create a new permission object on a site.

-   *Delete Permissions*: Delete a permission object on a site.

-   *Enumerate SubSites*: Get a collection of subsites designed for a site.

-   *Get Permission*: Retrieve the properties and relationships of a permission object on a site.

-   *Get Activities by Interval*: Get a collection of itemActivityStats resources for the activities that took place on this resource within the specified time interval.

    This operation only supports a time range of 90 days for daily counts. The value of the startDateTime and endDateTime parameters must represent a time range of less than 90 days.

-   *Get Analytics*: Get itemAnalytics about the views that took place under this resource. The itemAnalytics resource is a convenient way to get activity stats for allTime and the lastSevenDays. For a custom time range or interval, use the getActivitiesByInterval API.

-   *Get Lists*: Get the collection of lists for a site.

    Lists with the system facet are hidden by default. To list them, include system in your $select statement.

-   *Get Site*: Retrieve properties and relationships for a site resource. A site resource represents a team site in SharePoint.

-   *List Permissions*: List the effective sharing permissions on a DriveItem. Get the permission resources from the permissions navigation property on a site.

-   *Search for Sites*: Search across a SharePoint tenant for sites that match keywords provided.

    The only property that works for sorting is createdDateTime which shows the date and time in which the item was created. The search filter is a free text search that uses multiple properties when retrieving the search results.

-   *Update permission*: Update the permission object on a site. Update the properties of a sharing permission by patching the permission resource. Only the roles property can be modified this way.




</td>
</tr>
<tr>
<td valign="top">

*List Name* 

</td>
<td valign="top" colspan="2">

Enter the name of the list.

</td>
</tr>
<tr>
<td valign="top">

*Content Type Name* 

</td>
<td valign="top" colspan="2">

Enter the name of content type, for example, `Item/Document Set/Folder`.

</td>
</tr>
<tr>
<td valign="top">

*Query* 

</td>
<td valign="top" colspan="2">

Enter the search term, for example, `searchindex=indexname`.

</td>
</tr>
<tr>
<td valign="top">

*Page Size* 

</td>
<td valign="top" colspan="2">

Specify maximum number of results to be retrieved per page.

</td>
</tr>
<tr>
<td valign="top">

*Process in Pages* 

</td>
<td valign="top" colspan="2">

Message is processed in batches with size as specified in Page Size. Select only when used together with Looping Process Call.

</td>
</tr>
<tr>
<td valign="top">

*Column Name* 

</td>
<td valign="top" colspan="2">

Enter the name of the column.

</td>
</tr>
<tr>
<td valign="top">

*Directory* 

</td>
<td valign="top" colspan="2">

Enter directory path to where the file must be written, for example, `/mydirectory/mysubdirectory`.

</td>
</tr>
<tr>
<td valign="top">

*File Name* 

</td>
<td valign="top" colspan="2">

Enter name of the file to be written.

> ### Note:  
> If you don't enter a file name and the parameter remains blank, the content of the CamelFileName header is used as file name. If this header isn't specified, the Exchange ID is used as file name.
> 
> Expressions such as ab\*, a.\*, \*a\*, and so on, aren't supported.



</td>
</tr>
<tr>
<td valign="top">

*Comment* 

</td>
<td valign="top" colspan="2">

Specify the comment associated with the version.

</td>
</tr>
<tr>
<td valign="top">

*ExpirationDateTime* 

</td>
<td valign="top" colspan="2">

Enter the DateTime format of ‘yyyy-MM-ddTHH:mm:ss’ as the expiration time of the permission.

</td>
</tr>
<tr>
<td valign="top">

*Type* 

</td>
<td valign="top" colspan="2">

Select one of the types of sharing link:

-   View

-   Edit

-   Dynamic

    You must dynamically define the value in the message exchange using the property `SAP_SharePointOutboundType`. Supported values are:

    -   View

    -   Edit





</td>
</tr>
<tr>
<td valign="top">

*Scope* 

</td>
<td valign="top" colspan="2">

Select one of the scopes:

-   Anonymous

-   None

-   Organization

-   Users

-   Dynamic

    You must dynamically define the value in the message exchange using the property `SAP_SharePointOutboundScope`. Supported values are:

    -   Anonymous

    -   None

    -   Organization

    -   Users





</td>
</tr>
<tr>
<td valign="top">

*Folder Name* 

</td>
<td valign="top" colspan="2">

Enter folder name to create it under specified directory.

</td>
</tr>
<tr>
<td valign="top">

*Permission ID* 

</td>
<td valign="top" colspan="2">

Enter the Permission ID, which is received when the permission was created.

</td>
</tr>
<tr>
<td valign="top">

*Source Directory* 

</td>
<td valign="top" colspan="2">

Enter directory path from where the file must be read, for example, `/mydirectory/mysubdirectory`.

</td>
</tr>
<tr>
<td valign="top">

*Source File Name* 

</td>
<td valign="top" colspan="2">

Enter name of the file to be read. Source filename is available in source directory.

</td>
</tr>
<tr>
<td valign="top">

*Target Directory* 

</td>
<td valign="top" colspan="2">

Enter directory path to where the file must be written, for example, `/mydirectory/mysubdirectory`.

</td>
</tr>
<tr>
<td valign="top">

*Target File Name* 

</td>
<td valign="top" colspan="2">

Enter name of the file that must be placed in the target directory.

</td>
</tr>
<tr>
<td valign="top">

*Search For Item* 

</td>
<td valign="top" colspan="2">

Enter any search keyword to get the available list of drive items.

</td>
</tr>
<tr>
<td valign="top">

*Existing File Name* 

</td>
<td valign="top" colspan="2">

Enter the existing file name that is being renamed.

</td>
</tr>
<tr>
<td valign="top">

*New File Name* 

</td>
<td valign="top" colspan="2">

Enter the new file name.

</td>
</tr>
<tr>
<td valign="top">

*Role Type* 

</td>
<td valign="top" colspan="2">

Specify the role type:

-   Owner

-   Read

-   Write

-   Dynamic

    You must dynamically define the value in the message exchange using the property `SAP_SharePointOutboundRoleType`. Supported values are:

    -   Owner

    -   Read

    -   Write





</td>
</tr>
<tr>
<td valign="top">

*Handling for Existing Files* 

</td>
<td valign="top" colspan="2">

Select one of the actions to handle the existing file:

-   Rename

-   Replace

-   Dynamic


You must dynamically define the value in the message exchange using the property `SAP_SharePoint_FileHandling`. Supported values are:

-   Replace

-   Rename




</td>
</tr>
<tr>
<td valign="top">

*Item ID* 

</td>
<td valign="top" colspan="2">

Enter the item ID of the list for the specified List name.

</td>
</tr>
<tr>
<td valign="top">

*StartDateTime* 

</td>
<td valign="top" colspan="2">

Enter the starting point of time range that must be in the format “YYYY-MM-DD”.

This parameter supports a time range of 90 days for daily counts. The value must represent a time range of less than 90 days.

</td>
</tr>
<tr>
<td valign="top">

*EndDateTime* 

</td>
<td valign="top" colspan="2">

Enter the ending point of time range that must be in the format “YYYY-MM-DD”.

This parameter supports a time range of 90 days for daily counts. The value must represent a time range of less than 90 days.

</td>
</tr>
<tr>
<td valign="top">

*Interval* 

</td>
<td valign="top" colspan="2">

Select one of the values:

-   Day

-   Month

-   Week




</td>
</tr>
<tr>
<td valign="top">

*AnalyticsTimeRange* 

</td>
<td valign="top" colspan="2">

Select one of the values:

-   All Time

-   Seven Days




</td>
</tr>
<tr>
<td valign="top">

*Response Format* 

</td>
<td valign="top" colspan="2">

Select one of the values:

-   JSON

-   XML

-   Dynamic

    You must define the value ‘JSON’ or ‘XML’ in the message exchange using the property `SAP_SharePointOutboundResponseFormat`.




</td>
</tr>
<tr>
<td valign="top">

*Request Header* 

</td>
<td valign="top" colspan="2">

Pipe separated list of HTTP request headers to be sent to the Microsoft SharePoint target system.

</td>
</tr>
<tr>
<td valign="top">

*Response Header* 

</td>
<td valign="top" colspan="2">

Pipe separated list of HTTP response headers. The specified headers from Microsoft SharePoint target system are received in the message exchange.

</td>
</tr>
</table>

