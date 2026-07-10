<!-- loio7de679dd0e5e41c0873195d31eb3d020 -->

# Get All Data Store Entries for a Specific Message ID



To get data store entries that are associated with a specific message ID, perform the following call:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
<th valign="top">

Purpose

</th>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

`​/DataStoreEntries?messageid=<messageId>` 

</td>
<td valign="top">

Gets all data store entries for a given message ID.

</td>
</tr>
</table>

To retrieve all data store entries created during the message processing run identified by the message ID `ABCD1234XYZ`, perform the following request:

`https://<host address>/api/v1​/DataStoreEntries?messageid=ABCD1234XYZ`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

For each data store entry, the response contains a part with the following structure:

```
<m:properties>
<d:Id>1234-abcd-7890-xyz</d:Id>
<d:DataStoreName>My_Datastore</d:DataStoreName>
<d:IntegrationFlow>My_Integration_Flow</d:IntegrationFlow>
<d:Type/>
<d:Status>Overdue</d:Status>
<d:MessageId>ABCD1234XYZ</d:MessageId>
<d:DueAt>2021-02-06T14:24:24.016</d:DueAt>
<d:CreatedAt>2021-02-04T14:24:24.016</d:CreatedAt>
<d:RetainUntil>2021-05-05T14:24:24.016</d:RetainUntil>
</m:properties>

```

