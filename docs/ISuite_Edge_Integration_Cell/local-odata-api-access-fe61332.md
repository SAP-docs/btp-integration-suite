<!-- loiofe61332ff9b44fb88fa1e3da57e78ce6 -->

# Local OData API Access

Configure local OData API access to call monitoring APIs directly from Edge Integration Cell.

You can configure local OData API access to call monitoring APIs directly from your Edge Integration Cell runtime, without requiring intervention from the Cloud Integration UI.

You can find the Edge Integration Cell API package on the SAP Business Accelerator Hub at: [Overview | SAP Edge Integration Cell | SAP Business Accelerator Hub](https://api.sap.com/package/sap-int-eic-eic-operations/overview).

More information is available in the following blog: [Local OData API Access in Edge Integration Cell Runtimes](https://community.sap.com/t5/technology-blog-posts-by-sap/local-odata-api-access-in-edge-integration-cell-runtimes/ba-p/14195001).



## Enable Local API Access

To enable the local API access, activate the API support to the cluster in the *Edge Lifecycle Management* page by opening the *Modify Configuration* for your cluster and filling out the following properties related to local API access.

****


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*API Virtual Host*

</td>
<td valign="top">

Enter a custom domain name to expose local API endpoints. Register it in DNS if it needs to be exposed to the internet.

> ### Note:  
> The host name should be different from the default host name.



</td>
</tr>
<tr>
<td valign="top">

*API Virtual Host Key Alias*

</td>
<td valign="top">

Enter the alias of the key pair used to enable TLS on the virtual host. You must create the virtual host key alias and assign a unique name to it before uploading it to the keystore. This name is required when you upload the key alias.

</td>
</tr>
</table>

For information on how to get to the *Modify Configuration* dialogue box, see: [Modify Edge Integration Cell Solution Deployment Properties](modify-edge-integration-cell-solution-deployment-properties-6a060ff.md).



## Authentication

The following authentication methods are supported:

-   **Certificate-based authentication**. You need to use a public and a private key for a TLS connection. See [Client Certificate Authentication for API Clients](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/client-certificate-authentication-for-api-clients?version=CLOUD) for more details.

    > ### Restriction:  
    > External certificates are not supported for Edge Integration Cell local API.

-   **Basic authentication with clientId / clientsecret**. Authenticate users based on the user credentials \(clientid and clientsecret\) that are generated together with a service key. See [Basic Authentication with clientId and clientsecret for API Clients](https://help.sap.com/docs/integration-suite/dev-integrations-and-apis/basic-authentication-with-clientid-and-clientsecret-for-api-clients?version=CLOUD) for more details.

> ### Remember:  
> To authenticate, you need to create a service key in the BTP cockpit. For more information, see [Creating Service Instance and Service Key for Inbound Authentication](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/creating-service-instance-and-service-key-for-inbound-authentication?ai=true&version=CLOUD).



## Making Local API Calls

To distinguish the local API calls from the calls via cloud, you need to add the <code><b>/local</b></code> prefix to your defined Virtual Host followed by `/ap1/v1/<Desired Endpoint>`: **`https://<YOUR_DEFINED_VIRTUAL_HOST>/local/api/v1/<DESIRED_ENDPOINT_TO_BE_CALLED>`**

-   `<YOUR_DEFINED_VIRTUAL_HOST>`: This is the Virtual Host that you have defined for your edge Runtime in the *Edge Lifecycle Management*

-   `/local`: The addition of this prefix to the endpoint call is required to distinguish local calls from the calls via cloud
-   `/api/v1`: Depending on which API is called, the path is `/api/v1` for Message Processing Log and Message Store, or `/api/eic/v1` for Operations Cockpit.
-   `/<DESIRED_ENDPOINT_TO_BE_CALLED>`: This is the same as used for the calls over cloud.


> ### Example:  
> If the API virtual host is `edge-runtime.acme.com`, then the API calls can look like this:
> 
> -   `https://edge-runtime.acme.com/local/api/v1/MessageProcessingLogs`
> -   `https://edge-runtime.acme.com/local/api/v1/MessageStoreEntries`
> -   `https://edge-runtime.acme.com/local/api//eic/v1/Components`

> ### Note:  
> If you do not use the `/local` prefix then a 401 Unauthorized error will occur, even if you use a valid credential.



## API Overview

To trigger modifying actions \(POST, PUT, PATCH, and DELETE\), you need to fetch a CSRF token first. To do that, follow these steps:

1.  Send a GET call to the API root with the header `X-CSRF-Token` set to the value `Fetch`.
2.  The response includes the token value in the `X-CSRF-Token` header.
3.  When you send the modifying request, add the `X-CSRF-Token` header with the token retrieved from the first call.

The API package is organized on SAP Business Accelerator Hub based on the sections shown in the following table:


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Supported API Endpoints

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

[Message Processing Logs](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/message-processing-logs?ai=true&version=CLOUD)

</td>
<td valign="top">

-   `/MessageProcessingLogs`
    -   `/MessageProcessingLogErrorInformations`
    -   `/MessageProcessingLogAttachments`

    -   `/MessageProcessingLogCustomHeaderProperties`


-   `/DataStores`

    -   `/DataStoreEntries`


-   `/Variables`




</td>
<td valign="top">

Get an overview of messages processed on your Edge Integration Cell runtime and view details for individual messages.

> ### Note:  
> This API is implemented based on OData version 2 specification.

You can find the Message Processing Logs API on SAP Business Accelerator Hub at: [Overview | Message Processing Logs | SAP Business Accelerator Hub](https://api.sap.com/api/sap-int-eic-message-processing-logs-v1/overview)

</td>
</tr>
<tr>
<td valign="top">

[Message Stores](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/message-stores?ai=true&version=CLOUD)

</td>
<td valign="top">

-   `/MessageStoreEntries`
    -   `/MessageStoreEntryProperties`

    -   `/MessageStoreEntryAttachments`

    -   `/MessageStoreEntryAttachmentProperties`


-   `/JmsBrokers`
-   `/MessagingQueues`
    -   `/MessagingQueues(<queue>)/MessagingMessages`




</td>
<td valign="top">

Access message store entries, JMS resources, and data store entries.

> ### Note:  
> This API is implemented based on OData version 2 specification.

You can find the Message Stores API on SAP Business Accelerator Hub at: [Overview | Message Stores | SAP Business Accelerator Hub](https://api.sap.com/api/sap-int-eic-message-store-v1/overview)

You can find the JMS APIs on SAP Business Accelerator Hub at: [JMS Resources | Message Stores | SAP Business Accelerator Hub](https://api.sap.com/api/MessageStore/resource/JMS_Resources)

</td>
</tr>
<tr>
<td valign="top">

[Operations Cockpit API](operations-cockpit-api-da1abc0.md)

</td>
<td valign="top">

-   `/Components`
    -   `/Components/<component ID>/Pods`

    -   `/Components/<component ID>/Pods/<pod name>/Events`

    -   `/Components/<component ID>/Pods/<pod name>/Metrics`

    -   `/Components/<component ID>/RuntimeParameters`


-   `/Jobs` 
    -   `/Jobs/<jobId>/Schedule`




</td>
<td valign="top">

Access your Edge Integration Cell data even during offline mode when the Operations Cockpit user interface is unavailable.

> ### Note:  
> This API is implemented based on OData version 4 specification.

You can retrieve information such as component statuses, pods, event logs, metrics, and runtime parameters. You can also restart components.

You can find the Operations Cockpit API on SAP Business Accelerator Hub at: [ODATA V4 API | SAP Edge Integration Cell | SAP Business Accelerator Hub](https://api.sap.com/package/sap-int-eic-eic-operations/odatav4)

</td>
</tr>
</table>

> ### Note:  
> Not all APIs are exposed for local access. If you use an endpoint not listed here, an 403 Error will occur.



## Related Information

[API Documentation](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/api-documentation-3fd9fc923dee4d5db0696cfdce187154?version=CLOUD)

[Business Accelerator Hub OData API Documentation for Edge Integration Cell](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fapi.sap.com%2Fpackage%2Fsap-int-eic-eic-operations%2Foverview)

[Local OData API Access in Edge Integration Cell Ru... - SAP Community](https://community.sap.com/t5/technology-blog-posts-by-sap/local-odata-api-access-in-edge-integration-cell-runtimes/ba-p/14195001)

