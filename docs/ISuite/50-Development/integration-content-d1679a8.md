<!-- loiod1679a80543f46509a7329243b595bdb -->

# Integration Content

Manage integration artifacts for your tenant.

You can access the OData API at:

[Integration Content](https://api.sap.com/api/IntegrationContent/)

There, you find the basic operations.

This documentation provides additional information.



<a name="loiod1679a80543f46509a7329243b595bdb__section_w14_z43_4db"/>

## Overview

Operating an integration scenario requires certain integration artifacts. Using the OData API you can access integration artifacts.

Integration artifacts contain the information required for the runtime components to process messages in the context of a certain integration scenario. First and foremost, an integration flow artifact contains all information about the connectivity settings and processing steps modeled in an integration flow model with the Web UI \(in the *Design* section\). When an integration developer has finished the modeling tasks, they deploy the integration - as an *integration artifact* - on the tenant and, that way, makes it executable.

There are more kinds of artifacts, as summarized in the following table.

**Integration Artifact Types**


<table>
<tr>
<th valign="top">

Artifact Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Integration flow

</td>
<td valign="top">

An executable integration flow model

An integration flow specifies the way how a message is to be processed between different systems.

In particular, you define in an integration flow: the senders and receivers of a message, how the senders and receivers are connected to the tenant \(adapters\), and the steps that define the message processing.

You can design an integration flow in the Web UI *Design* section.

</td>
</tr>
<tr>
<td valign="top">

Value mapping

</td>
<td valign="top">

An executable value mapping definition

A value mapping allows you to transform one representation of an object to another representation. In most situations when data is exchanged between two systems, two ways of representing the same data need to be translated.

For example, one specific person is referred to as a particular customer number in one system and as an employee number in another system. Both numbers refer to the same person.

You can design a value mapping in the Web UI *Design* section.

> ### Note:  
> You can create a new Value Mapping artifact from any existing/downloaded Value Mapping project. You can upload either a .zip or a .jar file format.



</td>
</tr>
<tr>
<td valign="top">

OData API 

</td>
<td valign="top">

An executable OData API model

You can use an OData API to expose data sources as OData endpoints. You can design an OData in the Web UI *Design* section. The system generates from an OData API an integration flow that contains by default an OData sender adapter.

</td>
</tr>
</table>

Alternatively, you can access integration content through the OData API.



<a name="loiod1679a80543f46509a7329243b595bdb__section_ewb_szw_k5b"/>

## Permissions

To authorize an API client to access the OData API, perform the steps as described at:

Perform the steps described at: [Setting Up Inbound HTTP Connections \(for API Clients\)](../40-RemoteSystems/setting-up-inbound-http-connections-for-api-clients-8db3d51.md) 

Assign the role template as listed for the desired task \(for example, download deployed integration flow\) under [Tasks and Permissions for Cloud Integration](../60-Security/tasks-and-permissions-for-cloud-integration-556d557.md).

To be able to maintain custom tags:

Assign the following role template:

`WebToolingSettingsProductProfiles.savetenantconfiguration` \(part of role collection `PI_Administrator`\)



<a name="loiod1679a80543f46509a7329243b595bdb__section_uvw_dlf_t4b"/>

## Resources

The following table contains a list of resources and their respective descriptions.

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

Integration Package - Discover

</td>
<td valign="top">

Represents an integration package in the Cloud Integration *Discover* section.

You can use the `CopyIntegrationPackage` resource to copy an integration package from the *Discover* section to the *Design* section.

</td>
</tr>
<tr>
<td valign="top">

Integration Packages - Design

</td>
<td valign="top">

Represents an integration package in the Cloud Integration *Design* section.

You can use resource `IntegrationPackages` to access \(create, update, delete, read\) integration packages. You can read an entire integration package, or only an integration flow or you can read all the packages in design time.

</td>
</tr>
<tr>
<td valign="top">

Custom Tag Configurations

</td>
<td valign="top">

Represents a set of attributes \(custom tags\) defined on tenant level. Once defined, the integration package owners need to maintain these attributes when creating new integration packages.

The tenant administrator can maintain integration package-related attributes that are also referred to as *custom tags*. Integration developers can use custom tags to classify their integration packages.

If the tenant administrator has classified the custom tag as mandatory, the integration developer has to maintain the attribute when creating an integration package. Otherwise, the integration developer can't save the integration package.

Custom tags make it easier for integration developers to organize integration content across a large organization.

> ### Tip:  
> Example
> 
> The tenant administrator can define the mandatory custom tag `Author`. As a result, for each newly created integration package the integration developer has to specify the author name. This makes it easy for all involved integration developers to keep track of the ownership of the individual integration packages.

The tenant administrator can maintain custom tags using one of the following options:

-   Using the Cloud Integration *Settings* section.

-   Using the OData API \(`Custom Tags` interface\)


More information:

-   [Creating Custom Tags](IntegrationSettings/creating-custom-tags-71c0448.md)

-   [SAP Cloud Integration – Custom Tags](https://blogs.sap.com/2020/05/11/sap-cloud-integration-custom-tags/) \(SAP Community blog\)


> ### Note:  
> For more information on how to access custom tags specified for an individual integration package, see:
> 
> [SAP Cloud Integration – Custom Tags](https://blogs.sap.com/2020/05/11/sap-cloud-integration-custom-tags/) \(SAP Community blog\)



</td>
</tr>
<tr>
<td valign="top">

Integration Flow

</td>
<td valign="top">

Represents an integration flow model.

You can use resource `IntegrationDesigntimeArtifacts` to read, download, create, upload, deploy, and delete integration flows.

> ### Note:  
> -   You can't delete content from configure-only package.
> -   You can't delete from a locked artifact.



</td>
</tr>
<tr>
<td valign="top">

Configurations of Integration Flow

</td>
<td valign="top">

Represents externalized configuration parameters for an integration flow.

You can read or update integration flow configurations.

You can access integration flow configurations through the `IntegrationDesigntimeArtifacts` resource.

</td>
</tr>
<tr>
<td valign="top">

Resources of Integration Flow

</td>
<td valign="top">

Represents integration flow resources.

You can read, download, add, or update integration flow resources.

You can access integration flow resources through the `IntegrationDesigntimeArtifacts` resource.

> ### Note:  
> You can use the *ReferencedResourceType* parameter if you want to refer to a file type with another file type. For example, you can refer to an xsd file with a wsdl file. In this case, the value of the parameter is wsdl.
> 
> You can't download resources from configure-only content.



</td>
</tr>
<tr>
<td valign="top">

Message Mapping

</td>
<td valign="top">

Represents a message mapping.

You can read, create, and delete message mappings.

You can access message mappings through the `MessageMappingDesigntimeArtifacts` resource.

</td>
</tr>
<tr>
<td valign="top">

Script Collection

</td>
<td valign="top">

Represents a script collection.

You can create and upload a script collection, add resources to a script collection, and deploy a script collection.

You can access script collections through the `ScriptCollectionDesigntimeArtifacts` resource.

</td>
</tr>
<tr>
<td valign="top">

Build and Deploy Status

</td>
<td valign="top">

Represents the build and deploy status. This status indicates the deployment status of the artifact that is triggered for deployment.

You can access integration flow configurations through the `BuildAndDeployStatus` resource.

For more information on the possible status values, see [Build and Deploy Status](build-and-deploy-status-d8934e0.md).

For integration artifacts that have reached the worker node, another status becomes relevant, the runtime status. The runtime status indicates if a deployed artifact is ready to operate \(see [Runtime Status](runtime-status-c14a7b1.md)\).

</td>
</tr>
<tr>
<td valign="top">

MDI Delta Token

</td>
<td valign="top">

Represents the delta token for the SAP Master Data Integration receiver adapter \(MDI receiver adapter\).

See: [SAP Master Data Integration Receiver Adapter](sap-master-data-integration-receiver-adapter-e91e373.md)

</td>
</tr>
<tr>
<td valign="top">

Runtime Artifacts

</td>
<td valign="top">

Represents the runtime artifact associated with a design time artifact \(for example, an integration flow model or a value mapping\).

You can use resource `IntegrationRuntimeArtifacts` to read, deploy, and undeploy integration content.

> ### Note:  
> To deploy a runtime artifact, you've to include the artifact that you want to deploy as a binary stream into the body of your POST request. Refer to the OData Protocol specification for details on how to use Media Entities.
> 
> You can only deploy `BUNDLE` type integration artifacts \(integration flows, value mappings, or OData services\).



</td>
</tr>
<tr>
<td valign="top">

Error Information of Runtime Artifact

</td>
<td valign="top">

Represents error information related to a runtime artifact.

You can read error information related to deployed integration artifacts \(such as integration flows, for example\).

You can access error information through the `IntegrationRuntimeArtifacts` resource.

</td>
</tr>
<tr>
<td valign="top">

Endpoints of Runtime Artifacts

</td>
<td valign="top">

Represents endpoints of deployed integration content \(for example, integration flow endpoints\).

You can use resource `ServiceEndpoints` to read all endpoints provided for integration flows and to get the number of endpoints.

</td>
</tr>
<tr>
<td valign="top">

Value Mappings

</td>
<td valign="top">

Represents value mapping.

You can use resource `ValueMappingDesigntimeArtifacts` to read, download, create, upload, deploy value mappings, and to delete entries from value mappings.

</td>
</tr>
<tr>
<td valign="top">

Integration Adapter

</td>
<td valign="top">

Represents an integration adapter \(only available in the Cloud Foundry environment\).

You can use resource `IntegrationAdapterDesigntimeArtifacts` to import, deploy, or delete an integration adapter.

</td>
</tr>
</table>

For general information about query options, see [Query Options](query-options-99f4b70.md).

> ### Note:  
> To access integration content through a user interface, you can use the Cloud Integration *Design* application. To access predefined integration packages, you can go to the Cloud Integration *Discover* application.



<a name="loiod1679a80543f46509a7329243b595bdb__section_wsk_33x_54b"/>

## Example Requests

You find various example requests on SAP Business Accelerator Hub at [Integration Content](https://api.sap.com/api/IntegrationContent/).

For more example requests, see [Integration Content Example Requests](integration-content-example-requests-60cc8f1.md).



To trigger the modifying actions \(POST, PUT, and DELETE\), you need to fetch a CSRF token first. You can do that in the following way: First, send a GET call to the API with a header `X-CSRF-Token` with the value `Fetch`. As a response, you get the value of the token in the header `X-CSRF-Token`. When sending the modifying request, add the header `X-CSRF-Token` with the token retrieved from the first call.



On SAP Business Accelerator Hub, you can test API calls against a sandbox tenant or against a custom tenant \(to be configured under *API Environment*\). If you want to perform an API call against your custom tenant using an HTTP client such like Postman, make sure that the request URL is composed in the following way:

`https://<host address>/api/v1/<relative resource path>`

The part `https://<host address>/api/v1` is also referred to as service root URI of the API call. For more information on the address of an API call, see [HTTP Calls and URI Components](http-calls-and-uri-components-ca75e12.md).

You can find the relative resource path for each operation on SAP Business Accelerator Hub.

