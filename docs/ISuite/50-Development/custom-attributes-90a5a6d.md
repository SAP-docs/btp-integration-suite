<!-- loio90a5a6d2a75f4426964ec85c49faef88 -->

# Custom Attributes

This topic covers custom attributes and services, and guides you through creating, deleting, and updating custom attributes for application and products.

Custom attributes can be leveraged to influence the runtime behavior of the API proxy execution. It can be set at a product level or at an application level \(when application is created by admin on behalf of developer\). Custom attributes provide the flexibility to extend the functionality based on attribute value which can be set or read during the API proxy execution flow. These attributes can be accessed during an API call via the following policies: Verify API key, Access token, and Access entity.

For example, if you add attributes for your products, applications and use Verify API key or Access token verification policy in your flow variables, this can enforce any kind of runtime limitations and control functions.



<a name="loio90a5a6d2a75f4426964ec85c49faef88__section_hwy_cfn_xhb"/>

## Personas

**Personas**


<table>
<tr>
<th valign="top">

Role

</th>
<th valign="top">

Component

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

AuthGroup.API.Admin

</td>
<td valign="top">

Developer Hub

</td>
<td valign="top">

User assigned with this role can read, create, delete, and update custom attributes for application.

</td>
</tr>
<tr>
<td valign="top">

APIPortal.Administrator

</td>
<td valign="top">

API portal

</td>
<td valign="top">

User assigned with this role can read, create, delete, and update custom attributes for products

</td>
</tr>
</table>



<a name="loio90a5a6d2a75f4426964ec85c49faef88__section_vsy_dfn_xhb"/>

## Limits

**Limits**


<table>
<tr>
<th valign="top">

Attribute

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Custom attribute name size

</td>
<td valign="top">

255 characters

</td>
</tr>
<tr>
<td valign="top">

Custom attribute value size

</td>
<td valign="top">

1024 characters

</td>
</tr>
<tr>
<td valign="top">

Number of custom attributes permitted

</td>
<td valign="top">

18

</td>
</tr>
</table>



<a name="loio90a5a6d2a75f4426964ec85c49faef88__section_tly_2fn_xhb"/>

## Sample Payload

Sample payload to create a custom attribute

-   Url: https://<consumer API-Portal host\>:<port\>/apiportal/api/1.0/Management.svc/APIProducts HTTP/1.1
-   Method: POST
-   Content type: application/JSON
-   If you are in the Cloud Foundry environment, fetch the bearer token:

    -   Service url: https://<consumer API-Portal host\>/apiportal/api/1.0/Management.svc/APIProducts HTTP/1.1
    -   Method: HEAD
    -   Request Header: Authorization:Bearer <Token for API access\>
    -   Response: bearer-token value

    To know how to retrieve this token, see [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).


> ### Sample Code:  
> ```
> 
> {
>   "name": "SampleProduct",
>   "version": "1",
>   "isPublished": false,
>   "status_code": "PUBLISHED",
>   "title": "SampleProduct",
>   "description": "SampleProduct",
>   "isRestricted": false,
>   "scope": "",
>   "quotaCount": null,
>   "quotaInterval": null,
>   "quotaTimeUnit": null,
>   "additionalProperties": [
>     {
>       "entityId": "SampleProduct",
>       "name": "key1",
>       "value": "val1"
>     },
>     {
>       "entityId": "SampleProduct",
>       "name": "key2",
>       "value": "val2"
>     }
>   ],
>   "apiProxies": [
>     {
>       "__metadata": {
>         "uri": "APIProxies(name='SampleAPI')"
>       }
>     }
>   ],
>   "apiResources": [],
>   "__metadata": {
>     "type": "apiportal.APIProduct"
> 	}
> }
> 
> ```

Sample payload to create a custom attribute \(batch call\)

