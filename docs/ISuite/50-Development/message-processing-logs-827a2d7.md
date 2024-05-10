<!-- loio827a2d7e9c6f4866a1d6c0e647bcacd2 -->

# Message Processing Logs

Get an overview of the messages processed on a tenant and get the details for individual messages. The message processing log \(MPL\) stores data about the messages processed on a tenant. Furthermore, it stores information about the individual processing steps for each processed message.

You can access the OData API and find the basic operations at: [Message Processing Logs](https://api.sap.com/api/MessageProcessingLogs/resource)

This documentation provides additional information.



<a name="loio827a2d7e9c6f4866a1d6c0e647bcacd2__section_zz1_2lf_t4b"/>

## Entity Data Model

The following diagram shows how the entities related to `MessageProcessingLog` and `MessageStoreEntry` are related to each other:

![](images/OData_API_Entities_Messages_85a8f07.png)



<a name="loio827a2d7e9c6f4866a1d6c0e647bcacd2__section_bvh_n1x_k5b"/>

## Permissions

To authorize an API client to access the OData API:

Perform the steps described in: [Setting Up Inbound HTTP Connections \(for API Clients\)](../40-RemoteSystems/setting-up-inbound-http-connections-for-api-clients-8db3d51.md) 

Assign the following role template:

`MonitoringDataRead` \(see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md)\)

To access the ID Mapper, assign role template `MessageProcessingLocksRead`.



<a name="loio827a2d7e9c6f4866a1d6c0e647bcacd2__section_uvw_dlf_t4b"/>

## Resources



> ### Caution:  
> Note the following, if you plan to get message processing logs with status “Discarded”, using the OData API:
> 
> -   Discarded messages don’t contain error information.
> 
> -   Calling frequent queries, for error information, in discarded messages, can impose an unnecessary high load on the system.
> 
> Therefore, decide the usage for such specific queries, diligently.

****


<table>
<tr>
<th valign="top">

Resource

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Logs

</td>
<td valign="top">

Represents a message processing logs object.

More information:

-   [Monitor Message Processing](monitor-message-processing-314df3f.md)

-   [Message Status](message-status-733a57b.md)

-   [Message Processing Log](message-processing-log-b32f8cd.md)




</td>
</tr>
<tr>
<td valign="top">

Adapter Attributes

</td>
<td valign="top">

Represents adapter-specific attributes.

Each adapter has a defined set of attributes that are described for every adapter type as part of the adapter configuration.

The `AdapterId` property identifies the adapter that logs something \(the component ID of the adapter in the component metadata\). The `AdapterMessageId` property uniquely identifies a message in context of a particular adapter.

</td>
</tr>
<tr>
<td valign="top">

Attachments

</td>
<td valign="top">

Represents attachments of message processing logs.

> ### Note:  
> To be able to view attachments, you need the following role in the NEO environment :`esbmessagestorage.read`. In the Cloud Foundry environment, you need the role template `MessagePayloadsRead`\).



</td>
</tr>
<tr>
<td valign="top">

Custom Header Properties

</td>
<td valign="top">

Represents custom header properties of the message processing log.

> ### Caution:  
> **Restriction for the usage of `$orderby`**
> 
> Regarding the `$orderby` option with the `MessageProcessingLogCustomHeaderProperty` entity, `$orderby` supports only the combinations `$orderby=Name,Value` and `$orderby=Name desc,Value desc`. If you need additional options, we recommend that you implement these options on the client side.

More information: [Use Custom Header Properties to Search for Message Processing Logs](use-custom-header-properties-to-search-for-message-processing-logs-d4b5839.md)

</td>
</tr>
<tr>
<td valign="top">

Error Information

</td>
<td valign="top">

Represents error information for message processing logs.

</td>
</tr>
<tr>
<td valign="top">

ID Mapper

</td>
<td valign="top">

Allows you to get all target IDs for the given source ID \(stored in the ID mapper\) or to get all source IDs for the given target ID \(stored in the ID mapper\).

</td>
</tr>
<tr>
<td valign="top">

Idempotent Repository

</td>
<td valign="top">

Represents the idempotent repository.

> ### Note:  
> The `Idempotent Repository` resource of the `Message Processing Logs` API has been deprecated and replaced by a new one.

The idempotent repository contains information about files that have already been consumed from the connected server in scenarios where one or more of the following features are used: Aggregation step, FTP, adapter, JMS adapter, SFTP adapter, or XI adapter. Files that are stored in the idempotent repository can be identified by the file name. When Cloud Integration tries to process the file, the system can detect if the file has already been consumed \(based on its idempotent repository entry\) and that way can prevent it from being consumed a second time from the server.

More information:

-   [Define Aggregator](define-aggregator-aa23816.md)

-   [FTP Adapter](ftp-adapter-4464f89.md)

-   [JMS Adapter](jms-adapter-0993f2a.md)

-   [SFTP Adapter](sftp-adapter-e3dce88.md)

-   [XI Adapter](xi-adapter-8fedc92.md)


Certain values \(when indicated as `<hexalias>`\) need to be provided in hexadecimal notation. String characters are stored by the computer as numbers. When the hexadecimal notation is required, the text is to be provided not as decimal number but as a hexadecimal number instead. For example: The string `my alias` is expressed by the following decimal numbers: `109 121 32 97 108 105 97 115` because, according to the American Standard Code for Information Interchange \(ASCII \), the letter `m` is translated to the decimal number `109`, and so forth. If you convert each number to a hexadecimal number, you get: `6D 79 20 61 6C 69 61 73`. Note that `6D` is the hexadecimal representation of `109`, and so forth. If you want to specify `my alias` in an example request, enter `6D7920616C696173`.

</td>
</tr>
<tr>
<td valign="top">

External Logging \(only available in the Cloud Foundry environment.\)

</td>
<td valign="top">

Allows you to activate or deactivate external logging.

More information: [External Logging](external-logging-ad719c1.md)

</td>
</tr>
<tr>
<td valign="top">

Data Archiving \(only available in the Cloud Foundry environment.\)

</td>
<td valign="top">

Allows you to activate data archiving.

More information:[Archiving Data](archiving-data-bc71f88.md) 

</td>
</tr>
</table>

For general information about query options, see [Query Options](query-options-99f4b70.md).

> ### Note:  
> To access message processing logs through a user interface, you can use the *Monitor* application \(*Monitor Message Processing* section\).



<a name="loio827a2d7e9c6f4866a1d6c0e647bcacd2__section_wsk_33x_54b"/>

## Example Requests

You can find various example requests on SAP Business Accelerator Hub at [Message Stores](https://api.sap.com/api/MessageStore).

For more example requests, see [Message Processing Logs Example Requests](message-processing-logs-example-requests-27bc167.md).



To trigger the modifying actions \(POST, PUT, and DELETE\), you need to fetch a CSRF token first. You can do that in the following way: First, send a GET call to the API with a header `X-CSRF-Token` with the value `Fetch`. As a response, you get the value of the token in the header `X-CSRF-Token`. When sending the modifying request, add the header `X-CSRF-Token` with the token retrieved from the first call.



On SAP Business Accelerator Hub, you can test API calls against a sandbox tenant or against a custom tenant \(to be configured under *API Environment*\). If you want to perform an API call against your custom tenant using an HTTP client such like Postman, make sure that the request URL is composed in the following way:

`https://<host address>/api/v1/<relative resource path>`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

You can find the relative resource path for each operation on SAP Business Accelerator Hub.

**Related Information**  


[Monitor Message Processing](monitor-message-processing-314df3f.md "The message monitor provides an overview of the messages processed on a tenant and allows you to display the details for individual messages.")

