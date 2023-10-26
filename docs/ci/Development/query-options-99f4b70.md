<!-- loio99f4b708b1e4474ebe8af1a653aa4c55 -->

# Query Options

Query options allow you to control the amount and order of the data that a data service returns for the resource identified by the URI.



## OData System Query Options Supported by the Cloud Integration API

OData system query options are provided by the OData framework and documented in detail in the OData specification at [http://www.odata.org/documentation/odata-version-2-0/uri-conventions](http://www.odata.org/documentation/odata-version-2-0/uri-conventions).

This section provides a summary of the supported query options.

> ### Caution:  
> Not all quer options listed below are always supported by each entity type of the Cloud Integration OData API.
> 
> For more information on the supported query options, check out the description of the individual resources on SAP Business Accelerator Hub.

**Supported System Query Options**


<table>
<tr>
<th valign="top">

System Query Option

</th>
<th valign="top">

... Does the Following

</th>
</tr>
<tr>
<td valign="top">

`$count` 

</td>
<td valign="top">

Returns the number of records according to the resource path section of the URI \(or, if a filter is applied, the number of records matching the filter\).

</td>
</tr>
<tr>
<td valign="top">

`$expand` 

</td>
<td valign="top">

Returns related entities for a given navigation property in line with the entities being retrieved.

For example, adding the query `$expand=AdapterAttributes` to an OData request addressing the `MessagingProcessingLog` entity returns adapter-specific attributes in line with the message processing log data.

</td>
</tr>
<tr>
<td valign="top">

`$filter` 

</td>
<td valign="top">

Returns a subset of records according to the resource path section of the URI\) and to the filter expression.

</td>
</tr>
<tr>
<td valign="top">

`$inlinecount` 

</td>
<td valign="top">

Specifies that the response contains a count of the number of records in the collection of entries identified by the resource path section of the URI.

</td>
</tr>
<tr>
<td valign="top">

`$metadata` 

</td>
<td valign="top">

Returns the data model \(which is the structure of all resources\).

</td>
</tr>
<tr>
<td valign="top">

`$orderby` 

</td>
<td valign="top">

Specifies an expression for determining which values are used to order the collection of records identified by the resource path section of the URI.

> ### Caution:  
> **Limitations for the usage of `$orderby`**
> 
> Regarding the `$orderby` option with the `MessageProcessingLogCustomHeaderProperty` entity, note the following: `$orderby` supports only the combinations: `$orderby=Name,Value` as well as `$orderby=Name desc,Value desc`. In case you need additional options, we recommend you to implement these at the client side.



</td>
</tr>
<tr>
<td valign="top">

`$select` 

</td>
<td valign="top">

Returns a limited set of information on the entities identified by the resource path section of the URI.

> ### Note:  
> Using the `$select` option can have a positive impact on the performance of a request.



</td>
</tr>
<tr>
<td valign="top">

`$skip` 

</td>
<td valign="top">

Identifies a subset of records \(according to the resource path section of the URI\), where the subset is defined by seeking n entries and selecting only the remaining entries \(starting with entry n+1\).

</td>
</tr>
<tr>
<td valign="top">

`$top` 

</td>
<td valign="top">

Identifies a subset of records \(according to the resource path section of the URI\), where the subset is defined by selecting only the first n items of the set.

</td>
</tr>
<tr>
<td valign="top">

`$value` 

</td>
<td valign="top">

When applied with the entity RuntimeArtifactErrorInformation, this query returns the error message in JSON format.

</td>
</tr>
</table>



## Filter System Query Option \($filter\)

Examples for the `$filter` query option:

> ### Caution:  
> The browser translates space characters to `%20`. If you paste a URL from this documentation to the browser, the OData call therefore works. The string `%20` is left out of the example URLs to make them easier to read.

-   `https://<tmn>/api/v1/MessageProcessingLogs?$filter=MessageGuid eq 'AFQaBF-k2zSgMgIYekzBzk07Bs-T'`

    Addresses the message processing log with the MessageGuid `AFQaBF-k2zSgMgIYekzBzk07Bs-T`. This is equivalent to the query `https://<tmn>/api/v1/MessageProcessingLogs('AFQaBF-k2zSgMgIYekzBzk07Bs-T')`.

-   `https://<tmn>/api/v1/MessageProcessingLogs?$filter=ApplicationMessageId eq 'applicationID'`

    Addresses all message processing logs with the ApplicationMessageId `applicationID`.

-   `https://<tmn>/api/v1/MessageProcessingLogs?$filter=LogEnd gt datetime'2014-09-01T00:00:00' and LogEnd lt datetime'2014-09-02T00:00:00'`

    Addresses all message processing logs with log end time between the two datetime literals `2014-09-01T00:00:00Z` and `2014-09-02T00:00:00`.

    Currently, parsing of time zone information in datetime literals is not supported. All datetime literals are interpreted as UTC \(Universal Time Coordinated\). Therefore, a zone offset cannot be interpreted. For example, a call with the following syntax will not be interpreted correctly: `https://<tmn>/api/v1/MessageProcessingLogs?$filter=LogEnd gt datetime'2014-09-01T00:00:00Z' and LogEnd lt datetime'2014-09-02T00:00:00Z'`.

-   `https://<tmn>/api/v1/MessageProcessingLogs?$filter=Status eq 'ERROR'`

    Returns all message processing logs, where the associated messages are in ERROR status.

-   `https://<tmn>/api/v1/MessageProcessingLogs?$filter=CorrelationId eq 'AbCd-jshkdgsz23jds-T'`

    Returns all messages that are correlated by the CorrelationId `AbCd-jshkdgsz23jds-T`.




## Server-Side Paging \($skiptoken System Query Option\)

The Cloud Integration API provides 1000 entries for a call maximum. This feature also protects the Cloud Integration runtime environment if unfiltered queries enforce the return of huge amount of data.

If a query returns more than 1000 entries, the response will contain a *Next* link, which can be used to initiate the return of the additional entries.

Example:

```
<feed …>
 <id><tmn>/api/v1/MessageProcessingLogs</id>
 <title type="text">MessageProcessingLogs</title>
 …
 <link href="https://<tmn>/api/v1/MessageProcessingLogs?$skiptoken=1000" rel="next" />
</feed>
```

