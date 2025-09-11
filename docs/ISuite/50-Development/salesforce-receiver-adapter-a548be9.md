<!-- loioa548be9518704e4aad7d02963f3f7dec -->

# Salesforce Receiver Adapter

You configure the receiver channel with the Salesforce adapter to enable your tenant to send data to Salesforce customer relationship management \(CRM\) platform.

Once you’ve created a receiver channel and selected the Salesforce receiver adapter, you can configure its parameters by referring the following description:

The General tab shows general information such as the adapter type, its direction \(receiver\), the transport protocol, and the message protocol.

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

*Address*

</td>
<td valign="top">

Specify the recipient's endpoint URL, the Salesforce login base URL, for user authentication.

</td>
</tr>
<tr>
<td valign="top">

*Basic Credential Name*

</td>
<td valign="top">

Specify the name of the **User Credentials** artifact that contains the credentials for basic authentication. This refers to the username-password pair used in authentication to Salesforce. This property enables the system to fetch the User Credential security material deployed in your SAP Cloud Integration tenant.

</td>
</tr>
<tr>
<td valign="top">

*Security Token Alias*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the security token needed to connect to the Salesforce. This property enables the system to fetch the Security Token from the security material deployed in your SAP Cloud Integration tenant. This field can be omitted if your IP is allow listed on Salesforce.

</td>
</tr>
<tr>
<td valign="top">

*OAuth Credential Name*

</td>
<td valign="top">

Specify the name of the OAuth Credentials artifact that contains the Salesforce’s OAuth Consumer key-client secret pair. This property enables the system to retrieve the OAuth security material deployed in your SAP Cloud Integration tenant.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the connection timeout in milliseconds. The timeout allows you to control the wait time until the connection is established​.

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the response timeout in milliseconds. The timeout allows you to control the wait time until the message is received.

</td>
</tr>
<tr>
<td valign="top">

*Lazy Authentication*

</td>
<td valign="top">

Specify the use of Lazy Authentication when logging in. When enabled, the OAuth token retrieval or generation isn’t done until the first API call.

</td>
</tr>
</table>

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

*Type*

</td>
<td valign="top">

Specify the category of API that is used to interact with Salesforce. Select one of the following types:

-   *Apex Call*
-   *Event Processing*
-   *REST*
-   *REST Bulk* 
-   *REST Bulk 2.0* 
-   *REST Place Order* 



</td>
</tr>
<tr>
<td valign="top" colspan="2">

If you select *Apex Call*

</td>
</tr>
<tr>
<td valign="top">

*Method Name*

</td>
<td valign="top">

Select the Apex Rest Method used to specify the Method annotation in the Apex Class

</td>
</tr>
<tr>
<td valign="top">

*Resource Relative URL*

</td>
<td valign="top">

Specify the relative URL of Apex requestURI. The relative path is the part of the requestURI after the instance URL and needs to start with /. Example: if the request URL is https://instance.salesforce.com/services/apexrest/Account/123, the relative URL will be "/services/apexrest/ Account/123". Note that the dynamic headers and properties are supported. Example: "/services/apexrest/$\{property.SObject\}/$ \{property.sobjectld\}".

</td>
</tr>
<tr>
<td valign="top">

*HTTP Protocol*

</td>
<td valign="top">

Select the HTTP protocol version for Patch operations, the recommended option for use is "Default".

</td>
</tr>
<tr>
<td valign="top" colspan="2">

If you select *Event Processing*

</td>
</tr>
<tr>
<td valign="top">

*Event Type*

</td>
<td valign="top">

Specifies the category of the Event to be retrieved from Salesforce. Possible values include PushTopic Events, Platform Events, Change Data Capture Events, and Generic events.

</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the Operation to be performed:

-   *Event - Polling*



</td>
</tr>
<tr>
<td valign="top">

*Replay ID*

</td>
<td valign="top">

Specifies the Replay Id which is populated by Salesforce and refers to the position of the Event in the event stream. Note that the Replay Id values are not guaranteed to be contiguous for consecutive events. By specifying the value of the Replay Id, the integration flow retrieves events that are within the retention window and that have followed the specified Replay Id. Example: In case a Replay Id 200 is specified, the integration flow receives all messages with a Replay Id greater than 200. This field supports dynamic properties and a header.

