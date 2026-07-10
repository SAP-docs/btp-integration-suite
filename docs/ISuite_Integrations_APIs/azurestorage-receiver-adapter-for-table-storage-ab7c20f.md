<!-- loioab7c20f6ff2045d4b4013bb46fa2d196 -->

# AzureStorage Receiver Adapter for Table Storage

The AzureStorage receiver adapter enables SAP Integration Suite to perform write operations on tables on Azure Storage.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a receiver channel and selected the *AzureStorage* receiver adapter and the *Table Storage* message protocol, you can configure the following attributes.

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

*Table Storage*

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

-   *Add Entity*

    Inserts a new entity into the table \(does not support batch addition\).

-   *Create Table*

    Creates a new table in the storage account. If a table with the same name already exists in the account, an error is thrown.

-   *Delete Entity*

    Deletes an existing entity in the table.

-   *Delete Table*

    Deletes the specified table along with its data.

-   *Get Entities*

    Returns the queries of entities in a table with filter and select option. This operation can return a maximum of 1,000 entities at one time and execute for a maximum of five seconds. The response includes custom headers containing the continuation token in the following cases:

    -   If the result set contains more than 1,000 entities

    -   If the query doesn't complete within five seconds

    -   If the query crosses the partition boundary


-   *List Tables*

    Returns the list of tables under the specified storage account.

-   *Update Entity*

    Updates an existing entity in a table. This operation replaces the entire entity and can be used to remove properties.




</td>
</tr>
<tr>
<td valign="top">

*Storage Account Name* 

</td>
<td valign="top">

Enter the name of the storage account for all operations.

> ### Note:  
> The storage account name has been predefined already in the Azure Storage. If you enter a wrong name, the system displays an error message.



</td>
</tr>
<tr>
<td valign="top">

*Table Name* 

</td>
<td valign="top">

Enter the name of the name of the table for all operations, except \(*List Tables*\).

> ### Note:  
> Follow these rules when defining a table name:
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

*Partition Key*

\(Only if for *Operation* the option *Add Entity*, *Delete Entity* or *Update Entity* is selected\)

</td>
<td valign="top">

Enter the partition key.

Don't leave this field empty.

</td>
</tr>
<tr>
<td valign="top">

*Row Key*

\(Only if for *Operation* the option *Add Entity*, *Delete Entity* or *Update Entity* is selected\)

</td>
<td valign="top">

Enter the partition key.

Don't leave this field empty.

</td>
</tr>
<tr>
<td valign="top">

*Query Options*

\(Only if for *Operation* the option *Get Entities* or *List Tables* is selected\)

</td>
<td valign="top">

Enter query options. Prefix each query options with `$` character and separate by `&`. Filter, top, select can be used as query options.

-   You can use `$top` and `$select` as query parameters.

-   If both `$top` is used in the query and *Page Size* parameter is specified, pagination considers only *Page Size* parameter \(ignoring the `$top`\).




</td>
</tr>
<tr>
<td valign="top">

*Page Size*

\(Only if for *Operation* the option *Get Entities* or *List Tables* is selected\)

</td>
<td valign="top">

Specify the page size to retrieve specific number of results. If you do not specify any page size, the server returns up to 1000 results.

</td>
</tr>
<tr>
<td valign="top">

*Process in Pages*

\(Only if for *Operation* the option *Get Entities* or *List Tables* is selected\)

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
</table>



<a name="loioab7c20f6ff2045d4b4013bb46fa2d196__section_h43_dzh_3wb"/>

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

All table storage-related operations \(except *List Table*\)

</td>
<td valign="top">

SAP\_AzureStorage\_Outbound\_Tablename

</td>
<td valign="top">

Property

</td>
<td valign="top">

Capture the table name specified in the table storage operations.

</td>
</tr>
</table>

