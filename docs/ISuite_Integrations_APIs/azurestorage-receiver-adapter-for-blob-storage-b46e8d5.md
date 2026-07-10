<!-- loiob46e8d57a9a44537b21a5f6d521499a4 -->

# AzureStorage Receiver Adapter for BLOB Storage

The AzureStorage receiver adapter enables SAP Integration Suite to write BLOBs to Azure Storage.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a receiver channel and selected the *AzureStorage* receiver adapter and the *BLOB Storage* message protocol, you can configure the following attributes.

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

Receiver

</td>
</tr>
<tr>
<td valign="top">

*System* 

</td>
<td valign="top">

Receiver

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

*BLOB Storage*

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

*Dynamic* 

</td>
<td valign="top">

Select this option to dynamically define the authentication through the value of property `SAP_AzureStorage_Outbound_AuthType`.

-   To use Token Alias, use value `SASTOKEN`.

-   To use Key Alias, use value `SharedAccessKey`.




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

*Operation* 

</td>
<td valign="top">

Select one of the following options to define which operation to perform:

-   *Create Container*

    Creates blob container in the blob storage on the specified storage account.

-   *Delete Blob*

    Marks the specified blob for deletion. The blob is deleted later during garbage collection.

-   *Delete Container*

    Marks specified container for the deletion. The container and any blobs contained within it are later deleted during garbage collection.

-   *Get Blob Metadata*

    Returns all user-defined metadata for the specified blob.

-   *Get Blob Properties*

    Returns the properties of the specified blob.

-   *List Blobs*

    Lists all blobs in the container.

    The Prefix, Marker, MaxResults, and Delimiter elements are present only if they were specified on the request URL.

    The NextMarker element has a value only if the list results are not complete.

    If the request does not specify maxresults or specifies a value greater than 5,000, the server returns up to 5,000 items. If there are additional results to return, the service returns a continuation token in the NextMarker response element. In certain cases, the service may return fewer results than specified by max results and also return a continuation token.

-   *List Containers*

    Lists all containers in the blob storage.

-   *Set Blob Metadata*

    Sets user-defined metadata for the specified blob as one or more name value pairs.

-   *Upload Append Blob*

    Creates an append blob and uploads the content in the container. If the blob already exists, system appends the data. This operation supports only upload of files up to 4 MB size.

    > ### Note:  
    > Append blobs are intended for workflows like logging, where new entries can be appended to the end of a file. If any of the file formats have a specific schema in which data is to be written and processed, those files get corrupted during the append operation. Append operation merely adds data as characters at the end of file. It doesn’t specify the schema in which characters are appended to the original format. You can try appending text to a `.docx` file and it gets corrupted if you don’t specify the schema. Every a file format that is not attached to a schema appends data without getting corrupted. It is advised to be more cautious on which file type this operation is performed.

-   *Upload Blob from URL*

    Creates a new Block Blob where the contents of the blob are read from a given URL. The source blob can have any type, including a blob or container, private, or dynamic. The destination blob, however, must be a block blob. You need to provide the following details if you select this operation.

    The size of the source blob can be up to a maximum length of 256 MB. If the source blob is not public blob, then source blob has to be authenticated using SAS token only.

-   *Upload Block Blob*

    Creates a block blob and uploads the content. This operation supports a maximum file size of 4000 MB.




</td>
</tr>
<tr>
<td valign="top">

*Storage Account Name* 

</td>
<td valign="top">

Enter the name of the storage account for all the eleven previously-mentioned operations.

> ### Note:  
> The storage account name has been predefined already in the Azure Storage. If you enter a wrong name, the system displays an error message.



</td>
</tr>
<tr>
<td valign="top">

*Container Name* 

</td>
<td valign="top">

Enter the name of the container for all the previously-mentioned operations except for List Containers.

> ### Note:  
> Follow these rules when defining a container name:
> 
> -   Name contains only lowercase letters, numbers and hyphens.
> 
>     Name begins with either a letter or a number.
> 
>     Name size is between 3 and 63 characters.



