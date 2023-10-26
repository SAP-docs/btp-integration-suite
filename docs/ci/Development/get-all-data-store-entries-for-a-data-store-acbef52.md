<!-- loioacbef52d7ed14463901babc7888939a4 -->

# Get All Data Store Entries for a Data Store



To get data store entries of specific data store, perform the following call:


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

`​/DataStores(DataStoreName='<data store name>',IntegrationFlow='<integration flow ID>',Type='')/Entries` 

</td>
<td valign="top">

Gets all entries of a specific data store.

</td>
</tr>
</table>

To retrieve all data store entries of data store `MyDataStore` created by integration flow `MyIntegrationFlow`, perform the following request:

`https://<host address>/api/v1​/DataStores(DataStoreName='MyDataStore',IntegrationFlow='MyIntegrationFlow',Type='')/Entries`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

For each data store entry, the response contains a part with the following structure:

```
<m:properties>
            <d:Id>1234-abcd-7890-xyz</d:Id>
            <d:DataStoreName>MyDataStore</d:DataStoreName>
            <d:IntegrationFlow>MyIntegrationFlow</d:IntegrationFlow>
            <d:Type></d:Type>
            <d:Status>Waiting</d:Status>
            <d:MessageId>ABCD1234XYZ</d:MessageId>
            <d:DueAt>2021-07-08T09:15:05.837</d:DueAt>
            <d:CreatedAt>2021-07-06T09:15:05.837</d:CreatedAt>
            <d:RetainUntil>2021-08-05T09:15:05.837</d:RetainUntil>
</m:properties>
```

