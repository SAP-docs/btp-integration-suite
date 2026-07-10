<!-- loio71cb2649102d4677b0482c74d0bb8081 -->

# Get Message Processing Logs for a Dedicated Time Period

Get the message processing logs for all completed messages processed within a dedicated time period.



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

`/MessageProcessingLogs?$inlinecount=allpages&$filter=Status eq 'COMPLETED' and LogStart gt datetime'{beginning of time period}' and LogEnd lt datetime'{end of time period}'` 

</td>
</tr>
</table>

Assume that you like to get all message processing logs for completed messages processed in the time period of February 1 to February 14 2021.

Send the following GET request:

`https://<host address>/api/v1/MessageProcessingLogs?$inlinecount=allpages&$filter=Status eq 'COMPLETED' and LogStart gt datetime'2021-02-01T00:00:00' and LogEnd lt datetime'2021-02-14T00:00:00'`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

