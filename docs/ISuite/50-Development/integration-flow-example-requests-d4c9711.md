<!-- loiod4c97116fdc14913b93d1a16768f67d8 -->

# Integration Flow Example Requests



You can use resource `IntegrationDesigntimeArtifacts` to read, download, create, upload, deploy, and delete integration flows.

This section provides various example requests and additional information. Also check out the following SAP Community blog: [Cloud Integration – Remote OData API’s for Integration Flows](https://blogs.sap.com/2018/07/06/cloud-integration-remote-odata-apis-for-integration-flows/).

> ### Note:  



<a name="loiod4c97116fdc14913b93d1a16768f67d8__section_wws_3k5_r4b"/>

## Update Integration Flow Name

To update an Integration flow name, and save as a draft, send the following call:


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

PUT

</td>
<td valign="top">

/IntegrationDesigntimeArtifacts\(Id='<integration flow ID\>',Version='active'\)

</td>
</tr>
</table>

To update an Integration flow with Id `My_Integration_Flow` with the new name `My Integration Flow New`, and save as a draft, send the following PUT request:

`https://<host address>/api/v1/IntegrationDesigntimeArtifacts(Id='My_Integration_Flow',Version='active')`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

Provide the following request body:

```
{
  "Name": "My Integration Flow New",
  "ArtifactContent": "UEsDBBQACAgIAER6clIAAAAAAAAAAA ........ vLnByb3BQSwUGAAAAAAYABgDWAQAA8xIAAAAA"
}
```

> ### Note:  
> For the `ArtifactContent` property, you need to provide the base64-encoded content of the integration flow bundle \(for example, of the zip file that contains the integration flow model\).
> 
> To get the integration flow Id, open the integration flow model and select the *General* tab \(*ID* field\).



<a name="loiod4c97116fdc14913b93d1a16768f67d8__section_ot2_c3q_z4b"/>

## Update Integration Flow with Specific Version

To copy an Integration flow with a new version, send the following call:


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

POST

</td>
<td valign="top">

/IntegrationDesigntimeArtifactSaveAsVersion?Id='<integration flow ID\>'&SaveAsVersion='<new version\>

</td>
</tr>
</table>

To save Integration flow with Id `My_Integration_Flow` to version `1.0.0`, send the following POST request:

`https://<host address>/api/v1/IntegrationDesigntimeArtifactSaveAsVersion?Id='My_Integration_Flow'&SaveAsVersion='1.0.0'`

> ### Note:  
> If you would like to update an integration flow artifact with a specific version, the *PUT* method must be executed first.



<a name="loiod4c97116fdc14913b93d1a16768f67d8__section_ll2_3qq_z4b"/>

## Update Integration Flow Configuration Parameters


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

PUT

</td>
<td valign="top">

/IntegrationDesigntimeArtifacts\(Id='\{Id\}',Version='\{Version\}'\)​/$links​/Configurations\('\{ParameterKey\}'\)

</td>
</tr>
</table>

Assume that you've an integration flow with an externalized parameter for the HTTPS sender adapter address. When defining the HTTPS adapter address as externalized parameter, you've given it the parameter name `endpoint_address` and the initial value `endpoint1`.

The figure shows the externalized parameter in the *Connection* tab of the HTTPS sender adapter.

![](images/Externalized_Parameter_Endpoint_Address_3cac7ab.png)

To change the value of the externalized parameter to `endpoint1`, send the following PUT request:

`https://<host address>/api/v1/IntegrationDesigntimeArtifacts(Id='My_Integration_Flow',Version='1.0.1')​/$links​/Configurations('endpoint_address')`

Provide the following request body:

```
{
  "ParameterValue": "/endpoint2",
  "DataType": "xsd:string"
}
```

You can also do a batch request, for example:

> ### Sample Code:  
> ```
> --batch_34fcd829-64e4-4139-b880-f24aa4ee9235
> Content-Type: multipart/mixed; boundary=changeset_5e8e492f-2e3f-490f-9629-a4cd82a7aafd
>  
> --changeset_5e8e492f-2e3f-490f-9629-a4cd82a7aafd
> Content-Type: application/http
> Content-Transfer-Encoding: binary
>  
> PUT IntegrationDesigntimeArtifacts(Id='TestingCustomScheduler',Version='1.0.3')/$links/Configurations('Receiver1_host_33') HTTP/1.1
> Accept: application/json
> Content-Type: application/json
>  
> {
> "ParameterKey" : "Receiver1_host_33",
> "ParameterValue" : "blr002",
> "DataType" : "xsd:string"
> }
>  
> --changeset_5e8e492f-2e3f-490f-9629-a4cd82a7aafd
> Content-Type: application/http
> Content-Transfer-Encoding: binary
>  
> PUT IntegrationDesigntimeArtifacts(Id='TestingCustomScheduler',Version='1.0.3')/$links/Configurations('Sender_host_14') HTTP/1.1
> Accept: application/json
> Content-Type: application/json
>  
> {
> "ParameterKey" : "Sender_host_14",
> "ParameterValue" : "wdfsp001",
> "DataType" : "xsd:string"
> }
>  
> --changeset_5e8e492f-2e3f-490f-9629-a4cd82a7aafd--
> --batch_34fcd829-64e4-4139-b880-f24aa4ee9235--
> ```



<a name="loiod4c97116fdc14913b93d1a16768f67d8__section_emt_qkr_z4b"/>

## Perform Multiple Operations on Resources

You can perform multiple operations on resources in a single call using a batch request:

> ### Sample Code:  
> ```
> 
> --batch_abc
> Content-Type: multipart/mixed; boundary=changeset_123
> 
> --changeset_123
> Content-Type: application/http
> Content-Transfer-Encoding: binary
> 
> POST IntegrationDesigntimeArtifacts(Id='ResourceViewTest',Version='1.0.1')/Resources HTTP/1.1
> Content-Type: application/json
> 
> {
>                "Name":"Convert1.xsl",
>                "ResourceType":"xslt",
> 				"ResourceContent":"<Base64 encoded content>"
> }
> 
> --changeset_123
> Content-Type: application/http
> Content-Transfer-Encoding: binary
> 
> POST IntegrationDesigntimeArtifacts(Id='ResourceViewTest',Version='1.0.1')/Resources HTTP/1.1
> Content-Type: application/json
> 
> {
>                "Name":"Convert2.xsl",
>                "ResourceType":"xslt",
> 				"ResourceContent":"<Base64 encoded content>"
> }
> 
> 
> --changeset_123--
> --batch_abc--
> ```

> ### Note:  
> The `Name` and `ResourceType` must not be null.
> 
> `ResourceContent` should be in base64-encoded format.

For more information, check out the following SAP Community blog: [Cloud Integration – Remote OData API’s for Integration Flows](https://blogs.sap.com/2018/07/06/cloud-integration-remote-odata-apis-for-integration-flows/).