</td>
</tr>
<tr>
<td valign="top">

*Channel Name*

</td>
<td valign="top">

Consists of a Topic name preceded with a prefix. For instance, a PushTopic can be prefixed with “/topic/”. Example: /topic/MyPushTopic. Note that the names are case sensitive.

</td>
</tr>
<tr>
<td valign="top">

*API Version*

</td>
<td valign="top">

Specify the version of the API used for calling the Salesforce.

</td>
</tr>
<tr>
<td valign="top">

*Wait Time \(in ms\)*

</td>
<td valign="top">

Specifies how long the Receiver Adapter connects to Salesforce to retrieve events. The Adapter automatically disconnects after this period.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Events Count*

</td>
<td valign="top">

Specifies the maximum number of Events that will be collected in a single run.

</td>
</tr>
<tr>
<td valign="top">

*Invalid Replay Id Approach*

</td>
<td valign="top">

Select the approach to be applied when an invalid replayld has been found.

</td>
</tr>
<tr>
<td valign="top">

*Max Buffer Size \(in bytes\)*

</td>
<td valign="top">

Specify the maximum permissible capacity \(in bytes\) of the response content, which may contain many messages.

> ### Note:  
> It is recommended to keep a minimum value of 10 MB \(which is the default value\) as suggested by Salesforce and only increase it for a high volume scenario.



</td>
</tr>
<tr>
<td valign="top" colspan="2">

If you select *REST*

</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Specify the basic CRUD and Query operations. To access and exchange data with Salesforce, you can choose among the following operation options:

-   Metadata - All

-   Metadata - Basic

-   Metadata - Comprehensive

-   Other - Get REST API Versions

-   Other - Get REST Resource Endpoints

-   Salesforce Object - Create

-   Salesforce Object - Delete

-   Salesforce Object - Delete with External ID

-   Salesforce Object - Get

-   Salesforce Object - Get Blob

-   Salesforce Object - Get with External ID

-   Salesforce Object - Update

-   Salesforce Object - Upsert with External ID

-   Salesforce Objects - Composite

-   SOQL - Execute Query

-   SOQL - Execute Query for More Results

-   SOSL - Search Resource




</td>
</tr>
<tr>
<td valign="top">

*Salesforce Object*

\(if the operation is Metadata – Basic, Metadata – Comprehensive, Salesforce Object - Create, Salesforce Object - Delete, Salesforce Object - Delete with External ID, Salesforce Object - Get, Salesforce Object - Get Blob, Salesforce Object - Get with External ID, Salesforce Object - Update, Salesforce Object - Upsert with External ID\)

</td>
<td valign="top">

Specify the name of the SObject in Salesforce to perform the operation on. For example: Account, Lead, Order, and so on. You can select Custom in case any custom SObject is involved.

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Object ID*

\(if the operation is Salesforce Object - Get, Salesforce Object - Get Blob, Salesforce Object - Update\)

</td>
<td valign="top">

Specify the unique ID that represents a specific record of the SObject that you specified in the Salesforce Object field.

</td>
</tr>
<tr>
<td valign="top">

*External ID Name*

\(if the operation is Salesforce Object – Get with External ID, Salesforce Object – Delete with External ID, Salesforce Object – Upsert with External ID\)

</td>
<td valign="top">

Specify the name that refers to an External ID. The ID field maintained in Salesforce as part of the SObject. For example, *SAPReferenceNumber\_\_c*.

</td>
</tr>
<tr>
<td valign="top">

*External ID Value*

\(if the operation is Salesforce Object – Get with External ID, Salesforce Object – Delete with External ID, Salesforce Object – Upsert with External ID\)

</td>
<td valign="top">

Specify the value for the External ID field in Salesforce as part of the SObject. For example, in an integration scenario between Salesforce and SAP ECC, you can use SAPReferenceNumber\_\_c as the External ID Name and 10005210032 as the External ID Value to identify that record. 

</td>
</tr>
<tr>
<td valign="top">

*Filter Fields*

\(if the operation is Salesforce Object - Get, Salesforce object - Get with External ID\)

</td>
<td valign="top">

Specify a table to enter a selection of filtered fields to be returned in the response. This is a way to limit which fields of the response should be returned. Each field can be added in a separate row of the table.

