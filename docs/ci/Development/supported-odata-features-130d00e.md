<!-- loio130d00edf4e8484e9bb8e1bb5d5ffe8a -->

# Supported OData Features

> ### Remember:  
> This component or some of its features might not be available in the Cloud Foundry environment. For more information on the limitations, see SAP Note [2752867](https://me.sap.com/notes/2752867).



The following operations are supported when developing an OData API in the Cloud Integration web application:

****


<table>
<tr>
<th valign="top">

OData Operation

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Create

</td>
<td valign="top">

Maps to HTTP POST method

</td>
</tr>
<tr>
<td valign="top">

Read

</td>
<td valign="top">

Maps to HTTP GET method

</td>
</tr>
<tr>
<td valign="top">

Update

</td>
<td valign="top">

Maps to HTTP PUT method

</td>
</tr>
<tr>
<td valign="top">

Delete

</td>
<td valign="top">

Maps to HTTP DELETE method

</td>
</tr>
<tr>
<td valign="top">

Query

</td>
<td valign="top">

Maps to HTTP GET method

</td>
</tr>
<tr>
<td valign="top">

Function Imports

</td>
<td valign="top">

Custom operations that can be invoked through HTTP GET or POST method.

> ### Note:  
> Currently, Cloud Integration supports only function imports that can be invoked through HTTP GET method.



</td>
</tr>
</table>

The OData API supports the data types for the uploaded metadata file \(EDMX\) defined [here](https://www.odata.org/documentation/odata-version-2-0/overview/) except:

-   Null

-   Edm.Single

-   Edm.DateTimeOffset


The following system query options are supported when calling an OData API developed in the Cloud Integration web application:

****


<table>
<tr>
<th valign="top">

OData System Query Option

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

$select

</td>
<td valign="top">

Specifies a subset of properties to return.

</td>
</tr>
<tr>
<td valign="top">

$top

</td>
<td valign="top">

Determines the maximum number of records to return.

</td>
</tr>
<tr>
<td valign="top">

$skip

</td>
<td valign="top">

Sets the number of records to skip before it retrieves records in a collection.

</td>
</tr>
<tr>
<td valign="top">

$filter

</td>
<td valign="top">

Specifies an expression or function that must evaluate to **true** for a record to be returned in the collection.

</td>
</tr>
<tr>
<td valign="top">

$count

</td>
<td valign="top">

Returns the number of records in a collection.

</td>
</tr>
<tr>
<td valign="top">

$orderby

</td>
<td valign="top">

Determines which values are used to order a collection of records.

</td>
</tr>
<tr>
<td valign="top">

$expand

</td>
<td valign="top">

Specifies that related records must be retrieved in line with the record or collection being retrieved. For example, you can use $expand to retrieve a customer and all orders placed by that customer in a single query.

</td>
</tr>
<tr>
<td valign="top">

$inlinecount

</td>
<td valign="top">

Specifies that the response must contain a number of records in the collection of entries identified by the resource path section of the URI.

Message property must be an Integer value. This value is returned in the response.

</td>
</tr>
<tr>
<td valign="top">

$format

</td>
<td valign="top">

Specifies that a response to the request must be in the format specified by this query option.

</td>
</tr>
</table>

> ### Note:  
> The system query options $select and $count are supported out of the box. You do not have to write a script to enable functionality for these system query options.

> ### Note:  
> **Server side pagination support**:
> 
> To enable serverside pagination with next link in response, set the message header `skipToken` with a value for the skiptoken.
> 
> > ### Example:  
> > `skipToken : 20` adds the next link in response as ***<link href=”Products?$skiptoken=20″ rel=”next”/\>***

**Related Information**  


[Developing an OData API Project](developing-an-odata-api-project-d961654.md "")

