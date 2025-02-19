<!-- loioad719c1c2ecb48b6ba275d2b0ee2ba7a -->

# External Logging

The external logging feature enables customers to send message processing logs to an external system, independently of available database storage. This section describes how to enable it on your tenant.

The major customer use cases for the external logging feature are the integration into existing monitoring solutions in Splunk, or the consolidation of logs of multiple tenants. You can use it for high-throughput scenarios \(currently limited by our systems and databases\) and high volume queries. And it also suitable for advanced analysis, as well as for correlation with business data and long-term archiving.

If you've already set up Splunk as your external logging destination, you can enable the external logging feature.

To activate external logging in the Cloud Foundry Environment on your tenant, you have to fulfill the following prerequisites:

-   You've to be tenant Admin with the role `AuthGroup_Administrator` as well as the role `ExternalLoggingActivate`.

-   Use `activateExternalLogging` function of the official OData API, see:

    [Message Processing Logs](https://api.sap.com/api/MessageProcessingLogs/overview)


To access APIs clients, see [Setting Up Inbound HTTP connections \(for API Clients\)](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/8db3d5141cd644019f0cf244e2a6763f.html?locale=en-US). Create a new role collection and include the following roles: `ExternalLoggingActivationRead` and `ExternalLoggingActivate`.

To create a destination:

1.  Go to your subaccount, and under *Connectivity*, choose *Destinations.*

2.  Choose *New Destination* and configure the parameters as listed in the following table.


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

Add the destination URL to the Splunk HTTP Event Collector without the endpoint. For a detailed description how the event collector URL is structured, see [https://docs.splunk.com/Documentation/Splunk/9.0.3/Data/UsetheHTTPEventCollector](https://docs.splunk.com/Documentation/Splunk/9.0.3/Data/UsetheHTTPEventCollector)

Example:

For a Splunk Cloud Platform host `myhost`, use

`https://http-inputs-myhost.splunkcloud.com`

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*\*

</td>
<td valign="top">

Choose `Internet` for a Splunk Cloud Platform instance and *On Premise* for a Splunk Enterprise installation.

</td>
</tr>
<tr>
<td valign="top">

*Authentication*\*

</td>
<td valign="top">

Choose *Basic Authentication*.

</td>
</tr>
<tr>
<td valign="top">

*User*\*

</td>
<td valign="top">

Specify the value "Splunk".

</td>
</tr>
<tr>
<td valign="top">

*Password*\*

</td>
<td valign="top">

Specify the HTTP Event Collector token \(generated when configuring HEC in Splunk\).

For information on how to enable and configure the HTTP Event Collector, see: [https://docs.splunk.com/Documentation/Splunk/9.0.3/Data/UsetheHTTPEventCollector](https://docs.splunk.com/Documentation/Splunk/9.0.3/Data/UsetheHTTPEventCollector) 

</td>
</tr>
<tr>
<td valign="top">

*IndexName*\*

</td>
<td valign="top">

Enter an index name.

</td>
</tr>
<tr>
<td valign="top" colspan="2">

*Additional Properties* can be added using *New Property* \(mandatory with \*\)

> ### Restriction:  
> If you want to add *Additional Properties*, you must enter them manually.



</td>
</tr>
<tr>
<td valign="top">

*TargetSystem*\*

</td>
<td valign="top">

Splunk

</td>
</tr>
<tr>
<td valign="top">

*Source*

</td>
<td valign="top">

Any value, used to fill in the source attribute Splunk events.

</td>
</tr>
<tr>
<td valign="top">

*Host*

</td>
<td valign="top">

Any value, used to fill in the host attribute Splunk events.

</td>
</tr>
<tr>
<td valign="top">

*SourceType*

</td>
<td valign="top">

If the source type is specified, it's set to the defined value in Splunk events.

</td>
</tr>
<tr>
<td valign="top">

*DynamicSourceType*

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

*SourceTypePrefix*

</td>
<td valign="top">

If *DynamicSourceType* is true, and the *SourceTypePrefix* property is, the property value is prepended to the source type. For example: for a prefix of `Custom` and an MPL run event, the source type is to `CustomRun`.

</td>
</tr>
<tr>
<td valign="top">

*SubValuesInline*

</td>
<td valign="top">

If the property is set to `true`, values like custom header attributes and adapter attributes are added as JSON structures to the base `Run` event. This property is independent from the *SubValuesExtra* property.

</td>
</tr>
<tr>
<td valign="top">

*SubValuesExtra*

</td>
<td valign="top">

If the property is set to `true`, values like custom header attributes and adapter attributes are added as separate stand-alone events, following the base `Run` event. This property is independent of the `SubValuesInline` property.

</td>
</tr>
</table>

Then, to enable external logging, send a `POST` call to the following URL: `https://path-to-odata-api/api/v1/activateExternalLogging[?defaultLogLevel=(NONE|INFO|ERROR)]`, where the `path-to-odata-api` is specific to your environment. The optional parameter `defaultLogLevel` specifies the external logging level applied to existing and newly deployed integration flows. If this parameter is omitted or is *NONE*, then external logging doesn't take place, unless explicitly activated for a specific integration flow. If the log level is set to *INFO* or *ERROR* instead, MPLs for existing integration flows and newly deployed integration flows are immediately sent to the external system, unless the setting is explicitly changed for a specific Integration flow. You can change the default setting anytime by calling the activation API again. If external logging is already active, it takes up to 5 minutes for the new default level to take effect.

If the enabling of the external logging function is successful, you get a response code 200 and a message of success.

To check whether external logging is currently configured on a tenant, use the OData API allowing to query the message processing logs.

Send a `GET` call to the URL: `https://path-to-odata-api/api/v1/ExternalLoggingActivationStatus('tenant-name')`, where `path-to-odata-api` is specific to your environment. The parameter `tenant-name` doesn't specify the name of the tenant for which you check the status of the external logging function. The information about the tenant you want to check the logging status for, is taken from the security token used for the request.

You've to reload the *Monitor* to be able to see the external logging level options for your integration flows. If the enablement isn't successful, the system throws an error code as well as an error message.

If the external logging is activated,

1.  Go to the *Manage Integration* section.

2.  Choose the integration flow you want to have the external logging for.
3.  In the *Log Configuration* section, in addition to the standard *Log Level* you can set the *External Log Level*.
4.  You've 2-log level options to choose from: *Info* and *Error*.

After the successful activation of the external logging, you can deploy an integration flow and monitor it as usual.

The MPLs are sent to the Splunk server and you can browse for them in the Splunk destination. The MPLs sent to the external destination aren't stored in an SAP database, and SAP can't access them.

Internal and external log levels can be set independently.

> ### Note:  
> If an integration flow is undeployed, the external logging level is lost. You've to reconfigure the external logging level after redeployment of the integration flow.

**Disabling External Logging**

After activation, you can cancel the logging to an external destination by deactivating the external logging feature. To disable external logging, send a POST call to the following URL `https://path-to-odata-api/api/v1/deactivateExternalLogging`, where the `path-to-odata-api` is specific to your environment. If the disabling of the external logging function is successful, you get a response code 200 and a message of success.

After deactivation, no MPLs are sent to the external system. Logging configuration for deployed integration flows is retained and once activated again, the configured external logging level is restored to the value before deactivation.

**External Logging Status Information API**

We provide a status API to monitor the current status of external logging or diagnose errors in case external logging is disabled.

To retrieve status information , send a GET call to the following URL: `https://path-to-odata-api/api/v1/ExternalLoggingEvents` where the `path-to-odata-api` is specific to your environment. If external logging is activated, it returns a list of events that occurred in the last 14 days for these possible events:

-   External Logging was activated.

-   External logging was deactivated.
-   Errors causing failures in sending data to an external system.
-   Resuming sending data to an external system once an error is cleared.

If there are errors, the event carries the error reason as well as the error details received from the external system \(if available\).

