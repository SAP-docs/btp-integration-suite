<!-- loio49c733687c80415aa5b67d58cda99dbf -->

# Get Runtime Status of Deployed Integration Flow

Get the runtime status of a currently deployed integration flow.

Perform three subsequent calls:


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

POST

</td>
<td valign="top">

`/DeployIntegrationDesigntimeArtifact?Id='<bundleId>'&Version='<version>'` 

</td>
<td valign="top">

Get taskID of currently deployed integration flow.

</td>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

`/BuildAndDeployStatus(TaskId='<taskid>’)` 

</td>
<td valign="top">

Get build and deploy status of currently deployed integration flow.

</td>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

`/IntegrationRuntimeArtifacts('<bundleId>')` 

</td>
<td valign="top">

If build and deploy status is Success, get runtime status of currently deployed integration flow.

</td>
</tr>
</table>

To set up such a sequence of requests, you can design an integration flow with the following sequence of OData API calls:

![](images/Get_Runtime_Status_of_Deployed_Integration_Flow_0e404a3.png)

The integration flow performs the following steps:

1.  An HTTP client \(for example, Postman\) calls the integration flow. The request body contains the Id and version of the integration flow for which you like to request the runtime status.

    A content modifier \(not shown in the diagram\) stores Id and version as exchange properties \(let's give them the names: `bundleId` and `version`\).

2.  The first Request Reply step calls the Cloud Integration OData API through an HTTP receiver adapter \(for the tenant on which the integration flow in question is deployed\).

    Cloud Integration calls the OData API with the following URL and query:

    `https://<host address>/api/v1/DeployIntegrationDesigntimeArtifact?Id='${property.buldleId}'&Version='${property.version}'` \(POST method\)

    The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

    The OData API sends back a response that contains the taskId.

    A content modifier \(not shown in the diagram\) stores the taskId as exchange property.

3.  The second Request Reply step calls the OData API \(through an HTTP receiver adapter\) with the following URL and query:

    `https://<host address>/api/v1/BuildAndDeployStatus(TaskId='${property.taskId}')`

    The OData API provides a response with the following content:

    ```
    <m:properties>
          <d:TaskId>abcd-1234-5678-xyz</d:TaskId>
          <d:Status>Success</d:Status>
    </m:properties>
    ```

    A content modifier \(not shown in the diagram\) stores the status as exchange property.

4.  A routing step leads to two different routes, depending in the value of the status:

    -   The default route leads to a message end event.

    -   The route taken when the status provided by the OData API is `Success` contains another Request Reply step that calls the OData API through the HTTP receiver adapter. It specifies a call with the following URL and query:

        `https://<host address>/api/v1/IntegrationRuntimeArtifacts('${property.buldleId}')`

        The response contains attributes for the retrieved integration flow.

        The `Status` attribute contains the actual runtime status.

        The integration flow sends back the runtime status to the HTTP client.



**Related Information**  


[Integration Content](integration-content-d1679a8.md "Manage integration artifacts for your tenant.")

[Runtime Status](runtime-status-c14a7b1.md "Indicates if a deployed artifact is ready to operate.")

