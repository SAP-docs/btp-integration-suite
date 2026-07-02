<!-- loioad719c1c2ecb48b6ba275d2b0ee2ba7a -->

# External Logging Cloud Foundry Environment

The external logging feature enables customers to send message processing logs to an external system, independently of available database storage. This section describes how to enable it on your tenant.



## Context

> ### Caution:  
> This information is relevant only when you use SAP Cloud Integration in the Cloud Foundry environment.

The major customer use cases for the external logging feature are the integration into existing monitoring solutions, or the consolidation of logs of multiple tenants. You can use it for high-throughput scenarios \(currently limited by our systems and databases\) and high volume queries. And it is also suitable for advanced analysis, as well as for correlation with business data and long-term archiving.

> ### Caution:  
> Avoid transmitting message payloads or other large data volumes to an external logging system through custom headers. This may affect the performance of the data replication to the external logging system.

The external logging feature supports the following **target systems**:

-   **[Splunk](external-logging-cloud-foundry-environment-ad719c1.md#loioad719c1c2ecb48b6ba275d2b0ee2ba7a__SPLUNK)**. You can send logs to Splunk through the HTTP Event Collector \(HEC\) API.

-   **[JSON](external-logging-cloud-foundry-environment-ad719c1.md#loioad719c1c2ecb48b6ba275d2b0ee2ba7a__JSON)**. You can send logs as JSON objects to any HTTP endpoint. For example, you can integrate with custom log processing pipelines.

-   **[OTEL](external-logging-cloud-foundry-environment-ad719c1.md#loioad719c1c2ecb48b6ba275d2b0ee2ba7a__OTEL)**. You can send logs as OpenTelemetry Protocol \(OTLP\) log records over HTTP to any OTLP-compatible receiver.


Select the target system by setting the *TargetSystem* destination property to one of the values listed above.

> ### Restriction:  
> You can assign only one type of destination as a target system at a time.



## Prerequisites

To activate external logging in the Cloud Foundry Environment on your tenant, you have to fulfill the following prerequisites:

-   You are tenant Admin with the role `AuthGroup_Administrator` as well as the role `ExternalLoggingActivate`.

-   Use the `activateExternalLogging` function of the official OData API, see [Message Processing Logs](https://api.sap.com/api/MessageProcessingLogs/overview).


To access APIs clients, see [Setting Up Inbound HTTP Connections \(for API Clients\)](../ConnectionSetup/setting-up-inbound-http-connections-for-api-clients-8db3d51.md). Create a new role collection and include the following roles: `ExternalLoggingActivationRead` and `ExternalLoggingActivate`.



## Procedure

To create a destination:

1.  Go to your subaccount, and under *Connectivity*, choose *Destinations.*
2.  Select the context level where you want to create destinations.
3.  Choose *Create*, and then choose *From Scratch* to create a new destination.
4.  Configure the following parameters:

**Mandatory Destination Properties**


<table>
<tr>
<th valign="top">

Property \(mandatory with \*\)

</th>
<th valign="top">

Value or Description

</th>
</tr>
<tr>
<td valign="top">

*Name*\*

</td>
<td valign="top">

The name must be `CloudIntegration_MonitoringDataConsumer`.

</td>
</tr>
<tr>
<td valign="top">

*Type*\*

</td>
<td valign="top">

The type HTTP is used for both HTTP and HTTPS connections.

</td>
</tr>
<tr>
<td valign="top">

*URL*\*

</td>
<td valign="top">

The URL of the target system endpoint.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*\*

</td>
<td valign="top">

Choose `Internet` for cloud-hosted target systems, and `On Premise` for on-premises installations accessed through the Cloud Connector.

</td>
</tr>
<tr>
<td valign="top">

*TargetSystem*\*

</td>
<td valign="top">

Identifies the type of target system. Choose one of the following:

-   [Splunk](external-logging-cloud-foundry-environment-ad719c1.md#loioad719c1c2ecb48b6ba275d2b0ee2ba7a__SPLUNK)
-   [JSON](external-logging-cloud-foundry-environment-ad719c1.md#loioad719c1c2ecb48b6ba275d2b0ee2ba7a__JSON)
-   [OTEL](external-logging-cloud-foundry-environment-ad719c1.md#loioad719c1c2ecb48b6ba275d2b0ee2ba7a__OTEL)



</td>
</tr>
</table>

You can add additional properties by using the *New Property* option.

> ### Restriction:  
> If you want to add additional properties, you must enter them manually.

**Additional Properties**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Value or Description

</th>
</tr>
<tr>
<td valign="top">

`CompressData` 

</td>
<td valign="top">

If set to **true** \(default\), the system compresses HTTP request bodies using GZIP before transmission.

</td>
</tr>
<tr>
<td valign="top">

`TrustAll` 

</td>
<td valign="top">

If set to **true**, the system disables SSL certificate verification.

> ### Note:  
> Use this property with caution.



</td>
</tr>
<tr>
<td valign="top">

`TrustStoreLocation` 

</td>
<td valign="top">

Path or name of a trust store for SSL verification. Supported formats include .jks, .p12, .pfx, or a raw PEM certificate.

</td>
</tr>
<tr>
<td valign="top">

`TrustStorePassword` 

</td>
<td valign="top">

Password for the trust store specified in `TrustStoreLocation`.

</td>
</tr>
<tr>
<td valign="top">

`CloudConnectorLocationId` 

</td>
<td valign="top">

Logical location ID for the Cloud Connector instance. This is required when the system is configured with multiple Cloud Connector instances.

</td>
</tr>
<tr>
<td valign="top">

`MaxBatchSize` 

</td>
<td valign="top">

Maximum number of bytes per write batch.

</td>
</tr>
<tr>
<td valign="top">

`MaxBatchCount` 

</td>
<td valign="top">

Maximum number of log events per write batch.

</td>
</tr>
<tr>
<td valign="top">

`DateFormat` 

</td>
<td valign="top">

Format string for human-readable timestamps in log events.

> ### Note:  
> The default format is yyyy-MM-dd HH:mm:ss.SSS.



</td>
</tr>
<tr>
<td valign="top">

`SubValuesInline` 

</td>
<td valign="top">

If set to true, the system adds values such as custom header attributes and adapter attributes as nested JSON structures within the base Run event. This property is independent of `SubValuesExtra`. The default is **false**.

</td>
</tr>
<tr>
<td valign="top">

`SubValuesExtra` 

</td>
<td valign="top">

If set to **true** \(default\), the system adds values such as custom header attributes and adapter attributes as separate stand-alone events following the base Run event. This property is independent of `SubValuesInline`.

</td>
</tr>
</table>

> ### Note:  
> Each target system has its own set of additional properties. For more details, see the sections for [Splunk](external-logging-cloud-foundry-environment-ad719c1.md#loioad719c1c2ecb48b6ba275d2b0ee2ba7a__SPLUNK), [JSON](external-logging-cloud-foundry-environment-ad719c1.md#loioad719c1c2ecb48b6ba275d2b0ee2ba7a__JSON), and [OTEL](external-logging-cloud-foundry-environment-ad719c1.md#loioad719c1c2ecb48b6ba275d2b0ee2ba7a__OTEL).



## Enabling External Logging

To enable external logging, send a `POST` call to the following URL: `https://path-to-odata-api/api/v1/activateExternalLogging[?defaultLogLevel=(NONE|INFO|ERROR)]`, where the `path-to-odata-api` is specific to your environment.

The optional parameter `defaultLogLevel` specifies the external logging level applied to existing and newly deployed integration flows. If this parameter is omitted or is *NONE*, then external logging doesn't take place, unless explicitly activated for a specific integration flow. If the log level is set to *INFO* or *ERROR* instead, MPLs for existing integration flows and newly deployed integration flows are immediately sent to the external system, unless the setting is explicitly changed for a specific integration flow. You can change the default setting anytime by calling the activation API again. If external logging is already active, it takes up to 5 minutes for the new default level to take effect.

If the enabling of the external logging function is successful, you get a response code 200 and a message of success.

To check whether external logging is currently configured on a tenant, use the OData API allowing to query the message processing logs. Send a `GET` call to the URL: `https://path-to-odata-api/api/v1/ExternalLoggingActivationStatus('tenant-name')`, where `path-to-odata-api` is specific to your environment. The parameter `tenant-name` doesn't specify the name of the tenant for which you check the status of the external logging function. The information about the tenant is taken from the security token used for the request.

You've to reload the *Monitor* to be able to see the external logging level options for your integration flows. If the enablement isn't successful, the system throws an error code as well as an error message.

If the external logging is activated,

1.  Go to the *Manage Integration* section.

2.  Choose the integration flow you want to have the external logging for.
3.  In the *Log Configuration* section, in addition to the standard *Log Level* you can set the *External Log Level*.
4.  You've 2-log level options to choose from: *Info* and *Error*.

After the successful activation of the external logging, you can deploy an integration flow and monitor it as usual.

The MPLs are sent to the the configured external system. The MPLs sent to the external destination aren't stored in an SAP database, and SAP can't access them. Internal and external log levels can be set independently.

> ### Note:  
> If an integration flow is undeployed, the external logging level is lost. You've to reconfigure the external logging level after redeployment of the integration flow.



## Disabling External Logging

After activation, you can cancel the logging to an external destination by deactivating the external logging feature. To disable external logging, send a POST call to the following URL `https://path-to-odata-api/api/v1/deactivateExternalLogging`, where the `path-to-odata-api` is specific to your environment. If the disabling of the external logging function is successful, you get a response code 200 and a message of success.

After deactivation, no MPLs are sent to the external system. Logging configuration for deployed integration flows is retained and once activated again, the configured external logging level is restored to the value before deactivation.



### External Logging Status Information API

We provide a status API to monitor the current status of external logging or diagnose errors in case external logging is disabled.

To retrieve status information , send a GET call to the following URL: `https://path-to-odata-api/api/v1/ExternalLoggingEvents` where the `path-to-odata-api` is specific to your environment. If external logging is activated, it returns a list of events that occurred in the last 14 days for these possible events:

-   External Logging was activated.

-   External logging was deactivated.
-   Errors causing failures in sending data to an external system.
-   Resuming sending data to an external system once an error is cleared.

If there are errors, the event carries the error reason as well as the error details received from the external system \(if available\).



<a name="loioad719c1c2ecb48b6ba275d2b0ee2ba7a__SPLUNK"/>

## Splunk

When you set *TargetSystem* to **Splunk**, the system sends log events to Splunk through the HTTP Event Collector \(HEC\) API. The destination URL must point to the Splunk HEC base URL without including the endpoint path.

> ### Example:  
> For a Splunk Cloud Platform host named `myhost`, use: `https://http-inputs-myhost.splunkcloud.com`.

For details on enabling and configuring the HTTP Event Collector, see [Set up and use HTTP Event Collector in Splunk Web](https://docs.splunk.com/Documentation/Splunk/9.0.3/Data/UsetheHTTPEventCollector).

Authentication for Splunk requires an HEC token. You can provide the token in one of the following ways:

-   By using basic authentication. Set **Authentication** to **Basic Authentication**, **User** to any value \(such as Splunk\), and **Password** to the HEC token value.
-   By using the `AuthHeader` property. Set `AuthHeader` to the value `Splunk <token>` \(the word Splunk, followed by a space, then the token value\).


The Splunk target system supports both HTTP and HTTPS connections using direct connections or connections through the Cloud Connector. For authentication, it only supports **None** \(when the HEC token is provided through the `AuthHeader` property\) or *Basic Authentication* \(when the HEC token is provided through the `Password` property\). The system doesn't support any other authentication methods in the destination configuration.

You can add the following additional properties for Splunk using the `New Property` option:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Value or Description

</th>
</tr>
<tr>
<td valign="top">

`IndexName`

</td>
<td valign="top">

Enter an index name.

</td>
</tr>
<tr>
<td valign="top">

`Source` 

</td>
<td valign="top">

Any value, used to fill in the source attribute Splunk events.

</td>
</tr>
<tr>
<td valign="top">

`Host`

</td>
<td valign="top">

Any value, used to fill in the host attribute Splunk events.

</td>
</tr>
<tr>
<td valign="top">

`AuthHeader` 

</td>
<td valign="top">

Custom value for the HTTP authorization header. For example: `Bearer <token>`.

</td>
</tr>
<tr>
<td valign="top">

`SourceType`

</td>
<td valign="top">

If the source type is specified, it's set to the defined value in Splunk events.

</td>
</tr>
<tr>
<td valign="top">

`DynamicSourceType`

</td>
<td valign="top">

If set to `true`, the source type is set to a value matching one of the following event types:

-   `Run` for MPL runs

-   `CustomHeader` for custom header events
-   `AdapterAttribute` for adapter attribute events



</td>
</tr>
<tr>
<td valign="top">

`SourceTypePrefix`

</td>
<td valign="top">

If `DynamicSourceType` is true, and the `SourceTypePrefix` property is, the property value is prepended to the source type.

> ### Example:  
> For a prefix of `Custom` and an MPL run event, the source type is to `CustomRun`.



</td>
</tr>
<tr>
<td valign="top">

`Endpoint` 

</td>
<td valign="top">

The HEC endpoint path appended to the base URL. The default value is `/services/collector/event`

</td>
</tr>
</table>



<a name="loioad719c1c2ecb48b6ba275d2b0ee2ba7a__JSON"/>

## JSON

When you set *TargetSystem* to **JSON**, the system serializes log events as JSON objects and sends them via HTTP POST to the configured URL. This target system is suitable for integrations with custom log processing pipelines and any HTTP endpoint that accepts JSON payloads.

The JSON target system supports HTTP and HTTPS destinations. You can use both direct connections and connections through the cloud connector. The system supports all authentication methods offered in the destination configuration.

You can add the following additional properties for the JSON target system via `New Property`:


<table>
<tr>
<th valign="top">

**Property**

</th>
<th valign="top">

**Value or Description**

</th>
</tr>
<tr>
<td valign="top">

`JSONBatchType`

</td>
<td valign="top">

Controls how the system sends multiple log events in a batch. This property takes effect only when `MaxBatchCount` is greater than one. Possible values:

-   `single` \(default\): the system sends each log event in a separate HTTP POST request.


-   `array`: the system sends all log events in a batch in a single request as a JSON array: \[\{...\}, \{...\}\].


-   `sequence`: the system sends log events in a single request, concatenated and separated by the delimiter configured in `JSONSequenceDelimiter`. This follows the newline-delimited JSON \(NDJSON\) style.




</td>
</tr>
<tr>
<td valign="top">

`JSONSequenceDelimiter`

</td>
<td valign="top">

The delimiter inserted between JSON objects when you select `sequence` for JSONBatchType. The default is \\n \(newline\). You can use escape sequences: \\n, \\r, \\r\\n.

</td>
</tr>
<tr>
<td valign="top">

`JSONFormatting`

</td>
<td valign="top">

Controls the formatting of individual JSON objects. Possible values:

-   `standard` \(default\): compact JSON as produced by the JSON serializer.


-   `pretty`: JSON formatted with two-space indentation for easier reading.


-   `compact`: single-line JSON with all embedded newlines removed.




</td>
</tr>
</table>



<a name="loioad719c1c2ecb48b6ba275d2b0ee2ba7a__OTEL"/>

## OTEL

When you set *TargetSystem* to **OTEL**, the system sends message processing logs as log records that follow the OpenTelemetry Protocol \(OTLP\) Logs format. The system transmits these logs via HTTP POST to the configured URL, using the OTLP/HTTP JSON encoding. This target system works with any OTLP-compatible log backend. Use it with backends such as OpenTelemetry Collector, Grafana Loki, or other OTLP receivers.

The system wraps each batch of log records in the standard OTLP `resourceLogs` structure. It sets the `service.name` resource attribute to identify the source of the logs. Each log record contains the following information:

-   `timeUnixNano`. The time that message processing stops, in nanoseconds.

-   `observedTimeUnixNano`. The time that message processing stops, plus the transmission lag, in nanoseconds.

-   `severityNumber`. The number `17` represents an error , including failed/aborted/cancelled/escalated messages. Number `9` \(Info\) is for all other statuses.

-   `body`. The complete message processing log as a JSON string.


The **OTEL** target system supports HTTP and HTTPS destinations. It supports both direct connections and connections through the cloud connector. It also supports all authentication methods available in the destination configuration.

You can add the following additional properties for the **OTEL** target system via `New Property`:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Value or Description

</th>
</tr>
<tr>
<td valign="top">

`OTELServiceName`

</td>
<td valign="top">

The value of the `service.name` resource attribute. The default value is `MessageProcessingLogs`

</td>
</tr>
<tr>
<td valign="top">

`OTELScopeName`

</td>
<td valign="top">

The name of the instrumentation scope. The default value is `MPL`.

</td>
</tr>
<tr>
<td valign="top">

`OTELScopeVersion`

</td>
<td valign="top">

The version of the instrumentation scope. The default value is `1.0.0`

</td>
</tr>
</table>

> ### Note:  
> The OTEL target systems sends an empty POST body \(`{}`\) during connection validation. It checks whether the response contains `partialSuccess` to confirm the endpoint is an OTLP receiver. If the response does not contain `partialSuccess`, the connection test still succeeds. However, the system warns users that the server may not be a valid OTLP receiver.

