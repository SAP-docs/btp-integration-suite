<!-- loioa617d6f37ddc43db8eeb1279662ed5c2 -->

# OData API

The Cloud Integration application programming interface \(API\) allows you to access Cloud Integration resources, for example, monitoring data.

The OData API is implemented as a REST API and the technical protocol is Open Data Protocol \(OData\). This means that you can use standard HTTP methods \(for example, the GET method\) to call the API.

You can find the OData API on SAP Business Accelerator Hub at:

[SAP Cloud Integration](https://api.sap.com/package/CloudIntegrationAPI/odata)

A prerequisite for using the OData API is that your user is connected to Cloud Integration and that you have access to an OData client.

Individual actions that you can perform using the OData API are protected by an authorization concept. To find out the required role for the task that you want to perform with the OData API, see [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

The OData API covers the following aspects:

**OData API Overview**


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

[Integration Content](integration-content-d1679a8.md) 

</td>
<td valign="top">

Get deployed integration content or deploy/undeploy integration artifacts.

</td>
</tr>
<tr>
<td valign="top">

[Log Files, Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/93bc3722533741c7a48eec6a8352f060.html "Access technical system logs written during message processing on the worker/runtime node.") :arrow_upper_right: 

</td>
<td valign="top">

Get an overview of HTTP and trace log files.

</td>
</tr>
<tr>
<td valign="top">

[Message Processing Logs](message-processing-logs-827a2d7.md) 

</td>
<td valign="top">

Get an overview of the messages processed on a tenant and get the details for individual messages.

</td>
</tr>
<tr>
<td valign="top">

[Message Stores](message-stores-1aab5e9.md) 

</td>
<td valign="top">

Get data from the Message Store, such as message payloads, headers, properties, or attachments for processed messages.

</td>
</tr>
<tr>
<td valign="top">

[Partner Directory](partner-directory-0fe80dc.md) 

</td>
<td valign="top">

Get, write, or delete data of the Partner Directory. This content can be used to parameterize integration flows.

</td>
</tr>
<tr>
<td valign="top">

[Security Content](security-content-e01d3f0.md) 

</td>
<td valign="top">

Get, write, or delete security content, for example, keystore entries, user credentials, or certificates to user mappings.

</td>
</tr>
</table>

The OData API is structured by a number of entities, grouped on SAP Business Accelerator Hub according to the sections listed in the previous table. Each entity \(resource\) is specified by a number of properties, to which filtering options can also be applied.

You can address the collection of entries or a single entry within a collection.

How the entities are related to each other is described in the entity data model. This model also provides information on how to navigate between entities using the API.

This documentation provides an overview of the available resources and summarizes the supported HTTP methods and query options for each resource.

> ### Tip:  
> For more information about the programming model and how the HTTP methods and query options work, see [OData - the Best Way to REST](http://www.odata.org).
> 
> OData specification version 2.0 is supported by the Cloud Integration API.



<a name="loioa617d6f37ddc43db8eeb1279662ed5c2__section_cq4_5mj_lvb"/>

## HTTP Calls and URI Components

More information: [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md)



## Recommendations to Improve OData Request Performance

Using the OData API allows you to run certain requests on data processed by and stored on SAP BTP. The load that these requests put on the platform depends on the URL pattern and the respective parameters specified in the request, as well as the amount of data available. The latter depends directly on the details of message processing.

> ### Caution:  
> SAP has set a maximum time for the execution of an OData request. It is the customer's responsibility to design OData requests so that the set of returned data sets remains manageable \(as far as this suits the requirements of the client making the request\).

To keep the load on the network manageable, we therefore recommend that you use query options as follows:

-   Make requests as selective as possible by using the `$filter` option. For example, when you access message processing logs \(MPLs\) using the API, you can filter in such a way that the request retrieves MPLs in a restricted time interval only, with the log end time between two nearby datetime literals.

-   Use the `$select` option to make the API return only those properties that are required by the client. This reduces network load.

-   If it is necessary to navigate a large number of data sets \(\>1000\), use the `$top` and `$skip` options to iterate over the result set. Consider designing the client application in such a way that it offers paging options.

-   Note that when you use the OData API, you navigate to MessageStore entities starting from the MessageProcessingLog entity. Apply filter options to the MessageProcessingLog rather than the MessageStore entities.


**Related Information**  


[Integration Content](integration-content-d1679a8.md "Manage integration artifacts for your tenant.")

[Log Files, Neo Environment](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/93bc3722533741c7a48eec6a8352f060.html "Access technical system logs written during message processing on the worker/runtime node.") :arrow_upper_right:

[Message Processing Logs](message-processing-logs-827a2d7.md "Get an overview of the messages processed on a tenant and get the details for individual messages. The message processing log (MPL) stores data about the messages processed on a tenant. Furthermore, it stores information about the individual processing steps for each processed message.")

[Message Stores](message-stores-1aab5e9.md "Get data from Message Stores for processed messages and resources of the used JMS queues.")

[Partner Directory](partner-directory-0fe80dc.md "The Partner Directory contains information on partners that are connected to a tenant in the context of a larger business partner network.")

[Security Content](security-content-e01d3f0.md "Manage security content on the tenant that is required to configure secure connections with remote systems.")

[Query Options](query-options-99f4b70.md "Query options allow you to control the amount and order of the data that a data service returns for the resource identified by the URI.")

[Authentication](authentication-bd2fbd5.md "The API is protected by basic authentication and OAuth.")