</td>
</tr>
<tr>
<td valign="top">

*Payload Format*

</td>
<td valign="top">

Specify the format of the request message to be sent to and response to be returned from Salesforce. Possible values include Application/XML and Application/JSON. The default value is Application/XML.

</td>
</tr>
<tr>
<td valign="top">

*Pretty Print*

</td>
<td valign="top">

Specify the option to Pretty Print the response payload. This feature formats the XML payload or JSON payload, to improve its readability.

</td>
</tr>
<tr>
<td valign="top">

*SOQL Query*

\(if the operation is SOQL – Execute Query\)

</td>
<td valign="top">

Specify the SOQL Query to be executed in Salesforce and that returns the result matching the query.

</td>
</tr>
<tr>
<td valign="top">

*Next Records URL*

\(if the operation is SOQL – Execute Query for More Results\)

</td>
<td valign="top">

Specify the URL to retrieve more records. In case more records are returned in the response of the SOQL Query operation, specify this property to retrieve the next batch of records.

</td>
</tr>
<tr>
<td valign="top">

*SOSL Search*

\(if the operation is SOSL – Search Resource\)

</td>
<td valign="top">

Specify the SOSL Search that is executed in Salesforce and returns the result matching the query.

</td>
</tr>
<tr>
<td valign="top">

*Request Payload Format*

</td>
<td valign="top">

Select the request payload format in the API.

</td>
</tr>
<tr>
<td valign="top">

*Response Payload Format*

</td>
<td valign="top">

Select the response payload format in the API.

</td>
</tr>
<tr>
<td valign="top">

*Auto Pagination*

</td>
<td valign="top">

Eanble to retrieve all records in case query result has more than one page.

</td>
</tr>
<tr>
<td valign="top">

*Include deleted records in query result*

</td>
<td valign="top">

Enable to include records that have been deleted or merged as part of the results.

</td>
</tr>
<tr>
<td valign="top">

*Enable Batch Processing*

</td>
<td valign="top">

Enable to allow multiple round trips to Salesforce in case the number of records exceeds the allowed limit \(200 records\) for the SObject Collections. Note that this feature does not support allOrNone=true.

</td>
</tr>
<tr>
<td valign="top">

*Enable Lookup Query*

</td>
<td valign="top">

Enable this property to automatically resolve queries in the request body.

> ### Note:  
> Enable Query Lookup supports only XML Payload Format.



</td>
</tr>
<tr>
<td valign="top">

*Treat all XML Payload Values as String*

</td>
<td valign="top">

Select to treat all the values in the XML payload as string before sending it to Salesforce.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

If you select *REST Bulk*

</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Specify the Bulk operation. To access and exchange data with Salesforce via Bulk processing, you can choose among the following operation options:

-   Job - Get

-   Job - Abort

-   Job - Create

-   Job – Get all Batches

-   Job – Close

-   Batch - Get

-   Batch - Create

-   Batch – Get Request

-   Batch – Get Result

-   Batch Query – Create

-   Batch Query – Get Result

-   Batch Query – Get Result IDs




</td>
</tr>
<tr>
<td valign="top">

*Job ID*

\(if the operation is Job - Get, Job - Abort, Job – Get all Batches, Job – Close, Batch - Get, Batch - Create, Batch – Get Request, Batch – Get Result, Batch Query – Create, Batch Query – Get Result, Batch Query – Get Result IDs\)

</td>
<td valign="top">

Specify the ID of the job being monitored.

</td>
</tr>
<tr>
<td valign="top">

*Batch ID*

\(if the operation is Batch – Get, Batch – Get Request, Batch – Get Result, Batch Query – Get Result, Batch Query – Get Result IDs\)

</td>
<td valign="top">

Specify the ID of the batch being processed.

</td>
</tr>
<tr>
<td valign="top">

*Content Type*

\(if the operation is Batch – Create\)

</td>
<td valign="top">

Specify the type of content of the batches. You can select from CSV, JSON, XML, ZIP CSV, ZIP JSON, and ZIP XML. This implies that a batch can be created in CSV, JSON, and XML and its ZIP equivalent.

</td>
</tr>
<tr>
<td valign="top">

*Result ID*

\(if the operation is Batch Query – Get Result\)

</td>
<td valign="top">

