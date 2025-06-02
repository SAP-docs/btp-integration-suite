<!-- loioff3f9edc07344fa8a497dc4445ef7820 -->

# Amazon EventBridge Receiver Adapter

The Amazon EventBridge Receiver Adapter connects SAP Integration Suite to Amazon EventBridge. Amazon EventBridge is a serverless service that uses events to connect application components together.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loioff3f9edc07344fa8a497dc4445ef7820__section_qty_z21_tcc"/>

## How the Amazon EventBridge Receiver Adapter Works

If you have configured a Amazon EventBridge receiver adapter, the data exchange is performed as follows at runtime: SAP sends the request to Amazon EventBridge \(this is a receiver system\) through SAP Integration Suite. Amazon EventBridge works on the request and sends back the data to SAP.



<a name="loioff3f9edc07344fa8a497dc4445ef7820__section_ddl_ch1_tcc"/>

## Configuring the Amazon EventBridge Receiver Adapter

**Connection**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Region Name

</td>
<td valign="top">

Select the AWS Region where the S3 Bucket resides.

> ### Note:  
> If you are manually specifying this value, use `eu-central-1` instead of *eu-central-1 Europe \(Frankfurt\).*



</td>
</tr>
<tr>
<td valign="top">

Authentication Type

</td>
<td valign="top">

Select the authentication method. Currently, *Access Key and Secret Key* is used for authentication.

</td>
</tr>
<tr>
<td valign="top">

Access Key Alias

</td>
<td valign="top">

Specify the name of the Secure Parameter which stores the AWS Access Key.

</td>
</tr>
<tr>
<td valign="top">

Secret Key Alias

</td>
<td valign="top">

Specify the name of the Secure Parameter which stores the AWS Secret Key.

</td>
</tr>
<tr>
<td valign="top">

Connection Timeout \(in ms\)

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

Example: `6000`

</td>
</tr>
<tr>
<td valign="top">

Socket Timeout \(in ms\)

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message.

Example: `6000`

</td>
</tr>
</table>

**Processing**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Operation Type

</td>
<td valign="top">

Specify the type of operation to be performed. You can select from either of the two available options:

-   *Basic* allows you to send a single event to a single event bus.
-   *Advanced* allows you to send multiple events to multiple event buses.



</td>
</tr>
<tr>
<td valign="top">

Source

</td>
<td valign="top">

Specify the source of the event.

Example: `com.mycompany.myapp`

</td>
</tr>
<tr>
<td valign="top">

Resources

</td>
<td valign="top">

Specify the resources to be tagged to this event.

> ### Note:  
> Use comma separated values for multiple resources. These are AWS resources, identified by Amazon Resource Name \(ARN\), which the event primarily concerns. Any number, including zero, may be present.

Example: `resource1,resource2`

</td>
</tr>
<tr>
<td valign="top">

Detail Type

</td>
<td valign="top">

Specify the type of event.

Example: `Standard`

</td>
</tr>
<tr>
<td valign="top">

Bus Name

</td>
<td valign="top">

Specify the name of the event bus.

</td>
</tr>
<tr>
<td valign="top">

Detail

</td>
<td valign="top">

Specify the detail that needs to be sent to the event bus.

Example: `${in.body}`

</td>
</tr>
<tr>
<td valign="top">

Check if Bus Exists

</td>
<td valign="top">

Enable to validate the bus name for each entry in your payload.

</td>
</tr>
<tr>
<td valign="top">

Throw Exception on Failed Entry

</td>
<td valign="top">

Enable to check for the failed entries. In case of failures, an exception is thrown with failure count and failed entries.

</td>
</tr>
<tr>
<td valign="top">

Entries

\(Only available if *Advanced* is selected\)

</td>
<td valign="top">

Specify the entries that need to be sent to the event bus. This must be a JSON element.

> ### Sample Code:  
> ```
> {
>          "Source":"com.mycompany.myapp",
>          "Detail":"{ \"key1\": \"value1\", \"key2\": \"value2\" }",
>          "Resources":[
>             "resource1",
>             "resource2"
>          ],
>          "DetailType":"Standard"
>       },
>       {
>          "Source":"com.mycompany.myapp",
>          "Detail":"{ \"key1\": \"value3\", \"key2\": \"value4\" }",
>          "Resources":[
>             "resource1",
>             "resource2"
>          ],
>          "DetailType":"Custom"
>       }
>   ]
> }
> 
> ```



</td>
</tr>
<tr>
<td valign="top">

Request Headers

</td>
<td valign="top">

Enter a list of headers coming from the target system's response, separated by a pipe \(|\), to be received in the message. Use an asterisk\(\*\) to receive all the headers from the target system, which is also the default value.

</td>
</tr>
<tr>
<td valign="top">

Response Headers

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to send to the target system. By default, no custom headers are sent. Use an asterisk\(\*\) to send all custom headers to the target system. Alternatively, you can dynamically pass on the values by defining a property that includes a list of headers.

Default: `*`

</td>
</tr>
</table>