</td>
</tr>
<tr>
<td valign="top">

*Public Access Level*

\(Only if for *Operation* the option *Create Container* is selected\)

</td>
<td valign="top">

Specifies if data in the container is to be accessed publicly and indicates the level of access. Specify one of the three levels: *blob*, *container* or *private* to the account owner \(default: *blob*\).

</td>
</tr>
<tr>
<td valign="top">

*Public Access Level*

Only if for *Operation* one of the following options is selected:

-   *Delete Blob*

-   *Get Blob Metadata*

-   *Get Blob Properties*

-   *Set Blob Metadata*

-   *Upload Append Blob*

-   *Upload Block Blob*




</td>
<td valign="top">

Enter blob path along with the blob name.

Example: `/finance/employeesalaries.txt`

</td>
</tr>
<tr>
<td valign="top">

*Prefix*

\(Only if for *Operation* the option *List Blobs* or *List Containers* is selected\)

</td>
<td valign="top">

Filters the results to return only blob whose name begins with the specified prefix.

</td>
</tr>
<tr>
<td valign="top">

*Page Size*

\(Only if for *Operation* the option *List Blobs* or *List Containers* is selected\)

</td>
<td valign="top">

Specify the page size to retrieve specific number of results. If you do not specify any page size, the server returns up to 5000 results.

</td>
</tr>
<tr>
<td valign="top">

*Process in Pages*

\(Only if for *Operation* the option *List Blobs* or *List Containers* is selected\)

</td>
<td valign="top">

Message is processed in batches with a size specified by the *Page Size* parameter. Select this checkbox only when using the adapter together with a *Looping Process Call* step.

-   If you do not specify both *Page Size* and *Process in Pages*, the server returns results up to the maximum results supported by the respective REST API.

-   If you specify only *Page Size*, the server returns results up to the specified page size.

-   If you specify only *Process in Pages*, the server returns results up to the maximum results supported by the respective REST API.

-   If you do not specify *Page Size* and *Process in Pages*, the server returns results up to the specified page size until all the results in the storage are retrieved \(to be used in *Looping Process Call*\).




</td>
</tr>
<tr>
<td valign="top">

*Metadata Name: Value*

\(Only if for *Operation* the option *Set Blob Metadata* is selected\)

</td>
<td valign="top">

Enter one or more name value pair to set the metadata in the format `revenue:incometax` for one and `finance:incometax|finance:exciseduty` for more than one. If nothing is passed for name value pair, existing metadata is deleted.

</td>
</tr>
<tr>
<td valign="top">

*Handling for Existing Append Blob*

\(Only if for *Operation* the option *Upload Append Blob* or *Upload Block Blob* is selected\)

</td>
<td valign="top">

Choose an action to perform if the blob already exists.

-   *Append*

    If file exists already, append the data. Otherwise, create the file and append the data.

-   *Fail*

    If file already exists, set message status to *Failed* in the message processing log. Otherwise, create file and write data.

-   *Ignore*

    If file already exists, ignore the data and set message status to *Success* in the message processing log. Otherwise, create file and write data.

-   *Dynamic*

    Specify parameter value dynamically by the value of one of the following properties:

    -   `SAP_AzureStorage_AppendBlobHandling` if *Operation* set to *Upload Append Blob*

    -   `SAP_AzureStorage_BlockBlobHandling` if *Operation* set to *Upload Block Blob*. In that case, the value defined in the channel is overwritten. The allowed values for this property are `Append`, `Fail`, and `Ignore`.





</td>
</tr>
<tr>
<td valign="top">

*Source Blob Type* 

</td>
<td valign="top">

Select the source Blob type.

-   *Blob or Container*: No authentication required. This is the default type.

-   *Private*: SAS Authentication is required.

-   *Dynamic*: Enter the property `SAP_AzureStorage_SourceBlobType` to define the source blob type dynamically.




</td>
</tr>
<tr>
<td valign="top">

*Source Blob URL*

