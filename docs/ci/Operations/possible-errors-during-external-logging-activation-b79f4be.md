<!-- loiob79f4beba1ef49a8bde27fdb025436e8 -->

# Possible Errors During External Logging Activation

When activating external logging, different errors can occur.

Find below the different error situations and the error messages senr back by the OData API.


<table>
<tr>
<th valign="top">

Error Situation

</th>
<th valign="top">

Error Message and Response Body

</th>
</tr>
<tr>
<td valign="top">

No destination with the name `CloudIntegration_MonitoringDataConsumer` was found in the subaccount's destination configuration.

</td>
<td valign="top">

`Retrieving Destination failed. Destination with name CloudIntegration_MonitoringDataConsumer does not exist.` 

</td>
</tr>
<tr>
<td valign="top">

An error occured with the configuration of the destination. The error is returned in the `<DESTINATION_ERROR>` element. Common issues are missing mandatory parameters and invalid values in free-form parameters.

</td>
<td valign="top">

```
{
  "result": "ERROR",
  "message": "<DESTINATION_ERROR>",
  "infos": [
    {
      "description": "Read Tenant Information",
      "result": "SUCCESS",
      "dataSent": "",
      "dataReceived": ""
    },
    {
      "description": "Validating Connection Settings",
      "result": "ERROR",
      "dataSent": "",
      "dataReceived": "<DESTINATION_ERROR>"
    }
  ]
}
```



</td>
</tr>
<tr>
<td valign="top">

A problem occurred when connecting to the Splunk system. The error is returned in the`<ERROR_MESSAGE>` element. Common errors include DNS issues, configuration issues with Cloud Connector and firewall configuration problems.

</td>
<td valign="top">

```
{
  "result": "ERROR",
  "message": "<ERROR_MESSAGE>",
  "infos": [
    {
      "description": "Read Tenant Information",
      "result": "SUCCESS",
      "dataSent": "",
      "dataReceived": ""
    },
    {
      "description": "Validating Connection Settings",
      "result": "SUCCESS",
      "dataSent": "",
      "dataReceived": "All Settings Valid"
    },
    {
      "description": "Instantiating Selected Adapter",
      "result": "SUCCESS",
      "dataSent": "",
      "dataReceived": "Adapter Created"
    },
    {
      "description": "Calling OPTIONS on endpoint",
      "result": "ERROR",
      "dataSent": "OPTIONS /services/collector/event",
      "dataReceived": "<ERROR_MESSAGE>"
    }
  ]
}
```



</td>
</tr>
<tr>
<td valign="top">

A problem occurred when sending events to the target Splunk system after a successful configuration. The error message is returned in the `<SPLUNK_ERROR>` element. This message typically indicates a problem with the Splunk target instance or a mismatch of Splunk and destination configuration.

</td>
<td valign="top">

```
{
  "result": "ERROR",
  "message": "<SPLUNK_ERROR>",
  "infos": [
    {
      "description": "Read Tenant Information",
      "result": "SUCCESS",
      "dataSent": "",
      "dataReceived": ""
    },
    {
      "description": "Validating Connection Settings",
      "result": "SUCCESS",
      "dataSent": "",
      "dataReceived": "All Settings Valid"
    },
    {
      "description": "Instantiating Selected Adapter",
      "result": "SUCCESS",
      "dataSent": "",
      "dataReceived": "Adapter Created"
    },
    {
      "description": "Calling OPTIONS on endpoint",
      "result": "SUCCESS",
      "dataSent": "OPTIONS /services/collector/event",
      "dataReceived": "200"
    },
    {
      "description": "Polling Splunk HTTP Event Collector Endpoint",
      "result": "ERROR",
      "dataSent": "POST /services/collector/event",
      "dataReceived": "<SPLUNK_ERROR>"
    }
  ]
}
```



</td>
</tr>
</table>