> ### Sample Code:  
> ```
> 
> Content-Type: application/http
> Content-Transfer-Encoding: binary
> 
> PUT APIProducts(name='SampleProduct') HTTP/1.1
> Request Header: x-csrf-token: <value>
> Accept-Language: en-US
> Accept: application/json
> MaxDataServiceVersion: 2.0
> DataServiceVersion: 2.0
> Content-Type: application/json
> Content-Length: 234
> 
> {"name":"SampleProduct","title":"SampleProduct","scope":"","description":"<p>SampleProduct</p>","version":"1","status_code":"PUBLISHED","isRestricted":false,"isPublished":true,"quotaCount":-99,"quotaInterval":-99,"quotaTimeUnit":null}
> 
> --changeset
> 
> Content-Type: application/http
> Content-Transfer-Encoding: binary
> 
> POST APIProductAdditionalProperties HTTP/1.1
> x-csrf-token: fetch
> Accept-Language: en-US
> Accept: application/json
> MaxDataServiceVersion: 2.0
> DataServiceVersion: 2.0
> Content-Type: application/json
> Content-Length: 60
> 
> {"entityId": "SampleProduct","name": "key3","value": "val3"}
> 
> ```

Sample payload to update a custom attribute \(batch call\)

> ### Sample Code:  
> ```
> 
> Content-Type: multipart/mixed; boundary=changeset_9c02-68be-2f72
> 
> --changeset
> Content-Type: application/http
> Content-Transfer-Encoding: binary
> 
> PUT APIProducts(name='SampleProduct') HTTP/1.1
> Request Header: x-csrf-token: <value>
> Accept-Language: en-US
> Accept: application/json
> MaxDataServiceVersion: 2.0
> DataServiceVersion: 2.0
> Content-Type: application/json
> Content-Length: 234
> 
> {"name":"SampleProduct","title":"SampleProduct","scope":"","description":"<p>SampleProduct</p>","version":"1","status_code":"PUBLISHED","isRestricted":false,"isPublished":true,"quotaCount":-99,"quotaInterval":-99,"quotaTimeUnit":null}
> 
> --changeset
> Content-Type: application/http
> Content-Transfer-Encoding: binary
> 
> PUT APIProductAdditionalProperties(entityId='SampleProduct',name='key3') HTTP/1.1
> x-csrf-token: <value>
> Accept-Language: en-US
> Accept: application/json
> MaxDataServiceVersion: 2.0
> DataServiceVersion: 2.0
> Content-Type: application/json
> Content-Length: 14
> 
> {"value":"vx"}
> 
> ```

Sample payload to delete a custom attribute \(batch call\)

-   Url: https://<consumer API-Portal host\>:<port\>/apiportal/api/1.0/Management.svc/$batch HTTP/1.1
-   Method: POST
-   Content type: application/JSON
-   Request Header: Authorization:Bearer <Token for API access\> \(for Cloud Foundry environment\)

    To know how to retrieve this token, see [Accessing API Management APIs Programmatically](../accessing-api-management-apis-programmatically-24a2c37.md).


> ### Sample Code:  
> ```
> 
> Content-Type: multipart/mixed; boundary=changeset_9c02-68be-2f72
> 
> --changeset
> Content-Type: application/http
> l
> Content-Transfer-Encoding: binary
> 
> PUT APIProducts(name='SampleProduct') HTTP/1.1
> x-csrf-token: Fetch
> Accept-Language: en-US
> Accept: application/json
> MaxDataServiceVersion: 2.0
> DataServiceVersion: 2.0
> Content-Type: application/json
> Content-Length: 234
> 
> {"name":"SampleProduct","title":"SampleProduct","scope":"","description":"<p>SampleProduct</p>","version":"1","status_code":"PUBLISHED","isRestricted":false,"isPublished":true,"quotaCount":-99,"quotaInterval":-99,"quotaTimeUnit":null}
> 
> --changeset
> Content-Type: application/http
> Content-Transfer-Encoding: binary
> 
> PUT APIProductAdditionalProperties(entityId='SampleProduct',name='key3') HTTP/1.1
> x-csrf-token: fetch
> Accept-Language: en-US
> Accept: application/json
> MaxDataServiceVersion: 2.0
> DataServiceVersion: 2.0
> Content-Type: application/json
> Content-Length: 14
> 
> {"value":"vx"}
> 
> ```

