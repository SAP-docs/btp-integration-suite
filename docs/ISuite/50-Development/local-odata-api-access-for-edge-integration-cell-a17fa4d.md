<!-- loioa17fa4df7744455c8a35d1c3c2e45787 -->

# Local OData API Access for Edge Integration Cell

For Edge Integration Cell users, it is possible to configure local OData API access. This allows you to call a number of monitoring APIs without the intervention of the Cloud Integration UI, making it possible to directly access the APIs from the Edge Integration Cell.

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

Enter a valid domain name of your choice. Register in DNS if it needs to be internet-exposed.

</td>
</tr>
<tr>
<td valign="top">

*API Virtual Host Key Alias*

</td>
<td valign="top">

Use an alias for the keystore entry containing a valid key stored in the runtime.

</td>
</tr>
</table>

For information on how to get to the *Modify Configuration* dialogue box, see: [Modify Edge Integration Cell Solution Deployment Properties](../modify-edge-integration-cell-solution-deployment-properties-6a060ff.md).



## Authentication

Only a certificate-based authentication is supported. You need to use a public and a private key for a TLS connection. See [Client Certificate Authentication for API Clients](../40-RemoteSystems/client-certificate-authentication-for-api-clients-d9ca0ac.md) for more details on this type of authentication.



## Making Local API Calls

To distinguish the local API calls from the calls via cloud, you need to add the `/local` prefix to your defined Virtual Host followed by `/ap1/v1/<Desired Endpoint>`.

> ### Example:  
> `https://<YOUR_DEFINED_VIRTUAL_HOST>/local/api/v1/<DESIRED_ENDPOINT_TO_BE_CALLED>`
> 
> -   `<YOUR_DEFINED_VIRTUAL_HOST>`: This is the Virtual Host that you have defined for your edge Runtime in the *Edge Lifecycle Management*
> 
> -   `/local`: The addition of this prefix to the endpoint call is required to distinguish local calls from the calls via cloud
> -   `/api/v1`: Same as used for the calls over the cloud
> -   `/<DESIRED_ENDPOINT_TO_BE_CALLED>`: This is the same as used for the calls over cloud.

> ### Note:  
> If you do not use the `/local` prefix then a 401 Unauthorized error will occur, even if you use a valid credential.



## Supported API Endpoints

A subset of the OData APIs is exposed for local access, including:

-   `/MessageProcessingLogs`

    -   `/MessageProcessingLogErrorInformations`

    -   `/MessageProcessingLogAttachments`

    -   `/MessageProcessingLogCustomHeaderProperties`


-   `/MessageStoreEntries`

    -   `/MessageStoreEntryProperties`

    -   `/MessageStoreEntryAttachments`

    -   `/MessageStoreEntryAttachmentProperties`


-   `/DataStores`

    -   `/DataStoreEntries`


-   `/JmsBrokers`

-   `/Variables`


> ### Note:  
> Not all APIs are exposed for local access. If you use an endpoint not listed here, an 403 Error will occur.

**Related Information**  


[Business Accelerator Hub OData API documentation](https://api.sap.com/package/CloudIntegrationAPI/odata)

[Blog: Local OData API Access in Edge Integration Cell Runtimes](https://community.sap.com/t5/technology-blog-posts-by-sap/local-odata-api-access-in-edge-integration-cell-runtimes/ba-p/14195001)

