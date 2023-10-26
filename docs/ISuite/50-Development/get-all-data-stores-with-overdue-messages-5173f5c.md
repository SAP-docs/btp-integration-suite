<!-- loio5173f5c9af124c76bef0ee1aa5c57679 -->

# Get All Data Stores with Overdue Messages



To get data stores that contain overdue messages, perform the following call:


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

`​/DataStores?overdueonly=true` 

</td>
<td valign="top">

Gets all data stores that contain overdue messages.

</td>
</tr>
</table>

If `overdueonly` is set to `false` or not available, all data stores are shown.

For each retrieved data store entry,the response contains a part with the following structure:

```
<m:properties>
<d:DataStoreName>My_Datastore</d:DataStoreName>
<d:IntegrationFlow>My_Integration_Flow</d:IntegrationFlow>
<d:Type/>
<d:NumberOfMessages>19</d:NumberOfMessages>
<d:NumberOfOverdueMessages>19</d:NumberOfOverdueMessages>
</m:properties>
```

