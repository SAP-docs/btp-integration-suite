<!-- loio37e592e254fe4657a8ff1676ff8608ec -->

# OData

The Graph API follows the OData protocol; all payloads are JSON documents.

OData \(Open Data Protocol\) is an ISO/IEC-approved standard that defines a set of best practices for building and consuming RESTful APIs. OData helps you focus on your business logic while building RESTful APIs without having to worry about the various approaches to define request and response headers, status codes, HTTP methods, URL conventions, media types, payload formats, query options, and so forth. OData also provides guidance for tracking changes, defining functions/actions for reusable procedures, and sending asynchronous/batch requests.

OData RESTful APIs are easy to consume. What follows is a short introduction; see also our multipart tutorial series for an introduction to the Graph data protocol, and the reference material at [https://www.odata.org/](https://www.odata.org/).



## OData Resources

In OData, every request refers to a *resource*. A resource can be an entity, such as a sales order, a customer, or a bank account, or a subset of its attributes. For example, `GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v2/sap.graph/Product` returns the entire list of `Product` entities.

In many cases, you don't require a list, but a specific instance of an entity, for example the `Product` with the key \(identifier\) of 345, which can be accomplished by:

`GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v2/sap.graph/Product/345` 

or

`GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v2/sap.graph/Product('345')` 

Both requests are the same, and they retrieve the matching instance only. And `GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v2/sap.graph/Product/345/displayId` returns the single `displayId` attribute.

Using navigations, you can view additional connected resources or their attributes. For example, `GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v2/sap.graph/Product('345')/_division` results in the `Division` entity relevant to this `Product` entity instance.



<a name="loio37e592e254fe4657a8ff1676ff8608ec__section_pcw_sn5_ktb"/>

## Query Parameters

Where OData becomes interesting is through its usage of query parameters. The following is a brief introduction to the topic.



### Filtering: $filter

Graph API filtering follows the[OData filtering specifications](https://docs.oasis-open.org/odata/odata/v4.01/csprd06/part1-protocol/odata-v4.01-csprd06-part1-protocol.html#_Toc21423805). The initial step in retrieving data is to perform a `GET` request to a collection of resources, which can be a list of customers, a list of customer orders, or a list of customer quotes. In many cases, these lists can have extensive amounts of data, and filtering them means that you can get only the data that matches certain criteria.

To filter the result set of a query, the `$filter` URL parameter needs to be added with the filter string. Within this filter string, operators are used to construct the conditions. Depending on the entity type, there are specific fields and operators that can be used for filtering.

> ### Note:  
> This query parameter is only supported for top-level properties and not for a property of a contained \(nested\) entity.

For example, if the result set should only contain customer orders with a net amount below the value of 30,000 \(netAmount < 30000\), the following filter needs to be applied:

`netAmount lt 30000` 



### Supported Comparison Operators

Graph supports the following comparison operators:


<table>
<tr>
<th valign="top">

Operator

</th>
<th valign="top">

Sign

</th>
<th valign="top">

`$filter` Operator

</th>
</tr>
<tr>
<td valign="top">

Equals

</td>
<td valign="top">

=

</td>
<td valign="top">

`eq` 

</td>
</tr>
<tr>
<td valign="top">

Not equals

</td>
<td valign="top">

!=

</td>
<td valign="top">

`ne` 

</td>
</tr>
<tr>
<td valign="top">

Greater than

</td>
<td valign="top">

\>

</td>
<td valign="top">

`g`t

</td>
</tr>
<tr>
<td valign="top">

Greater than or equals

</td>
<td valign="top">

\>=

</td>
<td valign="top">

`ge` 

</td>
</tr>
<tr>
<td valign="top">

Less than

</td>
<td valign="top">

<

</td>
<td valign="top">

`lt` 

</td>
</tr>
<tr>
<td valign="top">

Less than or equals

</td>
<td valign="top">

<=

</td>
<td valign="top">

`le` 

</td>
</tr>
</table>

Example:

```json
GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.graph/SalesQuote?$filter=netAmount le 8400
```

This example filters for customer quotes that have a `netAmount` less than or equal to 8400.



### Using Logical Operators

Multiple statements can be combined into a larger filter condition, by applying one of the following logical operators:


<table>
<tr>
<th valign="top">

Logical Operator

</th>
<th valign="top">

`$filter` Operator

</th>
</tr>
<tr>
<td valign="top">

AND \(both need to be true\)

</td>
<td valign="top">

`and` 

</td>
</tr>
<tr>
<td valign="top">

OR \(at least one needs to be true\)

</td>
<td valign="top">

`or` 

</td>
</tr>
<tr>
<td valign="top">

NOT \(negate the following statement\)

</td>
<td valign="top">

`not`

</td>
</tr>
</table>

Example:

```json
GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.graph/SalesOrder?$filter=netAmount lt 15000 and orderDate lt 2017-01-01
```

> ### Note:  
> String values need to be escaped with single quotes.

Find more information about the logical operators in the official OData documentation [here](https://docs.oasis-open.org/odata/odata/v4.01/csprd06/part1-protocol/odata-v4.01-csprd06-part1-protocol.html#_Toc21423805).



### Projection of Results: `$select`

You can tell the Graph API to return only a subset of properties you need.

The projection of results is a standard OData query modifier and selected properties are specified via the `$select` query parameter.

To select only the properties that you need, use the `$select` query parameter in combination with one or more top-level properties of an entity.

> ### Note:  
> This query parameter is only supported for top-level properties and not for nested properties.

Example:

To return only the `id` and `lastName` properties of Employee entities, specify the following in the `$select` query parameter:

```json
GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.graph/Employee?$select=id,lastName
```

Response:

```json
{
  "@odata.context": "$metadata#Employee(id,lastName)",
  "value": [
    { "id": "1018",
      "lastName": "Lou"
    },
    { "id": "1000031",
      "lastName": "Sprengel"
    },
    { "id": "1000032",
      "lastName": "Rupieper"
    },
...
}
```

> ### Note:  
> **The resulting `Employee` entities are only represented by the two specified properties.**



### Advanced Filtering Using Any Support

Lambda can be used to filter for entities along attributes found in compositions. For example, you can filter out all `CorporateAccounts` where any of the addresses meet a given criteria . This can be a `CorporateAccount` that is expanded to its numerous addresses. For more information about Any support, see [OData.org: More Any and All](https://www.odata.org/blog/more-any-and-all/).

**Example** 

Fetch all `ServiceRequestCollection` where ANY item in `ServiceRequestParty` matches filter

> ### Sample Code:  
> ```json
> /sap.c4c/ServiceRequestCollection?$expand=ServiceRequestParty&$filter=ServiceRequestParty/any(d:d/PartyID eq 'some Party ID')
> ```

Response:

> ### Sample Code:  
> ```json
> 
> {
>   "@odata.context": "$metadata#ServiceRequestCollection(ServiceRequestParty())",
>   "value": [
>     {
>       "@odata.etag": "W/\"datetimeoffset'2022-04-27T15%3A29%3A28.3907090Z'\"",
>       "ObjectID": "00163EA813131EDCB1C7A87A004DEEAF",
>       "ProcessingTypeCodeText": "Service Request",
>       "Name": "Monarch bike enquiry",
>       "ResolvedOnDateTime": "2020-04-09T11:11:08Z",
>       "CreatedBy": "Prof. Dr. Graph Tester",
>       "LastChangedBy": "Prof. Dr. Graph Tester",
>       ...
>       "ServiceRequestParty": [
>         {
>           "ObjectID": "00163EA813131EDCB1C7A87A004D4EAF",
>           "ParentObjectID": "00163EA813131EDCB1C7A87A004DEEAF",
>           "PartyID": "some Party ID",
>           "PartyUUID": null,
>           "RoleCategoryCodeText": "Buyer Party",
>           "RoleCode": "1001",
>           "RoleCodeText": "Account",
>           "Main": true,
>           "EntityLastChangedOn": "2022-04-27T15:29:28.390Z",
>           ...
>         }
>       ]
>     }
>   ]
> }
> ```



### Result Expansion: $expand

The SAP API Explorer expands most of the query results. But when using the `$select` query parameter, result set expansion can be used to also include related entities, which would otherwise not be included in the result set. This can be achieved by using the OData `$expand` query parameter and specifying which properties to expand.

**Example**

> ### Sample Code:  
> ```json
> GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/dev/sap.graph/SalesOrder?$select=id,orderDate,netAmount
> ```

**Response**

> ### Sample Code:  
> ```json
> {
>   "@odata.context": "$metadata#SalesOrder(id,orderDate,netAmount)",
>   "value": [
>     {
>       "id": "00163e37-bedf-1ed9-betaad-514c152dcc55",
>       "orderDate": null,
>       "netAmount": 15
>     },
>     {
>       "id": "00163e37-bedf-1ed9-betaad-e818d2bc2dba",
>       "orderDate": null,
>       "netAmount": 0
>     },
>     {
>       "id": "00163e37-bedf-1ed9-betaad-f41808420dea",
>       "orderDate": null,
>       "netAmount": 15
>     }
>   ...
>   ]
> }
> ```

**Example**

To see the items and the status of these customer orders, use `$expand=items,processingStatus` in the request:

> ### Sample Code:  
> ```json
> GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.graph/SalesOrder?$select=id,orderDate,netAmount&$expand=items,processingStatus
> ```

**Response**

> ### Sample Code:  
> ```json
> {
>   "@odata.context": "$metadata#CustomerOrder(id,orderDate,netAmount,items(),processingStatus())",
>   "value": [
>     {
>       "id": "00163e37-bedf-1ed9-betaad-514c152dcc55",
>       "orderDate": null,
>       "netAmount": 15,
>       "processingStatus": {
>         "name": "Open",
>         "descr": null,
>         "code": "A"
>       },
>       "items": [
>         {
>           "text": "Managed Spare Part (Non-stock)",
>           "quantity": 1,
>           "id": "10",
>           ...,
>           "quantityUnit": {
>             "code": "C62"
>           }
>         }
>       ]
>     },
>     {
>       "id": "00163e37-bedf-1ed9-betaad-e818d2bc2dba",
>       ...
>     }
>   ]
> }
> ```



### Pagination

To allow easier consumption of the result data, pagination can be used. This means, that the overall result set is split into multiple smaller parts, such as the amount of data that can be displayed on a single page. Client-side pagination uses the `$stop` and `$skip` parameters.

The pagination concept follows the OData specifications as well. The OData API provides several pagination options for query results.

-   `$top` - this parameter controls how many results are returned. You can add the desired number, such as`$top5` - this displays only the top five results.
-   `$skip` - this option skips the desired number of results. Combined with the `$top` parameter, you can narrow the results even more.

You can use `$skip` or `$top` in combination with other query parameters to narrow down the results even more.

**Example**

> ### Sample Code:  
> ```json
> GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/bdg/sap.graph/Product?$select=id&$top=5
> ```

**Response**

Returns only the first five products from the list, and only the ID of the product is displayed:

> ### Sample Code:  
> ```json
> {
>   "@odata.context": "$metadata#Product(id)",
>   "value": [
>     { "id": "014e75cf-71c6-4965-ba5d-cb3fa1055ec1" },
>     { "id": "01574be9-f73d-4954-a777-2324b6bb7989" },
>     { "id": "02676ec1-7504-4993-a0e6-8272a026cef1" },
>     { "id": "050e151e-2bb2-44a2-bf3f-7bd08abeta92f7" },
>     { "id": "0dad9cc7-d1f7-4192-b041-a57d871864ad" },
>   ]
> }
> ```

For server-side pagination you can use the `$skiptoken` parameter.



### Etag

Etags \(entity tags\) are versions to track down changes that occur for a given entity. This means that if the entity data changes then the Etag value changes as well.

Etags are used to allow clients to do caching and to easily check if something has changed.

**Example** 

This tracks metadata changes.

> ### Sample Code:  
> ```
> @odata.metadataEtag
> ```



### `$count`

With the `$count` parameter you can see how many results your query has in total, even if less are shown due to pagination. To do this, you need to set `?$count=true`.

**Example**

> ### Sample Code:  
> ```json
> GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.graph/Product?$count=true
> ```

**Response**

> ### Sample Code:  
> ```json
> {
>   "@odata.context": "$metadata#Product",
>   "@odata.count": 89,
>   "value": [...],
>   "@odata.nextLink": "Product?$count=true&$skiptoken=20"
> }
> ```

The entire result set contains 89 product entries, but only the first 20 entries are displayed as part of the query response due to the server-side paging that Graph has set.



### `$orderby`

With the `$orderby` option, you can order the entries in your list in ascending or descending order \(`asc` or `desc`\) with all the attributes that track the date or a specific point in time, such as `createdAt`, `deliveryDate`, `modifiedAt`, and so on. Or you can order the list alphabetically with attributes such as `name`.

**Example**

> ### Sample Code:  
> ```json
> GET https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.graph/Product?$orderby=name asc
> ```

**Response**

This operation displays the list of products ordered alphabetically by name in ascending order.



<a name="loio37e592e254fe4657a8ff1676ff8608ec__section_njv_gfp_5sb"/>

## Create, Read, Update, and Delete \(CRUD\) Operations

Graph allows you to create, read, update and delete data, considering any existing access rights and data source boundaries, using the following standard HTTP methods:


<table>
<tr>
<th valign="top">

HTTP Verb

</th>
<th valign="top">

CRUD

</th>
</tr>
<tr>
<td valign="top">

POST

</td>
<td valign="top">

Create

</td>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

Read

</td>
</tr>
<tr>
<td valign="top">

PUT

</td>
<td valign="top">

Update/Replace

</td>
</tr>
<tr>
<td valign="top">

PATCH

</td>
<td valign="top">

Update/Modify

</td>
</tr>
<tr>
<td valign="top">

DELETE

</td>
<td valign="top">

Delete

</td>
</tr>
</table>

As GET is the most common of the CRUD operations, the following examples show you how to create \(POST\) an entity and update \(PATCH\).

> ### Sample Code:  
> ```json
> POST https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.s4/A_BusinessPartner
> 
> {
>   "Supplier": "",
>   "AcademicTitle": "",
>   "AuthorizationGroup": "",
>   "BusinessPartnerCategory": "1",
>   "CorrespondenceLanguage": "EN",
>   "FirstName": "Daniel",
>   "FormOfAddress": "",
>   "Industry": "",
>   "InternationalLocationNumber1": "0",
>   "InternationalLocationNumber2": "0",
>   "IsFemale": false,
>   "IsMale": true,
>   "IsNaturalPerson": "1",
>   "IsSexUnknown": false,
>   "Language": "DE",
>   "LastName": "Lou",
>   "LegalForm": "",
>   "OrganizationBPName1": "",
>   "OrganizationBPName2": "",
>   "OrganizationBPName3": "",
>   "OrganizationBPName4": "",
>   "OrganizationFoundationDate": null,
>   "OrganizationLiquidationDate": null,
>   "SearchTerm1": "SIGCUSTBP01",
>   "SearchTerm2": "",
>   "AdditionalLastName": "",
>   "BirthDate": null,
>   "BusinessPartnerBirthDateStatus": "",
>   "BusinessPartnerBirthplaceName": "",
>   "BusinessPartnerDeathDate": null,
>   "BusinessPartnerIsBlocked": false,
>   "BusinessPartnerType": "",
>   "GroupBusinessPartnerName1": "",
>   "GroupBusinessPartnerName2": "",
>   "IndependentAddressID": "",
>   "InternationalLocationNumber3": "0",
>   "MiddleName": "",
>   "NameCountry": "",
>   "NameFormat": "",
>   "PersonFullName": "",
>   "IsMarkedForArchiving": false,
>   "BusinessPartnerIDByExtSystem": "",
>   "BusinessPartnerPrintFormat": "",
>   "BusinessPartnerOccupation": "",
>   "BusPartMaritalStatus": "",
>   "BusPartNationality": "",
>   "BusinessPartnerBirthName": "",
>   "BusinessPartnerSupplementName": "",
>   "NaturalPersonEmployerName": "",
>   "LastNamePrefix": "",
>   "LastNameSecondPrefix": "",
>   "Initials": "",
>   "TradingPartner": ""
> }
> ```

If this operation is run successfully, you'll receive a 201 response and the result is that you created your first `BusinessPartner`.

**Example**

This shows how to add the birth date to the `BusinessPartner` object that was created in the previous request.

> ### Sample Code:  
> ```json
> PATCH https://is-demo-kjsbzgso-57c46d694dff43deabe46431e745b4ef.a.integration.cloud.sap/graph/api/v1/sap.s4/A_BusinessPartner/<id of entity to update>
> 
> {
>   "BirthDate": "1987-12-06"
> ```

**Response**

After adding the birth date, the result is as follows:

> ### Sample Code:  
> ```json
> {
>   "BusinessPartner": "<id of entity to update>",
>   "Supplier": "",
>   "AcademicTitle": "",
>   "AuthorizationGroup": "",
>   "BusinessPartnerCategory": "1",
>   "CorrespondenceLanguage": "EN",
>   "FirstName": "Daniel",
>   "FormOfAddress": "",
>   "Industry": "",
>   "InternationalLocationNumber1": "0",
>   "InternationalLocationNumber2": "0",
>   "IsFemale": false,
>   "IsMale": true,
>   "IsNaturalPerson": "1",
>   "IsSexUnknown": false,
>   "Language": "DE",
>   "LastName": "Lou",
>   "LegalForm": "",
>   "OrganizationBPName1": "",
>   "OrganizationBPName2": "",
>   "OrganizationBPName3": "",
>   "OrganizationBPName4": "",
>   "OrganizationFoundationDate": null,
>   "OrganizationLiquidationDate": null,
>   "SearchTerm1": "SIGCUSTBP01",
>   "SearchTerm2": "",
>   "AdditionalLastName": "",
>   "BirthDate": "1987-12-06",
>   "BusinessPartnerBirthDateStatus": "",
>   "BusinessPartnerBirthplaceName": "",
>   "BusinessPartnerDeathDate": null,
>   "BusinessPartnerIsBlocked": false,
>   "BusinessPartnerType": "",
>   "GroupBusinessPartnerName1": "",
>   "GroupBusinessPartnerName2": "",
>   "IndependentAddressID": "",
>   "InternationalLocationNumber3": "0",
>   "MiddleName": "",
>   "NameCountry": "",
>   "NameFormat": "",
>   "PersonFullName": "",
>   "IsMarkedForArchiving": false,
>   "BusinessPartnerIDByExtSystem": "",
>   "BusinessPartnerPrintFormat": "",
>   "BusinessPartnerOccupation": "",
>   "BusPartMaritalStatus": "",
>   "BusPartNationality": "",
>   "BusinessPartnerBirthName": "",
>   "BusinessPartnerSupplementName": "",
>   "NaturalPersonEmployerName": "",
>   "LastNamePrefix": "",
>   "LastNameSecondPrefix": "",
>   "Initials": "",
>   "TradingPartner": ""
> }
> ```

