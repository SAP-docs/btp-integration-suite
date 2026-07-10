<!-- loio8b86912eb31a482cbb81e9fa618b0655 -->

# Get Single Data Store Entry



To get a single data store entry, perform the following call:


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

`​/DataStoreEntries(Id='{EntryId}',DataStoreName='{DataStoreName}',IntegrationFlow='{IntegrationFlowName}',Type='{Type}')` 

</td>
<td valign="top">

Gets a single data store entry.

</td>
</tr>
</table>

To get a single entry with entry ID `1234-abcd-4567-xyz` from the local data store `MyStore`, perform the following GET request:

`https://<host address>/api/v1​/DataStoreEntries(Id='{1234-abcd-4567-xyz}',DataStoreName='{DataStoreName}',IntegrationFlow='{MyIntegrationFlow}',Type='{Type}')`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

The response contains an entry with the following elements:

```
<m:properties>
        <d:Id>1234-abcd-4567-xyz</d:Id>
        <d:DataStoreName>MyStore</d:DataStoreName>
        <d:IntegrationFlow>MyIntegrationFlow</d:IntegrationFlow>
        <d:Type></d:Type>
        <d:Status>Waiting</d:Status>
        <d:MessageId>ABCD_XYZ</d:MessageId>
        <d:DueAt>2021-04-16T13:53:35.28</d:DueAt>
        <d:CreatedAt>2021-04-14T13:53:35.28</d:CreatedAt>
        <d:RetainUntil>2021-07-13T13:53:35.28</d:RetainUntil>
</m:properties>
```