\(Only if for *Operation* the option *Upload Blob from URL* is selected\)

</td>
<td valign="top">

Specify complete URL of the blob.

Example: `https://myaccount.blob.core.windows.net/mycontainer/myblob`

A new Block Blob is created, and the the content of the blob is read from the address given by the URL. The source blob can have any type, including a block blob, append blob, or page blob. The destination blob, however, must be a block blob.

</td>
</tr>
<tr>
<td valign="top">

*Destination Blob Path*

\(Only if for *Operation* the option *Upload Blob from URL* is selected\)

</td>
<td valign="top">

Enter blob path along with the blob name.

Example: `/employeesalary.txt`

</td>
</tr>
<tr>
<td valign="top">

*Source SAS Token Alias*

\(Only if for *Operation* the option *Upload Blob from URL* is selected\)

</td>
<td valign="top">

Enter alias name of token to be used to communicate with the Source Azure Blob.

</td>
</tr>
<tr>
<td valign="top">

*Handling of Existing Block Blob*

\(Only if for *Operation* the option *Upload Blob from URL* is selected\)

</td>
<td valign="top">

Choose an action to perform to handle the already existing blob.

-   *Overwrite*: If blob already exists in destination, overwrite the blob, otherwise create blob. This is the default action.

-   *Fail*

    If blob already exists, set message status to *Failed* in the message processing log. Otherwise, create blob.

-   *Ignore*

    If blob already exists in the destination, ignore and set message status to *Success* in the message processing log. Otherwise, create blob.

-   *Dynamic*

    Specify parameter value dynamically by the value of one of property `SAP_ AzureStorage_BlobFromURLHandling`.

    In that case, the value defined in the channel is overwritten. If property is not defined, message processing results in a failure. The allowed values for this property are `Overwrite`, `Fail`, and `Ignore`.




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
<tr>
<td valign="top">

*Response Format* 

</td>
<td valign="top">

The following response formats are given:

-   *JSON*

-   *XML*: Response is converted to XML format by the adapter.

-   *Default*: Response received from Azure Storage is handed over to the exchange without changing the format.

-   *Dynamic*: To define response format dynamically, enter the property `SAP_AzureStorage_Outbound_ResponseFormat`.




</td>
</tr>
<tr>
<td valign="top">

*Request Headers* 

</td>
<td valign="top">

Enter Pipe-separated \(`|`\) value list of request headers to be sent to Azure.

If you enter the value `*`, all message headers are converted to request headers and forwarded.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers* 

</td>
<td valign="top">

Enter Pipe-separated \(`|`\) value list of response headers.

The headers specified by Azure Storage are converted to message/exchange headers.

If you enter the value `*`, all response header values are converted to message/exchange headers.

</td>
</tr>
</table>



<a name="loiob46e8d57a9a44537b21a5f6d521499a4__section_h43_dzh_3wb"/>

## Default Headers and Exchange Properties


<table>
<tr>
<th valign="top">

Sl No

</th>
<th valign="top">

Operation

</th>
<th valign="top">

Name

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

1

</td>
<td valign="top">

Upload Block Blob

</td>
<td valign="top">

SAP\_AzureStorage\_Outbound\_BlockBlobName

</td>
<td valign="top">

Property

</td>
<td valign="top">

Capture the Block Blob name specified.

</td>
</tr>
<tr>
<td valign="top">

2

</td>
<td valign="top">

Upload Append Blob

</td>
<td valign="top">

SAP\_AzureStorage\_Outbound\_AppendBlobName

</td>
<td valign="top">

Property

</td>
<td valign="top">

Capture the Append blob name specified.

</td>
</tr>
<tr>
<td valign="top">

3

</td>
<td valign="top">

All Blob storage related operations \(Except

List Container\)

</td>
<td valign="top">

SAP\_AzureStorage\_Outbound\_ContainerName

</td>
<td valign="top">

Property

</td>
<td valign="top">

Capture the Container name specified in Blob storage operations.

</td>
</tr>
</table>

