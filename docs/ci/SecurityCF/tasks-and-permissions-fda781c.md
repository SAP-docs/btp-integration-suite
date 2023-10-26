<!-- copyfda781c59e4b46a390ce5b409f60365e -->

# Tasks and Permissions

The following table provides an overview of which roles are required in order to accomplish the various tasks related to Cloud Integration. It's also indicated in how far the tasks and roles are relevant for the main persona defined for Cloud Integration.

In the different environments, these persona are mapped to different objects.

-   In the Neo environment, a persona is realized by an authorization group \(beginning with the string *AuthGroup*\).

-   In the Cloud Foundry environment, a persona ia realized by a role collection.


The mapping of the persona to the authorization groups \(Neo\) or role collections \(Cloud Foundry\) is described under [Persona](../SecurityNeo/persona-2937e5c.md).

In the different environments, the permissions to execute certain tasks are given by different objects.

-   In the Neo environment, a permission to execute a task is given by a role.

-   In the Cloud Foundry environment, a permission to execute a task is given by a role template.


**Tasks and Permissions**


<table>
<tr>
<th valign="top">

Area

</th>
<th valign="top">

Task

</th>
<th valign="top">

Role \(Neo\)

</th>
<th valign="top">

Role-Templates \(Cloud Foundry\)

</th>
<th valign="top">

Persona

</th>
</tr>
<tr>
<td valign="top">

Discover

</td>
<td valign="top">

View packages

</td>
<td valign="top">

WebToolingCatalog.OverviewRead

</td>
<td valign="top">

CatalogPackagesRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Discover

</td>
<td valign="top">

View package artifacts

</td>
<td valign="top">

WebToolingCatalog.OverviewRead

WebToolingCatalog.DetailsRead

</td>
<td valign="top">

CatalogPackageArtifactsRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Discover

</td>
<td valign="top">

Copy package to workspace

</td>
<td valign="top">

WebToolingCatalog.OverviewRead

WebToolingWorkspace.Write

</td>
<td valign="top">

CatalogPackagesCopy

</td>
<td valign="top">

Integration Developer

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

View packages and package artifacts

</td>
<td valign="top">

WebToolingWorkspace.Read

</td>
<td valign="top">

WorkspacePackagesRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

Create, edit, import, export, delete package with its artifacts

</td>
<td valign="top">

WebToolingWorkspace.Read

WebToolingWorkspace.Write

</td>
<td valign="top">

WorkspacePackagesEdit

</td>
<td valign="top">

Integration Developer

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

Update package

</td>
<td valign="top">

WebToolingWorkspace.Read

WebToolingWorkspace.Write

</td>
<td valign="top">

WorkspacePackagesEdit

</td>
<td valign="top">

Integration Developer

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

Configure artifacts \(integration flows and value mappings\)

</td>
<td valign="top">

WebToolingWorkspace.Read

WebTooling.IntegrationFlowConfigure

</td>
<td valign="top">

WorkspacePackagesConfigure

</td>
<td valign="top">

Integration Developer

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

Deploy/undeploy artifacts

</td>
<td valign="top">

WebToolingWorkspace.Read

NodeManager.read

GenerationAndBuild.generationandbuildcontent

NodeManager.deploycontent

</td>
<td valign="top">

WorkspaceArtifactsDeploy

</td>
<td valign="top">

Integration Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

Export Package for transport

</td>
<td valign="top">

WebToolingWorkspace.Read

TransportModule.read

TransportModule.write

</td>
<td valign="top">

WorkspacePackagesTransport

</td>
<td valign="top">

n.a.

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

Import package from transport

</td>
<td valign="top">

WebToolingWorkspace.Read

TransportModule.read

TransportModule.write

</td>
<td valign="top">

WorkspacePackagesTransport

</td>
<td valign="top">

n.a.

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

Update Package from transport

</td>
<td valign="top">

WebToolingWorkspace.Read

TransportModule.read

TransportModule.write

</td>
<td valign="top">

WorkspacePackagesTransport

</td>
<td valign="top">

n.a.

</td>
</tr>
<tr>
<td valign="top">

Design

</td>
<td valign="top">

Read/write Partner Directory-related content \(string/binary parameters, authorized users, alternative partners, and user credentials\)

