<!-- loio30df22d1f7c3429a846efb1e3653fbbc -->

# Configure the Google Pub/Sub Receiver Adapter

Google Pub/Sub Receiver adapter allows reliable publishing of messages to Google Pub/Sub.



<a name="loio30df22d1f7c3429a846efb1e3653fbbc__section_wqx_dwk_22c"/>

## How the Google Pub/Sub Receiver Adapter Works

If you have configured the Google Pub/Sub receiver adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Google Pub/Sub \(this is a receiver system\), Google Pub/Sub works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio30df22d1f7c3429a846efb1e3653fbbc__section_okv_pxk_22c"/>

## Configure the Google Pub/Sub Sender Adapter

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

*Address*

</td>
<td valign="top">

Specify the hostname pointing to the Google Pub/Sub service.

Example: `https://pubsub.googleapis.com`

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the method for authentication to Google Pub/Sub. Currently *Currently OAuth2 Service Account* is supported.

</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Token URL*

</td>
<td valign="top">

Specify the OAuth2 Token URL which identifies as the authorization server for producing a JWT token internally.

Example: `https://www.googleapis.com/oauth2/v4/token`

</td>
</tr>
<tr>
<td valign="top">

*Client Email*

</td>
<td valign="top">

Specify the Google Service Account Client Email.

Example: `limited-svcaccount@192843.iam.gserviceaccount`

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias*

</td>
<td valign="top">

Specify the alias for Google Service Account Private Key for authentication.

</td>
</tr>
<tr>
<td valign="top">

*Scope*

</td>
<td valign="top">

Specify the scope of the connection to Google Pub/Sub service.

Default: `https://www/googleapis/auth/pubsub`

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable this property to reuse the connection.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established with Google Pub/Sub service.

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received with Google Pub/Sub service.

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

Descriptions

</th>
</tr>
<tr>
<td valign="top">

*Entity*

</td>
<td valign="top">

Select the entity for message processing:

-   *Topics*
-   *Subscriptions*



</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Select the operation to be performed.

</td>
</tr>
<tr>
<td valign="top">

*Project ID*

</td>
<td valign="top">

Specify the Google Pub/Sub project ID.

</td>
</tr>
<tr>
<td valign="top">

*Topic ID*

</td>
<td valign="top">

Specify the Topic ID to be used.

</td>
</tr>
<tr>
<td valign="top">

*Operation Type*

</td>
<td valign="top">

Select the type of operation when *Operation* is set to *Publish Message*.

</td>
</tr>
<tr>
<td valign="top">

*Encode Data*

</td>
<td valign="top">

Enable to encode data to Base64.

> ### Note:  
> Google Pub/Sub can only accept Base64 encoded data. If not enabled data must be converted to Base64 before using the adapter.



</td>
</tr>
<tr>
<td valign="top">

*Ordering Key*

</td>
<td valign="top">

Specify the ordering key for this message.

> ### Note:  
> For subscriptions with message ordering enabled, messages with the same ordering key are sent in the order in which they were published.



</td>
</tr>
<tr>
<td valign="top">

*Subscription ID*

</td>
<td valign="top">

Specify the Subscription ID.

</td>
</tr>
<tr>
<td valign="top">

*Acknowledgement ID*

</td>
<td valign="top">

Specify the Acknowledgement ID for the messages being used.

</td>
</tr>
<tr>
<td valign="top">

*Acknowledgement Deadline \(in sec\)*

</td>
<td valign="top">

Specify the new acknowledgement deadline with respect to the time when this request is sent to the Google Pub/Sub system.

Example: `5`

</td>
</tr>
<tr>
<td valign="top">

*Page Size*

</td>
<td valign="top">

Specify the maximum number of topics to be returned.

Example: `10`

</td>
</tr>
<tr>
<td valign="top">

*Page Token*

</td>
<td valign="top">

Specify the value returned by the last ListTopicsResponse; indicates that this is a continuation of a prior topics.list call, and that the system should return the next page of data.

> ### Note:  
> A value of null or an empty string retrieves the first page.



</td>
</tr>
<tr>
<td valign="top">

*Message Attributes*

</td>
<td valign="top">

Specify multiple message attributes as key value pairs.

Example: Set *Key* to `status` and *Value* to `end of message`

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), that you want to send to the target system. By default, no custom headers are sent.

Alternatively, use an \* to send all custom headers to the target system.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers coming from the target system's response, separated by a pipe \(|\), to be received in the message. Use an \* to receive all the headers from the target system, which is also the default value.

</td>
</tr>
</table>

