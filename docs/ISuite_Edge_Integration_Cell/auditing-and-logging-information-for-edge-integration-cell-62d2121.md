<!-- loio62d2121ae0114b6494e094e77cb45f1f -->

# Auditing and Logging Information for Edge Integration Cell

Here you can find a list of the security events that are logged by Edge Integration Cell.



Edge Integration Cell stores audit log entries locally in the internal Kubernetes database, even when operating offline. When connectivity is restored, the system automatically replicates the entries to the cloud. After replication, the system deletes entries from the local databases.

For example, if an audit log is created at 1:00 PM and the system remains offline for four hours, you see the log entry recorded at 5:00 PM in the audit log viewer. This time reflects when the log was uploaded, not when it was generated.



> ### Caution:  
> Prolonged offline periods may result in significant local storage of audit logs. This storage can lead to database bloat, which may eventually cause the PostgreSQL database to become read-only. If PostgreSQL enters read-only mode, write operations such as MPL writes start to fail.

**Security and Audit Logs**


<table>
<tr>
<th valign="top">

Event grouping

</th>
<th valign="top">

What events are logged

</th>
<th valign="top">

How to identify related log events

</th>
<th valign="top">

Additional information

</th>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Delete data store entry

</td>
<td valign="top">

-   action: Delete

-   objectType: Message


Example:

Deletion of data store entry `126` of global data store `CustomerReviews` writes the following audit log event:

> ### Output Code:  
> ```
> {
>   "action": "Delete",
>   "objectType": "Message",
>   "objectId": "CustomerReviews/GLOBAL/126",
>   "attributes": {
>     "ids": "[126]",
>     "storeName": "CustomerReviews",
>     "id": "126"
>   },
>   "changedAttributes": {},
>   "customDetails": {
>     "agentGeneratedId": "generate-agent-id-here",
>     "ingestedByAgentTimestamp": "2021-06-29T15:22:30.135Z"
>   }
> }
> ```



</td>
<td valign="top">

