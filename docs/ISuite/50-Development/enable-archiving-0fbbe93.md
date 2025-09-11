<!-- loio0fbbe93559ea43778287c56c216f944c -->

# Enable Archiving

To enable data archiving on a tenant in the Cloud Foundry environment, use the OData API.



<a name="loio0fbbe93559ea43778287c56c216f944c__section_vg5_5td_kgc"/>

## Before You Start

You can configure the content metadata that your document management system uses to archive message processing logs \(MPL\).

You can modify several properties before enabling archiving. Once archiving is enabled, you can't change these properties. Expand the code section below to view the full metadata.

> ### Restriction:  
> Depending on your document management system, only some properties may be supported. For example, OpenText DMS doesn't support `orderable: true`.



### Code

```

  
   
    {
	"id": "mpl:message",
	"localName": "message",
	"localNamespace": "mpl",
	"displayName": "MPL Message",
	"queryName": "mpl:message",
	"description": "MPL Message",
	"baseId": "cmis:document",
	"parentId": "cmis:document",
	"creatable": true,
	"fileable": true,
	"queryable": true,
	"fulltextIndexed": false,
	"includedInSupertypeQuery": true,
	"controllablePolicy": false,
	"controllableACL": true,
	"versionable": false,
	"contentStreamAllowed": "allowed",
	"propertyDefinitions": {
		"mpl:messageGuid": {
			"maxLength": 32,
			"id": "mpl:messageGuid",
			"localName": "messageGuid",
			"localNamespace": "mpl",
			"displayName": "mpl:messageGuid",
			"queryName": "mpl:messageGuid",
			"description": "Guid of message",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:correlationId": {
			"maxLength": 120,
			"id": "mpl:correlationId",
			"localName": "correlationId",
			"localNamespace": "mpl",
			"displayName": "mpl:correlationId",
			"queryName": "mpl:correlationId",
			"description": "correlationId",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:messageId": {
			"maxLength": 120,
			"id": "mpl:messageId",
			"localName": "messageId",
			"localNamespace": "mpl",
			"displayName": "mpl:messageId",
			"queryName": "mpl:messageId",
			"description": "messageId",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:messageType": {
			"maxLength": 100,
			"id": "mpl:messageType",
			"localName": "messageType",
			"localNamespace": "mpl",
			"displayName": "mpl:messageType",
			"queryName": "mpl:messageType",
			"description": "messageType",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:logStart": {
			"id": "mpl:logStart",
			"localName": "logStart",
			"localNamespace": "mpl",
			"displayName": "mpl:logStart",
			"queryName": "mpl:logStart",
			"description": "logStart",
			"propertyType": "datetime",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:logEnd": {
			"id": "mpl:logEnd",
			"localName": "logEnd",
			"localNamespace": "mpl",
			"displayName": "mpl:logEnd",
			"queryName": "mpl:logEnd",
			"description": "logEnd",
			"propertyType": "datetime",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:sender": {
			"maxLength": 40,
			"id": "mpl:sender",
			"localName": "sender",
			"localNamespace": "mpl",
			"displayName": "mpl:sender",
			"queryName": "mpl:sender",
			"description": "sender",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:receiver": {
			"maxLength": 40,
			"id": "mpl:receiver",
			"localName": "receiver",
			"localNamespace": "mpl",
			"displayName": "mpl:receiver",
			"queryName": "mpl:receiver",
			"description": "receiver",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:status": {
			"maxLength": 40,
			"id": "mpl:status",
			"localName": "status",
			"localNamespace": "mpl",
			"displayName": "mpl:status",
			"queryName": "mpl:status",
			"description": "status",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:logLevel": {
			"maxLength": 10,
			"id": "mpl:logLevel",
			"localName": "logLevel",
			"localNamespace": "mpl",
			"displayName": "mpl:logLevel",
			"queryName": "mpl:logLevel",
			"description": "logLevel",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:statusCustom": {
			"maxLength": 40,
			"id": "mpl:statusCustom",
			"localName": "statusCustom",
			"localNamespace": "mpl",
			"displayName": "mpl:statusCustom",
			"queryName": "mpl:statusCustom",
			"description": "statusCustom",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:messageSize": {
			"id": "mpl:messageSize",
			"localName": "messageSize",
			"localNamespace": "mpl",
			"displayName": "mpl:messageSize",
			"queryName": "mpl:messageSize",
			"description": "messageSize",
			"propertyType": "integer",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:transactionCount": {
			"id": "mpl:transactionCount",
			"localName": "transactionCount",
			"localNamespace": "mpl",
			"displayName": "mpl:transactionCount",
			"queryName": "mpl:transactionCount",
			"description": "transactionCount",
			"propertyType": "integer",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:iFlowComponentType": {
			"maxLength": 40,
			"id": "mpl:iFlowComponentType",
			"localName": "iFlowComponentType",
			"localNamespace": "mpl",
			"displayName": "mpl:iFlowComponentType",
			"queryName": "mpl:iFlowComponentType",
			"description": "iFlowComponentType",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:iFlowName": {
			"maxLength": 150,
			"id": "mpl:iFlowName",
			"localName": "iFlowName",
			"localNamespace": "mpl",
			"displayName": "mpl:iFlowName",
			"queryName": "mpl:iFlowName",
			"description": "iFlowName",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:iFlowSymbolicName": {
			"maxLength": 150,
			"id": "mpl:iFlowSymbolicName",
			"localName": "iFlowSymbolicName",
			"localNamespace": "mpl",
			"displayName": "mpl:iFlowSymbolicName",
			"queryName": "mpl:iFlowSymbolicName",
			"description": "iFlowSymbolicName",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": true,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		},
		"mpl:tenantId": {
			"maxLength": 150,
			"id": "mpl:tenantId",
			"localName": "tenantId",
			"localNamespace": "mpl",
			"displayName": "mpl:tenantId",
			"queryName": "mpl:tenantId",
			"description": "tenantId",
			"propertyType": "string",
			"cardinality": "single",
			"updatability": "oncreate",
			"inherited": false,
			"required": false,
			"queryable": true,
			"orderable": true,
			"openChoice": false
		}
	}
}

  

```

