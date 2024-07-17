<!-- loio0fbbe93559ea43778287c56c216f944c -->

# Enable Archiving

To enable data archiving on a tenant in the Cloud Foundry environment, use the OData API.

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

If enabling the archiving function is successful, you get a response code `200` and a message of success. After a successful activation call, you can configure archiving for integration flows in the *Monitor* section. To do so, you've to reload the *Monitor* section to be able see the configuration options for your integration flows.

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