[Managing Data Stores](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ac39f1d1bd2f427c97b3694e54370bda.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Delete data store

</td>
<td valign="top">

-   action: Delete

-   objectType: Message


Example:

Deletion of global data store `CustomerReviews` writes the following audit log event:

> ### Output Code:  
> ```
> {
>   "action": "Delete",
>   "objectType": "Message",
>   "objectId": "CustomerReviews/GLOBAL/ALL",
>   "attributes": {
>     "storeName": "CustomerReviews"
>   },
>   "changedAttributes": {},
>   "customDetails": {
>     "agentGeneratedId": "generate-agent-id-here",
>     "ingestedByAgentTimestamp": "2021-06-29T15:26:34.345Z"
>   }
> } 
> ```



</td>
<td valign="top">

[Managing Data Stores](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ac39f1d1bd2f427c97b3694e54370bda.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Download variable

</td>
<td valign="top">

-   action: Read

-   objectType: Message


Example:

Download of global variable `timestamp` writes the following audit log event:

> ### Output Code:  
> ```
> {
>   "action": "Read",
>   "objectType": "Message",
>   "objectId": "sap_global_store/GLOBAL/timestamp",
>   "attributes": {
>     "storeName": "sap_global_store",
>     "id": "timestamp"
>   },
>   "changedAttributes": {},
>   "customDetails": {
>     "agentGeneratedId": "generate-agent-id-here",
>     "ingestedByAgentTimestamp": "2021-06-30T09:53:31.226Z"
>   }
> }
> ```

Example:

Download of local variable `ProductId` \(related to integration flow `Write_Product_ID` writes the following audit log event:

> ### Output Code:  
> ```
> {
>   "action": "Read",
>   "objectType": "Message",
>   "objectId": "sap_global_store/Write_Product_ID/ProductId",
>   "attributes": {
>     "qualifier": "Write_Product_ID",
>     "storeName": "sap_global_store",
>     "id": "ProductId"
>   },
>   "changedAttributes": {},
>   "customDetails": {
>     "agentGeneratedId": "generate-agent-id-here",
>     "ingestedByAgentTimestamp": "2021-06-30T10:04:51.569Z"
>   }
> }
> ```



</td>
<td valign="top">

[Managing Variables](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ca93653ec211457190ff8466e42ff9cd.html "The Variables view allows you to monitor variables used in integration flows.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Delete variable

</td>
<td valign="top">

-   action: Delete

-   objectType: Variable


Example:

Deletion of global variable `timestamp` writes the following audit log event:

> ### Output Code:  
> ```
> {
>   "action": "Delete",
>   "objectType": "Variable",
>   "objectId": "sap_global_store/GLOBAL/timestamp",
>   "attributes": {
>     "ids": "[timestamp]",
>     "storeName": "sap_global_store",
>     "id": "timestamp"
>   },
>   "changedAttributes": {},
>   "customDetails": {
>     "agentGeneratedId": "generate-agent-id-here",
>     "ingestedByAgentTimestamp": "2021-06-30T09:56:48.985Z"
>   }
> }
> ```

Example:

Deletion of local variable `ProductId` \(related to integration flow `Write_Product_ID` writes the following audit log event:

> ### Output Code:  
> ```
> {
>   "action": "Delete",
>   "objectType": "Variable",
>   "objectId": "sap_global_store/Write_Product_ID/ProductId",
>   "attributes": {
>     "qualifier": "Write_Product_ID",
>     "ids": "[ProductId]",
>     "storeName": "sap_global_store",
>     "id": "ProductId"
>   },
>   "changedAttributes": {},
>   "customDetails": {
>     "agentGeneratedId": "generate-agent-id-here",
>     "ingestedByAgentTimestamp": "2021-06-30T10:08:27.385Z"
>   }
> } 
> ```



</td>
<td valign="top">

[Managing Variables](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/ca93653ec211457190ff8466e42ff9cd.html "The Variables view allows you to monitor variables used in integration flows.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Move messages to another queue

</td>
<td valign="top">

-   action: Move

-   objectType: Message Queue




</td>
<td valign="top">

[Managing Message Queues](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cdcce24f484a41c08ab46d12ab666451.html "You can monitor queues that are active for a tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Delete message queue

</td>
<td valign="top">

-   action: Delete

-   objectType: Message Queue


Example:

Deletion of message queue `MyQueue` writes the following audit log event:

> ### Output Code:  
> ```
> {
>   "action": "Delete",
>   "objectType": "Message Queue",
>   "objectId": "MyQueue",
>   "attributes": {},
>   "changedAttributes": {},
>   "customDetails": {
>     "agentGeneratedId": "generate-agent-id-here",
>     "ingestedByAgentTimestamp": "2021-06-30T10:26:08.601Z"
>   }
> }
> ```



</td>
<td valign="top">

[Managing Message Queues](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cdcce24f484a41c08ab46d12ab666451.html "You can monitor queues that are active for a tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Delete message from message queue

</td>
<td valign="top">

-   action: Delete

-   objectType: Message


Example:

Deletion of a message from message queue `MyQueue` writes the following audit log event:

> ### Output Code:  
> ```
> {
>   "action": "Delete",
>   "objectType": "Message",
>   "objectId": "ID:12345-abcde",
>   "attributes": {
>     "Queue": "MyQueue"
>   },
>   "changedAttributes": {},
>   "customDetails": {
>     "agentGeneratedId": "generate-agent-id-here",
>     "ingestedByAgentTimestamp": "2021-06-30T10:49:47.974Z"
>   }
> } 
> ```



</td>
<td valign="top">

[Managing Message Queues](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cdcce24f484a41c08ab46d12ab666451.html "You can monitor queues that are active for a tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Download message from message queue

</td>
<td valign="top">

-   action: Read

-   objectType: Message


Example:

Downloading a message from message queue `MyQueue` writes the following audit log event:

> ### Output Code:  
> ```
> {
>   "action": "Read",
>   "objectType": "Message",
>   "objectId": "ID:12345-abcde",
>   "attributes": {
>     "Queue": "MyQueue"
>   },
>   "changedAttributes": {},
>   "customDetails": {
>     "agentGeneratedId": "generate-agent-id-here",
>     "ingestedByAgentTimestamp": "2021-06-30T10:49:40.913Z"
>   }
> }
> ```



</td>
<td valign="top">

[Managing Message Queues](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cdcce24f484a41c08ab46d12ab666451.html "You can monitor queues that are active for a tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Manage stores

</td>
<td valign="top">

Retry message from message queue

</td>
<td valign="top">

-   action: Retry

-   objectType: Message




</td>
<td valign="top">

[Managing Message Queues](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/cdcce24f484a41c08ab46d12ab666451.html "You can monitor queues that are active for a tenant.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Message monitoring

</td>
<td valign="top">

Read / download message payload / header when monitoring integration flow with Trace log level

</td>
<td valign="top">

-   action: Read

-   objectType: Message Payload \(Trace\)


Example:

Reading the message payload writes the following audit log event:

> ### Output Code:  
> ```
> {
>   "action": "Read",
>   "objectType": "Message Payload (Trace)",
>   "objectId": "mplId\\1234-xyz;traceId\\abcd;stepId\\u003dEndEvent_2; Odata-Read",
>   "attributes": {
>     "runtime ID": "edgeintegrationcell",
>     "message": "Reading Content for Message Payload (Trace) with Id 1353"
>   },
>   "changedAttributes": {},
>   "customDetails": {
>     "agentGeneratedId": "generate-agent-id-here",
>     "ingestedByAgentTimestamp": "2021-07-05T10:09:35.531Z"
>   }
> }
> ```



</td>
<td valign="top">

[Monitor Message Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/314df3f8f4334dd8829c62e865cc6d02.html "The message monitor provides an overview of the messages processed on a tenant and allows you to display the details for individual messages.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Message monitoring

</td>
<td valign="top">

Read message processing log attachment

</td>
<td valign="top">

-   action: Read

-   objectType: MPL Attachment

-   > ### Output Code:  
    > ```
    > {
    >   "action": "Read",
    >   "objectType": "MPL Attachment",
    >   "objectId": "mplAtt-1234",
    >   "attributes": {
    >     "runtime ID": "edgeintegrationcell",
    >     "message": "Reading Content for MPL Attachment with Id mplAtt-1234"
    >   },
    >   "changedAttributes": {},
    >   "customDetails": {
    >     "agentGeneratedId": "generate-agent-id-here",
    >     "ingestedByAgentTimestamp": "2021-07-05T10:09:35.531Z"
    >   }
    > }
    > 
    > ```




</td>
<td valign="top">

[Monitor Message Processing](https://help.sap.com/viewer/9519789d5664487f8b9cd89eba514477/CLOUD/en-US/314df3f8f4334dd8829c62e865cc6d02.html "The message monitor provides an overview of the messages processed on a tenant and allows you to display the details for individual messages.") :arrow_upper_right: 

</td>
</tr>
</table>

**Related Information**  


[Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

[Audit Logging in the Neo Environment](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/02c39712c1064c96b37c1ea5bc9420dc.html)

[Auditing and Logging Information for Cloud Integration](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/CLOUD/en-US/d1c7bfe00b7c448ab56d7b4d454475f9.html "Here you can find a list of the security events that are logged by Cloud Integration.") :arrow_upper_right:

