<!-- loiob5b27c92045746acb8127c56faef1246 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configuration API Specification and Usage

The Graph Configuration API is an OData API endpoint.

The API is available using the following URL:

```
{region-specific host}/configuration/v1/sap.graph
```

> ### Note:  
> You can get the region-specific host from the service bindings.

All the available resources are listed under the URL. You can get the OData metadata by using the `“/configuration/v1/sap.graph/$metadata”` path.



<a name="loiob5b27c92045746acb8127c56faef1246__section_zv3_jkd_k1c"/>

## Graph API Configuration Resource

A business data graph is represented by a Graph Configuration API resource. The resource URL is as follows:

```
{region-specific host}/configuration/v1/sap.graph/GraphConfiguration
```



<a name="loiob5b27c92045746acb8127c56faef1246__section_ulh_4kd_k1c"/>

## Graph Configuration Properties


<table>
<tr>
<th valign="top">

Name

</th>
<th valign="top">

Required

</th>
<th valign="top">

Data Type

</th>
<th valign="top">

Read-Only

</th>
</tr>
<tr>
<td valign="top">

`businessDataGraphIdentifier` 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

String

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`schemaVersion` 

</td>
<td valign="top">

 

</td>
<td valign="top">

String

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`graphModelVersion` 

</td>
<td valign="top">

 

</td>
<td valign="top">

String

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`effectiveGraphModelVersion` 

</td>
<td valign="top">

 

</td>
<td valign="top">

String

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
</tr>
<tr>
<td valign="top">

`exclude` 

</td>
<td valign="top">

 

</td>
<td valign="top">

Array of Strings

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`dataSources` 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

Array of data sources

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`locatingPolicy` 

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
<td valign="top">

Array of locating policies

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`statusDetails` 

</td>
<td valign="top">

 

</td>
<td valign="top">

String

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
</tr>
<tr>
<td valign="top">

`logMessages` 

</td>
<td valign="top">

 

</td>
<td valign="top">

Array of log messages

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
</tr>
<tr>
<td valign="top">

`extensions` 

</td>
<td valign="top">

 

</td>
<td valign="top">

Array of Strings

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`status` 

</td>
<td valign="top">

 

</td>
<td valign="top">

String

</td>
<td valign="top">

<span style="color:#2B7D2B;"><span class="SAP-icons-V5"></span></span> 

</td>
</tr>
</table>

For more information about the Graph configuration properties, see [Business Data Graph Configuration File](business-data-graph-configuration-file-e93d38c.md).

> ### Note:  
> The `status` property shows the state of the business data graph during design time. This means that when you create a business data graph, the status is `PROCESSING`. From that point, you need to poll the Graph Configuration API resource to check if the processing of the business data graph was successful. If an error occurs during the process, the status is changed to `FAILED`. If the process is successful, the status is changed to `DEPLOYMENT_INITIATED`. When this status is reached, the business data graph is deployed. You can also find the relevant logs in the `logMessages` property.



<a name="loiob5b27c92045746acb8127c56faef1246__section_rkl_51p_k1c"/>

## Examples of Graph Configuration Usage

> ### Note:  
> The following examples for a Graph instance used the EU10 region-specific host.



### Example 1: Create a Simple Business Data Graph with Two Data Sources

> ### Sample Code:  
> ```
> {
>     "businessDataGraphIdentifier": "my-bdg",
>     "dataSources": [
>         {
>             "name": "my.custom",
>             "services": [
>                 {
>                     "destinationName": "csv-frequent-flyer",
>                     "path": ""
>                 }
>             ],
>             "namespace": "my.custom"
>         },
>         {
>             "name": "s4",
>             "services": [
>                 {
>                     "destinationName": "s4-business-partner",
>                     "path": ""
>                 }
>             ]
>         }
>     ],
>     "locatingPolicy": {
>         "cues": [],
>         "rules": [
>             {
>                 "name": "sap.s4.*",
>                 "leading": "s4",
>                 "local": []
>             },
>             {
>                 "name": "sap.graph.*",
>                 "leading": "s4"
>             },
>             {
>                 "name": "my.custom.*",
>                 "leading": "my.custom"
>             }
>         ]
>     }
> }
> ```

POST: `https://eu10.graph.sap/configuration/v1/sap.graph/GraphConfiguration`

Response: 201 with the created business data graph configuration.



### Example 2: Get a Business Data Graph

GET: `https://eu10.graph.sap/configuration/v1/sap.graph/GraphConfiguration/{BDG-Id}`

Response: 200 with the corresponding business data graph configuration.



### Example 3: Update Existing Business Data Graph

PATCH: `https://eu10.graph.sap/configuration/v1/sap.graph/GraphConfiguration/{BDG-Id}`

Response: 200 with the updated business data graph configuration.