Read/write certificate-to-user mappings \(only in the Neo environment\)

</td>
<td valign="top">

TenantPartnerDirectory.read

TenantPartnerDirectory.write

NodeManager.deploycredentials

NodeManager.readcredentials

CertificateUserMappings.Write

CertificateUserMappings.Read

</td>
<td valign="top">

AuthGroup\_TenantPartnerDirectoryConfigurator

</td>
<td valign="top">

Partner Directory configurator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View Monitor Overview

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View message processing logs

</td>
<td valign="top">

IntegrationOperationServer.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View payload of stored messages from message storage \(also trace and message processing log attachments\)

</td>
<td valign="top">

esbmessagestorage.read

</td>
<td valign="top">

 

</td>
<td valign="top">

Business Expert

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View tasks

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View tail log

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View deployed artifact list

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View deployed integration flow in graphical editor

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Download deployed integration flow

Download WSDL

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View deployed security material

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Add credentials

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.deploycredentials

NodeManager.deploycontent

</td>
<td valign="top">

CredentialsEdit

</td>
<td valign="top">

Integration Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Add known host, keystore, PGP keyring artifacts

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.deploysecuritycontent

NodeManager.deploycontent

</td>
<td valign="top">

SecurityMaterialEdit

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Edit credentials

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.deploycredentials

NodeManager.deploycontent

</td>
<td valign="top">

CredentialsEdit

</td>
<td valign="top">

Integration Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Undeploy credentials

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.deploycontent

NodeManager.deploycredentials

</td>
<td valign="top">

CredentialsEdit

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Undeploy known host, keystore, PGP keyring artifacts

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.deploycontent

NodeManager.deploysecuritycontent

</td>
<td valign="top">

SecurityMaterialEdit

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Download keystore, public/prviate keyring, known host, .. artifact

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

NodeManager.readsecuritycontent

</td>
<td valign="top">

SecurityMaterialDownload

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View certificate-to-user mappings

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Create/edit/delete certificate-to-user mappings

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.deploysecuritycontent

NodeManager.read

</td>
<td valign="top">

SecurityMaterialEdit

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View keystore entries

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Download public keystore entries

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Add/replace/delete keystore entries

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.deploysecuritycontent

</td>
<td valign="top">

SecurityMaterialEdit

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View access policies

</td>
<td valign="top">

IntegrationOperationServer.read

AccessPolicies.Read

</td>
<td valign="top">

 

</td>
<td valign="top">

Integration Developer

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Maintain access policies

</td>
<td valign="top">

IntegrationOperationServer.read

AccessPolicies.Write

</td>
<td valign="top">

 

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View data store entries

</td>
<td valign="top">

IntegrationOperationServer.read

ESBDataStore.read

</td>
<td valign="top">

DataStoresAndQueuesRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View data store entries - message payload

</td>
<td valign="top">

IntegrationOperationServer.read

ESBDataStore.readPayload

</td>
<td valign="top">

DataStorePayloadsRead

</td>
<td valign="top">

Business Expert

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View data store entries - variables

</td>
<td valign="top">

IntegrationOperationServer.read

ESBDataStore.readPayload

</td>
<td valign="top">

DataStorePayloadsRead

</td>
<td valign="top">

Business Expert

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Delete data store entries/variables

</td>
<td valign="top">

IntegrationOperationServer.read

ESBDataStore.read

ESBDataStore.delete

</td>
<td valign="top">

DataStoresAndQueuesDelete

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View payload of stored messages from message store

</td>
<td valign="top">

esbmessagestorage.read

</td>
<td valign="top">

MessagePayloadsRead

</td>
<td valign="top">

Business Expert

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View trace configuration

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

ConfigurationService.RuntimeBusinessParameterRead

</td>
<td valign="top">

TraceConfigurationRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Edit trace configuration

\(enable/disable trace\)

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.read

ConfigurationService.RuntimeBusinessParameterRead

ConfigurationService.RuntimeBusinessParameterWrite

</td>
<td valign="top">

TraceConfigurationEdit

</td>
<td valign="top">

Integration Developer

Business Expert

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Override access policies

Get access to data \(for example, JMS queues, message processing log attachments\) although the data is protected by access policies. Note that when this role is assigned to a user, it overrides all access policies that might prevent the user from accessing data processed by certain artifacts \(for example, integration flows\). However, the role AccessPoliciesArtifacts.AccessAll doesn't grant permission to access payload data.