To configure the type definition, follow these steps:

> ### Note:  
> If you don't need to change the metadata, you can skip these steps. Enabling archiving automatically deploys the type definition.

1.  Make the necessary changes to the metadata.
2.  Log in to your document management system's repository using WorkBench. For more information, see [Utilizing CMIS Workbench together with BTP DMS](https://community.sap.com/t5/technology-blog-posts-by-sap/utilizing-cmis-workbench-together-with-btp-dms/ba-p/13538866).
3.  Navigate to *Type* in the top menu bar.
4.  Select *CMIS Document*\(`cmis:document`\).
5.  Choose *Create Type* in the top menu bar.
6.  Upload the metadata as a JSON file.

> ### Note:  
> SAP doesn't track configuration changes made on the customer side and isn't responsible for any changes to the properties listed above.



<a name="loio0fbbe93559ea43778287c56c216f944c__section_k1w_csd_kgc"/>

## Procedure

To enable data archiving on your tenant, use the function `activateArchivingConfiguration` of the *Message Processing Logs* OData API \(at: [https://api.sap.com/api/MessageProcessingLogs](https://api.sap.com/api/MessageProcessingLogs), select *Data Archiving* resource\).

A successful activation call performs the following steps:

-   Checks if a destination with the correct name exists.

-   Activates the archiving job.

-   Enables configuration of the archiving settings on the user interface.


On creation of the archiving job, the system defines a random start time for it.

> ### Remember:  
> To avoid job execution errors, ensure to have the destination and \(if you use it\) the Cloud Connector configured correctly.

> ### Note:  
> To call the archiving function, you need the role `DataArchiving.Activate`.

> ### Note:  
> For authorization to the following APIs, follow the instructions provided under [Setting Up Inbound HTTP Connections \(for API Clients\)](../40-RemoteSystems/setting-up-inbound-http-connections-for-api-clients-8db3d51.md).
> 
> Make sure that your user is assigned to the `DataArchiving.Read` or `DataArchiving.Activate` role, depending on the API call you want to make.

To enable archiving, send a `POST` call to the URL : `https://path-to-odata-api/api/v1/activateArchivingConfiguration`, where `path-to-odata-api` is specific to your environment.

If enabling the archiving function is successful, you get a response code `200` and a message of success. After a successful activation call, you can configure archiving for integration flows in the *Monitor* section. To do so, you've to reload the *Monitor* section to be able to see the configuration options for your integration flows.

If the enablement isn't successful, the system throws an error code as well as an error message.

To check whether archiving is currently configured on a tenant, use the OData API allowing to query the message processing logs. Send a `GET` call to the URL: `https://path-to-odata-api/api/v1/ArchivingConfigurations('tenant-name')`, where `path-to-odata-api` is specific to your environment.

> ### Note:  
> To call this function, you've to have the role `DataArchiving.Read`.

> ### Note:  
> The parameter `tenant-name` **doesn't** specify the name of the tenant for which you check the status of the archiving function.
> 
> The information for which tenant you want to check the archiving status, is taken from the security token used for the request.

**Related Information**  


[HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md "")

