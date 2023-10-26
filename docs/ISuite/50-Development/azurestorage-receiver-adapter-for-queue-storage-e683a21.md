<!-- loioe683a211578d4ef1820d0dd46ec3c80f -->

# AzureStorage Receiver Adapter for Queue Storage

The AzureStorage receiver adapter enables SAP Integration Suite to write files and folders to Azure Storage.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a third-party web service that is outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.

Once you have created a receiver channel and selected the *AzureStorage* receiver adapter and the *Queue Storage* message protocol, you can configure the following attributes.

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

*Queue Storage*

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

-   *Create Queue*

    Creates queue on the specified storage account.

-   *Delete Message*

    Deletes the specified message from the queue.

-   *Delete Queue*

    Permanently deletes the specified queue.

-   *Get Messages*

    Retrieves one or more messages upto a maximum of 32 messages from the front of the queue.

-   *Get Queue Metadata*

    Returns all user-defined metadata and queue properties on the specified queue. Metadata is associated with the queue as name-values pairs.

-   *List Queues*

    Returns the list of queues in the specified storage account.

-   *Peek Messages*

    Retrieves one or more messages from the front of the queue but does not alter the visibility of the message.

-   *Put Message*

    Adds a new message to the queue.

-   *Set Queue Metadata*

    Sets user-defined metadata on the specified queue as one or more name value pairs.

-   *Upload Message*

    Updates the visibility timeout of a message. You can also use this operation to update the contents of a message. A message must be in a format that can be included in an XML request with UTF-8 encoding, and the encoded message can be up to 64KB in size.




</td>
</tr>
<tr>
<td valign="top">

*Storage Account Name* 

</td>
<td valign="top">

Enter the name of the storage account for all the eleven above-mentioned operations.

> ### Note:  
> The storage account name has been predefined already in the Azure Storage. If you enter a wrong name, the system displays an error message.



</td>
</tr>
<tr>
<td valign="top">

*Queue Name* 

</td>
<td valign="top">

Enter the name of the container for all the above-mentioned operations except for *List Queues*.

> ### Note:  
> Follow these rules when defining a queue name:
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

*Popreceipt*

\(Only if for *Operation* the option *Delete Message* or *Update Message* is selected\)

</td>
<td valign="top">

Specifies the valid pop receipt value returned from an earlier call to the *Update Message* operation

</td>
</tr>
<tr>
<td valign="top">

*Message Id*

\(Only if for *Operation* the option *Delete Message* or *Update Message* is selected\)

</td>
<td valign="top">

The MessageID element is a GUID value that identifies the message in the queue.

</td>
</tr>
<tr>
<td valign="top">

*Max. Number Of Messages*

\(Only if for *Operation* the option *Get Messages and Peek Messages* is selected\)

</td>
<td valign="top">

The number of messages to retrieve from the queue, up to a maximum of 32. If you do not specify the number of messages, only one message is executed.

</td>
</tr>
<tr>
<td valign="top">

*Visibility Timeout \(in s\)*

\(Only if for *Operation* the option *Get Messages*, *Put Message*, or *Update Message* is selected\)

</td>
<td valign="top">

Specifies the visibility timeout value in seconds, up to a maximum of 120 seconds. The default value is 30 seconds.

</td>
</tr>
<tr>
<td valign="top">

*Prefix*

\(Only if for *Operation* the option *List Queues* is selected\)

</td>
<td valign="top">

Returns only queues with name that begins with the specified prefix.

</td>
</tr>
<tr>
<td valign="top">

*Page Size*

\(Only if for *Operation* the option *List Queues* is selected\)

</td>
<td valign="top">

Specify the page size to retrieve specific number of results. If you do not specify any page size, the server returns up to 5000 results.

</td>
</tr>
<tr>
<td valign="top">

*Process in Pages*

\(Only if for *Operation* the option *List Queues* is selected\)

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

*Number of Messages To Peek*

\(Only if for *Operation* the option *Peek Messages* is selected\)

</td>
<td valign="top">

The number of messages to peek from the queue up to a maximum of 32. If you do not specify the number of messages, only one message is peeked from the queue. This is optional.

</td>
</tr>
<tr>
<td valign="top">

*Message TTL*

\(Only if for *Operation* the option *Put Message* or *Update Message* is selected\)

</td>
<td valign="top">

Enter the time-to-live interval for the message, in seconds.

</td>
</tr>
<tr>
<td valign="top">

*Metadata Name: Value*

\(Only if for *Operation* the option *Set Queue Metadata* is selected\)

</td>
<td valign="top">

Enter one or more name value pair to set the metadata in the format `revenue:incometax` for one and `finance:incometax|finance:exciseduty` for more than one. If nothing is passed for name value pair, existing metadata is deleted.

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



<a name="loioe683a211578d4ef1820d0dd46ec3c80f__section_h43_dzh_3wb"/>

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

All Queue storage-related operations \(except *List Queue*\)

</td>
<td valign="top">

SAP\_AzureStorage\_Outbound\_QueueName

</td>
<td valign="top">

Property

</td>
<td valign="top">

Capture the queue name specified in the queue storage operations.

</td>
</tr>
<tr>
<td valign="top">

2

</td>
<td valign="top">

Get messages in queue

</td>
<td valign="top">

SAP\_AzureStorage\_DeliveryCount

</td>
<td valign="top">

Property

</td>
<td valign="top">

When a message is retrieved for the first time, its `DequeueCount` property is set to 1.

If it is not deleted and is subsequently retrieved again, the `DequeueCount` property is incremented.

</td>
</tr>
</table>

