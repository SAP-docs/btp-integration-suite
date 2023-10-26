<!-- loiob90b0b5ffc01491d95edc06bfce00f8d -->

# Get Custom Header Properties

Get custom header properties for a dedicated message ID.



Perform the following call:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

Resource Path

</th>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

`​/MessageProcessingLogs('{MessageGuid}')​/CustomHeaderProperties` 

</td>
</tr>
</table>

You can set custom header properties in a Script step. After processing the integration flow, custom header properties are displayed in the *Monitor* application \(under *Monitor Message Processing*\). However, you can also use the OData API to retrieve custom header properties.

There's an integration flow design guideline that shows you how to set custom header properties using the Script step \(see [Use Custom Header Properties to Search for Message Processing Logs](use-custom-header-properties-to-search-for-message-processing-logs-d4b5839.md)\).

When you've deployed and processed this integration flow, the corresponding message processing log shows the custom header property `po_number` with a certain value.

Assume that the message ID is `ABCD-1234-XYZ`. To get the custom header property, send the following GET request:

`https://<host address>/api/v1/MessageProcessingLogs('ABCD-1234-XYZ')​/CustomHeaderProperties'`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

The response contains the following part:

```
<m:properties>
<d:Id>999</d:Id>
<d:Name>po_number</d:Name>
<d:Value>12345</d:Value>
</m:properties>
```

