<!-- loioa17fa4df7744455c8a35d1c3c2e45787 -->

# Local OData API Access for Edge Integration Cell

For Edge Integration Cell users, it is possible to configure local OData API access. This allows you to call a number of monitoring APIs without the intervention of the Cloud Integration UI, making it possible to directly access the APIs from the Edge Integration Cell.

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

For information on how to get to the *Modify Configuration* dialogue box, see:  <?sap-ot O2O class="- topic/xref " href="6a060ffd345a4c4ab545d5c31cb24119.xml" text="Modify Edge Integration Cell Solution Deployment Properties" desc="" xtrc="xref:3" xtrf="file:/home/builder/src/dita-all/zpk1713331951414/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/a17fa4df7744455c8a35d1c3c2e45787.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .



## Authentication

The following authentication methods are supported:

-   **Certificate-based authentication**. You need to use a public and a private key for a TLS connection. See [Client Certificate Authentication for API Clients](../ConnectionSetup/client-certificate-authentication-for-api-clients-d9ca0ac.md) for more details.

    > ### Restriction:  
    > External certificates are not supported for Edge Integration Cell local API.

-   **Basic authentication with clientId / clientsecret**. Authenticate users based on the user credentials \(clientid and clientsecret\) that are generated together with a service key. See  <?sap-ot O2O class="- topic/xref " href="db55f0d917754e999954c2796b11b114.xml" text="" desc="" xtrc="xref:5" xtrf="file:/home/builder/src/dita-all/zpk1713331951414/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/a17fa4df7744455c8a35d1c3c2e45787.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?>  for more details.

> ### Remember:  
> To authenticate, you need to create a service key in the BTP cockpit. For more information, see[Creating Service Instance and Service Key for Inbound Authentication](../ConnectionSetup/creating-service-instance-and-service-key-for-inbound-authentication-19af5e2.md).



## Making Local API Calls

To distinguish the local API calls from the calls via cloud, you need to add the <code><b>/local</b></code> prefix to your defined Virtual Host followed by `/ap1/v1/<Desired Endpoint>`: **`https://<YOUR_DEFINED_VIRTUAL_HOST>/local/api/v1/<DESIRED_ENDPOINT_TO_BE_CALLED>`**

-   `<YOUR_DEFINED_VIRTUAL_HOST>`: This is the Virtual Host that you have defined for your edge Runtime in the *Edge Lifecycle Management*

-   `/local`: The addition of this prefix to the endpoint call is required to distinguish local calls from the calls via cloud
-   `/api/v1`: Same as used for the calls over the cloud
-   `/<DESIRED_ENDPOINT_TO_BE_CALLED>`: This is the same as used for the calls over cloud.


> ### Example:  
> If the API virtual host is `edge-runtime.acme.com`, then the API calls can look like this:
> 
> -   `https://edge-runtime.acme.com/local/api/v1/MessageProcessingLogs`
> -   `https://edge-runtime.acme.com/local/api/v1/MessageStoreEntries`
> -   `https://edge-runtime.acme.com/local/api/v1/Components`

> ### Note:  
> If you do not use the `/local` prefix then a 401 Unauthorized error will occur, even if you use a valid credential.



## API Overview

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

[Message Processing Logs](message-processing-logs-827a2d7.md)

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

[Message Stores](message-stores-1aab5e9.md)

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

Components

</td>
<td valign="top">

-   `/Components`
    -   `/Components/<component ID>/Pods`

    -   `/Components/<component ID>/Pods/<pod name>/Events`

    -   `/Components/<component ID>/Pods/<pod name>/Metrics`

    -   `/Components/<component ID>/RuntimeParameters`





</td>
<td valign="top">

Access Edge Integration Cell system monitoring data, including components, pods, events, metrics, and runtime parameters.

> ### Note:  
> This API is implemented based on OData version 4 specification.

You can find the Components API on SAP Business Accelerator Hub at: [ODATA V4 API | SAP Edge Integration Cell | SAP Business Accelerator Hub](https://api.sap.com/package/sap-int-eic-eic-operations/odatav4)

</td>
</tr>
<tr>
<td valign="top">

 <?sap-ot O2O class="- topic/xref " href="da1abc0c46514798bea0d283f0fb418a.xml" text="" desc="" xtrc="xref:14" xtrf="file:/home/builder/src/dita-all/zpk1713331951414/loio3268cb35959d4b368fb49de861bfe8a1_en-US/src/content/localization/en-us/a17fa4df7744455c8a35d1c3c2e45787.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

</td>
<td valign="top">

 

</td>
<td valign="top">

Access your Edge Integration Cell data even during offline mode when the Operations Cockpit user interface is unavailable.

You can retrieve information such as component statuses, pods, event logs, metrics, and runtime parameters. You can also restart components.

You can find the Operations Cockpit API on SAP Business Accelerator Hub at: [ODATA V4 API | SAP Edge Integration Cell | SAP Business Accelerator Hub](https://api.sap.com/package/sap-int-eic-eic-operations/odatav4)

</td>
</tr>
</table>

> ### Note:  
> Not all APIs are exposed for local access. If you use an endpoint not listed here, an 403 Error will occur.

**Related Information**  


[Business Accelerator Hub OData API Documentation for Edge Integration Cell](https://api.sap.com/package/sap-int-eic-eic-operations/overview)

[Blog: Local OData API Access in Edge Integration Cell Runtimes](https://community.sap.com/t5/technology-blog-posts-by-sap/local-odata-api-access-in-edge-integration-cell-runtimes/ba-p/14195001)