Specify the Result ID in the response to the batch result list request. For Bulk API Query operations, you can use this Result ID to retrieve the results of a Bulk Query.

</td>
</tr>
<tr>
<td valign="top">

*SOQL Query*

\(if the operation is Batch Query – Create\)

</td>
<td valign="top">

Specify the SOQL Query to be executed in Salesforce and that will return the results matching the query.

</td>
</tr>
<tr>
<td valign="top">

*Data from Attachment*

</td>
<td valign="top">

Enable to accept body from attachment.

</td>
</tr>
<tr>
<td valign="top">

*Handle XML Null Values*

</td>
<td valign="top">

Enable to use null values in the payload to nullify properties in Salesforce.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

If you select *REST Bulk 2.0*

</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Specify the operation to be performed.

-   Job - Abort

-   Job - Close

-   Job - Create

-   Job - Delete

-   Job - Get

-   Job - Get All Jobs

-   Job Query - Abort

-   Job Query - Create

-   Job Query - Delete

-   Job Query - Get All Query Jobs

-   Job Query - Get Information

-   Job Query - Get Results




</td>
</tr>
<tr>
<td valign="top">

*Advanced Job Properties*

</td>
<td valign="top">

Enable to specify all the advanced properties in the adapter instead of in the payload.

</td>
</tr>
<tr>
<td valign="top">

*Job Result Type*

</td>
<td valign="top">

Select the type of records to be retrieved for the selected job ID.

</td>
</tr>
<tr>
<td valign="top">

*Enable PkChunking*

</td>
<td valign="top">

Enable to automatic primary key \(PK\) chunking. PK chunking splits bulk queries on large tables into chunks based on the record IDs, or primary keys, of the queried records.

</td>
</tr>
<tr>
<td valign="top">

*Job Type*

</td>
<td valign="top">

Select to filter based on the job type.

</td>
</tr>
<tr>
<td valign="top">

*Query Locator*

</td>
<td valign="top">

Specify a querylocator with a locator value to get a specific set of job results.

</td>
</tr>
<tr>
<td valign="top">

*Query Job ID*

</td>
<td valign="top">

Specify the job id of the query.

</td>
</tr>
<tr>
<td valign="top">

*Max Records*

</td>
<td valign="top">

Specify the maximum number of records the adapter is expected to receive from Salesforce per page to prevent a timeout.Example: 2000.

> ### Note:  
> If working with a very large number of query results, then there is a possibility of timeout before receiving all the data from Salesforce.



</td>
</tr>
<tr>
<td valign="top" colspan="2">

If you select *REST Place Order*

</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Specify the Place Order operation. The Place Order API supports 8 operations that retrieve or push data to Salesforce. These operations are categorized in to three groups known as Account, Contract, and Order:

-   Account - Add Contracts and Orders

-   Account - Add Orders

-   Contract - Add Orders

-   Contract - Filter Details

-   Contract - Get

-   Order - Add Products

-   Order - Filter Details

-   Order - Get




</td>
</tr>
<tr>
<td valign="top">

*Contract ID*

\(if the operation is Contract – Add Orders, Contract – Get, Contract - Filter Details\)

</td>
<td valign="top">

Specify the Contract ID of the Contract that is processed. Contracts act as the parent Salesforce Object and Orders as the child Salesforce Object.

</td>
</tr>
<tr>
<td valign="top">

*Order ID*

\(if the operation is Order – Add Products, Order – Get, Order – Filter Details\)

</td>
<td valign="top">

Specify the Order ID of the Order that is being processed. Similar to the Salesforce Object ID, this is the unique identifier that can be found in the last part of the URL in the Order record view in the Salesforce Console.

</td>
</tr>
<tr>
<td valign="top">

*Filter Name*

\(if the operation is Contract – Filter Details, Order – Filter Details\)

</td>
<td valign="top">

Specify the name of the child object field to be used for filtering purposes. For illustration, imagine that you would like to filter all orders that below to a contract and that have a particular status code.

</td>
</tr>
<tr>
<td valign="top">

*Filter Value*

\(if the operation is Contract – Filter Details, Order – Filter Details\)

</td>
<td valign="top">

Specify the value of the child object field used for filtering purposes. Together, the Filter Name and Filter Value can help you to retrieve specific fields of an Order or a Contract.

</td>
</tr>
</table>