</td>
<td valign="top">

AccessPoliciesArtifacts.AccessAll

</td>
<td valign="top">

AccessPoliciesArtifacts.AccessAll

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Add/Edit/undeploy number ranges

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.deploycontent

</td>
<td valign="top">

MonitoringArtifactsDeploy

</td>
<td valign="top">

Integration Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View number ranges

</td>
<td valign="top">

IntegrationOperationServer.read

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Retry queues

</td>
<td valign="top">

IntegrationOperationServer.read

ESBDataStore.read

ESBDataStore.retry

</td>
<td valign="top">

QueuesRetry

</td>
<td valign="top">

Integration Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Delete queues

</td>
<td valign="top">

IntegrationOperationServer.read

ESBDataStore.read

ESBDataStore.delete

</td>
<td valign="top">

DataStoresAndQueuesDelete

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View queues

</td>
<td valign="top">

IntegrationOperationServer.read

ESBDataStore.read

</td>
<td valign="top">

DataStoresAndQueuesRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View runtime processing locks

</td>
<td valign="top">

IntegrationOperationServer.read

MessageProcessingLocks.Read

</td>
<td valign="top">

MessageProcessingLocksRead

</td>
<td valign="top">

Integration Developer

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Delete runtime processing locks

</td>
<td valign="top">

IntegrationOperationServer.read

MessageProcessingLocks.Delete

</td>
<td valign="top">

MessageProcessingLocksDelete

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Test connectivity

</td>
<td valign="top">

IntegrationOperationServer.read

NodeManager.readcredentials

</td>
<td valign="top">

MonitoringDataRead \(only for tests without authentication\)

CredentialsRead

</td>
<td valign="top">

Integration Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Change log level

</td>
<td valign="top">

IntegrationOperationServer.read

ConfigurationService.RuntimeBusinessParameterWrite

NodeManager.read

</td>
<td valign="top">

 

</td>
<td valign="top">

Integration Developer

Business Expert

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

View audit log entries

</td>
<td valign="top">

IntegrationOperationServer.read

AuditLog.Read

</td>
<td valign="top">

 

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Read data metrics for health monitoring API: JMS queue statistics, certificate expiry dates

</td>
<td valign="top">

HealthCheckMonitoringData.Read

</td>
<td valign="top">

HealthCheckMonitoringData.Read

</td>
<td valign="top">

Specific for CALM

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Activate archiving Enablement

</td>
<td valign="top">

 

</td>
<td valign="top">

DataArchivingActivate

</td>
<td valign="top">

Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Read archiving enablement

</td>
<td valign="top">

 

</td>
<td valign="top">

DataArchivingRead

</td>
<td valign="top">

Integration Developer

Business Expert

Tenant Administrator

ReadOnly Business Expert

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Change archiving configuration

</td>
<td valign="top">

IntegrationOperationServer.read

ConfigurationService.RuntimeBusinessParameterWrite

NodeManager.read

</td>
<td valign="top">

TraceConfigurationEdit

</td>
<td valign="top">

Integration Developer

Business Expert

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Monitor

</td>
<td valign="top">

Change log level

</td>
<td valign="top">

 

</td>
<td valign="top">

TraceConfigurationEdit

</td>
<td valign="top">

Integration Developer

Business Expert

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Inspect

\(only when using SAP Cloud Integration in the Cloud Foundry environment\)

</td>
<td valign="top">

Inspect usage of integration resources

</td>
<td valign="top">

n.a.

</td>
<td valign="top">

MonitoringDataRead

</td>
<td valign="top">

Integration Developer

Business Expert

Read-Only Persona/System Developer

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Settings

</td>
<td valign="top">

View/change runtime profile

</td>
<td valign="top">

WebToolingSettingsProductProfiles.savetenantconfiguration

</td>
<td valign="top">

 

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
<tr>
<td valign="top">

Settings

</td>
<td valign="top">

Set transport system

</td>
<td valign="top">

WebToolingSettingsProductProfiles.savetenantconfiguration

</td>
<td valign="top">

 

</td>
<td valign="top">

Tenant Administrator

</td>
</tr>
</table>