Sample payload to create a custom attribute \(application\)

-   Url: https://<consumer Dev-Portal host\>:<port\>/odata/1.0/data.svc/APIMgmt.Applications HTTP/1.1
-   Method: POST
-   Content type: application/JSON
-   If you are in the Cloud Foundry environment, fetch the bearer token:

    -   Service url: https://<consumer Dev-Portal host\>/odata/1.0/data.svc/APIMgmt.Applications HTTP/1.1
    -   Method: HEAD
    -   Request Header: Authorization:Bearer <Token for API access\>
    -   Response: bearer-token value

    To know how to retrieve this token, see [Accessing Developer Hub APIs Programmatically](../accessing-developer-hub-apis-programmatically-dabee6e.md).


> ### Sample Code:  
> ```
> 
> {
>     "id": "00000000000000000000000000000000",
>     "version": "1",
>     "title": "<AppName>",
>               "developer_id": "b",
>     "ToSubscriptions": [
>         {
>             "ToAPIProduct": [
>                 {
>                     "__metadata": {
>                         "uri": "APIMgmt.APIProducts('<ProdName>')"
>                     }
>                 }
>             ],
>             "id": "00000000000000000000000000000000"
>         }
>     ],
>     "ToAttributes": [
>         {
>              "name": "<AttributeName>",
>             "value": "<Attributevalue>",
>             "entityType": "Applications",
>             "entityId": "0000000"
>         },{
>              "name": "<AttributeName>",
>             "value": "<Attributevalue>",
>             "entityType": "Applications",
>             "entityId": "0000000"
>         },{
>             "name": "<AttributeName>",
>             "value": "<Attributevalue>",
>             "entityType": "Applications",
>             "entityId": "0000000"
>         }
>     ]
> }
> 
> 
> 
> ```

Sample payload to create a custom attribute via navigation \(application\)

-   Url: https://<consumer Dev-Portal host\>:<port\>/odata/1.0/data.svc/APIMgmt.Applications\(<application\_id\>\)/ToAttributes
-   Method: POST
-   Content type: application/JSON
-   If you are in the Cloud Foundry environment, fetch the bearer token:

    -   Service url: https://<consumer Dev-Portal host\>/odata/1.0/data.svc/APIMgmt.Applications\(<application\_id\>\)/ToAttributes
    -   Method: HEAD
    -   Request Header: Authorization:Bearer <Token for API access\>
    -   Response: bearer-token value

    To know how to retrieve this token, see [Accessing Developer Hub APIs Programmatically](../accessing-developer-hub-apis-programmatically-dabee6e.md).


> ### Sample Code:  
> ```
> 
> {
>             "name": "<AttributeName>",
>             "value": "<Attributevalue>",
>             "entityType": "Applications",
>             "entityId": "0000000"
>         }
> 
> 
> 
> 
> ```

Sample payload to update a custom attribute \(application\)

-   Url: https://<consumer Dev-Portal host\>:<port\>/odata/1.0/data.svc/APIMgmt.Attributes\(name=<attribute\_name\>,entityId=<application\_id\>,entityType='Applications'\)
-   Method: PUT
-   Content type: application/JSON
-   Request Header: x-csrf-token: fetch

> ### Sample Code:  
> ```
> 
> {
>             "name": "<AttributeName>",
>             "value": "<Attributevalue_updated>",
>             "entityType": "Applications",
>             "entityId": "0000000"
>         }
> 
> 
> 
> 
> ```

Sample URL to delete a custom attribute \(application\)

-   Url: https://<consumer Dev-Portal host\>:<port\>/odata/1.0/data.svc/APIMgmt.Attributes\(name=<attribute\_name\>,entityId=<application\_id\>,entityType='Applications'\)
-   Method: DELETE
-   Content type: application/JSON
-   Request Header: x-csrf-token: fetch

**Related Information**  


[Add Custom Attributes to a Product](add-custom-attributes-to-a-product-e46a874.md "Add custom attributes to a product.")

