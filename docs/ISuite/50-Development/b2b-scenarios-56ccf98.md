<!-- loio56ccf98b864144219ae32aff6035b23f -->

# B2B Scenarios

Use the `B2B Scenarios OData API` to access and manage data related to inter-enterprise business integration scenarios.

With this API, you can securely query business documents and this way support efficient data exchange and business process collaboration between enterprises.

Find the OData API and the basic operations at [B2B Scenarios](https://hub.sap.com/api/B2BScenarios/overview) on SAP Business Accelerator Hub. Note that the *Try out* feature is currently unavailable.



<a name="loio56ccf98b864144219ae32aff6035b23f__section_ept_fch_zgc"/>

## Permissions

To authorize an API client to access the OData API, perform the steps described in [Setting Up Inbound HTTP Connections \(for API Clients\)](../40-RemoteSystems/setting-up-inbound-http-connections-for-api-clients-8db3d51.md) in the Cloud Foundry environment.

Then, assign the following role templates:

-   `MonitoringDataRead`

-   `B2bInterchangeOperate`

-   `B2bInterchangePayloadRead`

-   `B2bInterchangeRead`


See also [Tasks and Permissions](https://help.sap.com/docs/integration-suite/sap-integration-suite/tasks-and-permissions-556d5575d4b0483e85d4f3251f21d0ec).



<a name="loio56ccf98b864144219ae32aff6035b23f__section_brb_gch_zgc"/>

## Resources

The following resources are included in the API:

****


<table>
<tr>
<th valign="top">

Resource

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Orphaned Interchanges

</td>
<td valign="top">

Retrieve a list of all orphaned interchanges available in the system.

</td>
</tr>
<tr>
<td valign="top">

Business Documents

</td>
<td valign="top">

Retrieve a list of all inter-enterprise business documents available in the system.

</td>
</tr>
<tr>
<td valign="top">

Business Document Additional Field

</td>
<td valign="top">

Retrieve business document notes.

</td>
</tr>
<tr>
<td valign="top">

Sender Technical Acknowledgment

</td>
<td valign="top">

Retrieve sender technical acknowledgment.

</td>
</tr>
<tr>
<td valign="top">

Receiver Technical Acknowledgment

</td>
<td valign="top">

Retrieve receiver technical acknowledgment.

</td>
</tr>
<tr>
<td valign="top">

Sender Functional Acknowledgment

</td>
<td valign="top">

Retrieve sender functional acknowledgment .

</td>
</tr>
<tr>
<td valign="top">

Receiver Functional Acknowledgment

</td>
<td valign="top">

Retrieve receiver functional acknowledgment.

</td>
</tr>
<tr>
<td valign="top">

Custom Objects

</td>
<td valign="top">

Retrieve custom objects.

</td>
</tr>
<tr>
<td valign="top">

Error Details

</td>
<td valign="top">

Retrieve error details.

</td>
</tr>
<tr>
<td valign="top">

Business Document Processing Event

</td>
<td valign="top">

Retrieve processing events.

</td>
</tr>
<tr>
<td valign="top">

Business Document Payloads

</td>
<td valign="top">

Retrieve documents payloads.

</td>
</tr>
<tr>
<td valign="top">

Business Document Protocol Headers

</td>
<td valign="top">

Retrieve protocol headers.

</td>
</tr>
<tr>
<td valign="top">

Business Document Notes

</td>
<td valign="top">

Retrieve business document notes.

</td>
</tr>
<tr>
<td valign="top">

Technical Acknowledgment

</td>
<td valign="top">

Retrieve technical acknowledgments.

</td>
</tr>
<tr>
<td valign="top">

Functional Acknowledgment

</td>
<td valign="top">

Retrieve functional acknowledgments.

</td>
</tr>
<tr>
<td valign="top">

Data Archiving

</td>
<td valign="top">

Allows you to activate data archiving. See [Archiving Data](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/archiving-data-cloud-foundry-environment?locale=en-US&state=PRODUCTION&version=Cloud).

</td>
</tr>
</table>

For general information about query options, see [Query Options](https://help.sap.com/docs/integration-suite/sap-integration-suite/query-options).



<a name="loio56ccf98b864144219ae32aff6035b23f__section_bxm_gch_zgc"/>

## Example Requests

To trigger the modifying actions \(POST, PUT, and DELETE\), you need to fetch a CSRF token first, as described in the following:

1.  Send a GET call to the API with a header X-CSRF-Token with the value `Fetch`.
2.  As a response, you get the value of the token in the header X-CSRF-Token.
3.  When sending the modifying request, add the header X-CSRF-Token with the token retrieved from the first call.

On SAP Business Accelerator Hub, you can test API calls against a sandbox tenant or against a custom tenant, which you configure under *API Environment*. If you want to perform an API call against your custom tenant using an HTTP client such as Postman, make sure that the request URL is composed according to the following pattern:

`https://<host address>/api/v1/<relative resource path>`

> ### Note:  
> `https://<host address>/api/v1` is the service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

You can find the relative resource path for each operation on SAP Business Accelerator Hub. For example requests, see [B2B Scenarios](https://hub.sap.com/api/B2BScenarios/overview).



### Get Orphaned Interchanges for a Dedicated Time Period

In the following example, you want to get the orphaned interchanges within a dedicated time period. In this case, assume that the time period is 2025-10-07T11:23:17.152 to 2025-10-08T11:23:17.152.

1.  Perform a GET call with the following resource path:

    ```
    OrphanedInterchanges/$count?$filter=(Date ge datetime'2025-10-07T11:23:17.152' and Date le datetime'2025-10-08T11:23:17.152') 
    ```

2.  Then, send the following GET request:

    ```
    https://<host address>/api/v1/ OrphanedInterchanges/$count?$filter=(Date ge datetime'2025-10-07T11:23:17.152' and Date le datetime'2025-10-08T11:23:17.152') 
    ```




### Get Document Payloads

In the following example, you want to retrieve business document payloads for a specific business document.

1.  Perform a GET call with the following resource path:

    ```
    /BusinessDocuments('{Id} 
    ')/BusinessDocumentPayloads 
    ```

    With this API, you can retrieve all business document payloads associated with a specific business document. It's typically used to view all raw data content \(such as attachments or messages\) related to a business document.

2.  Assume that the document ID is `9b12fbad477049ff907ac7f5a8411528`. To get the custom header property, send the following GET request:

    ```
    https://<host address>/api/v1//BusinessDocuments('9b12fbad477049ff907ac7f5a8411528')/BusinessDocumentPayloads
    ```


