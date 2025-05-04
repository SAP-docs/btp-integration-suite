<!-- loio45610e7b33144b7e9ea81e6cd536519e -->

# Configure the IBM MQ \(REST\) Receiver Adapter

IBM MQ Receiver Adapter allows reliable and convenient publishing of messages to IBM MQ.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio45610e7b33144b7e9ea81e6cd536519e__aeq30223"/>

## How the IBM MQ Receiver Adapter Works

If you have configured the IBM MQ Receiver Adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to IBM MQ \(this is a receiver system\), IBM MQ Receiver Adapter works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio45610e7b33144b7e9ea81e6cd536519e__sec_3t4_rdc"/>

## Configure the IBM MQ Receiver Adapter

Once you have created a receiver channel and selected the IBM MQ Receiver Adapter, you can configure its parameters as shown below:

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

Specify the address of the IBM MQ endpoints.

Example: `https://web-{hostname}`

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select the type of authentication for connecting to IBM MQ:

-   *Basic*
-   *Token-Based*



</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the User Credential that stores the username-password pair.

</td>
</tr>
<tr>
<td valign="top">

*Proxy Type*

</td>
<td valign="top">

Select the proxy type:

-   *Internet*
-   *On-Premise*



</td>
</tr>
<tr>
<td valign="top">

*Location ID* 

</td>
<td valign="top">

Specify the location ID from the Cloud Connector.

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

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received.

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

*Operation*

</td>
<td valign="top">

Select the type of operation to be performed.

</td>
</tr>
<tr>
<td valign="top">

*API Version*

</td>
<td valign="top">

Select the API version.

</td>
</tr>
<tr>
<td valign="top">

*Queue Manager Name*

</td>
<td valign="top">

Specify the name of the queue manager to connect to for messaging.

</td>
</tr>
<tr>
<td valign="top">

*Queue Name*

</td>
<td valign="top">

Specify the name of the queue from where message is read.

</td>
</tr>
<tr>
<td valign="top">

*Content Type*

</td>
<td valign="top">

Select the Parameter content type:

-   *Application/JSON*
-   *Application/XML*
-   *Text/HTML*
-   *Text/Plain*
-   *Text/XML*

    > ### Note:  
    > This field is editable and can be used for any other content types supported by IBM MQ.




</td>
</tr>
<tr>
<td valign="top">

*MQ CSRF Token*

</td>
<td valign="top">

Specify the CSRF protection header. The value can be any valid string \(including a blank string\).

</td>
</tr>
<tr>
<td valign="top">

*MQ Correlation ID* 

</td>
<td valign="top">

Specify the correlation ID which is a 48 character hexadecimal encoded string, representing 24 bytes.

Example: `414d5120514d4144455620202020202067d8bf5923582e02`.

> ### Note:  
> -   If *API Version* is set as `v3`, prefix hex-string with `ID:` as `ID:414d5120514d4144455620202020202067d8bf5923582e02`.
> -   You can also specify an application-specific value can also be specified, as `My Custom CorelID`. This sets the correlation ID of the created message.



</td>
</tr>
<tr>
<td valign="top">

*Message ID*

</td>
<td valign="top">

Specify the message ID which is a 48 character hexadecimal encoded string representing 24 bytes.

</td>
</tr>
<tr>
<td valign="top">

*Message Expiry*

</td>
<td valign="top">

Specify the maximum time to keep the message on the queue, in milliseconds \(Limited to the range 0-99999999900\). The default value is `unlimited` which specifies that the message does not expire.

</td>
</tr>
<tr>
<td valign="top">

*Message Persistence*

</td>
<td valign="top">

Select the message persistence:

-   *Persistent*
-   *Non Persistent*

The default value is *Non Persistent* which indicates that the message does not survive system failures or queue manager restarts.

</td>
</tr>
<tr>
<td valign="top">

*Reply Queue*

</td>
<td valign="top">

Specify the reply-to destination for the created message. The format of the header uses the standard notation of supplying the reply-to queue and an optional queue manager.

Example: `replyQueue[@replyQmgr]`

</td>
</tr>
<tr>
<td valign="top">

*Message Priority*

</td>
<td valign="top">

Specify the message priority between the range 0-9.

The default value is `asDestination` which specifies that the message uses the priority specified in the DEFPRTY attribute of the underlying IBM MQ queue object.

</td>
</tr>
<tr>
<td valign="top">

*User Properties*

</td>
<td valign="top">

Specify the user defined properties for the message in the format property\_name; user\_value; user\_type. For multiple user properties use comma separator.

Example: `myA;5;byte,myB;-10;integer`

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to send to the target system. By default, no custom headers are sent. Use an asterisk\(\*\) to send all custom headers to the target system. Alternatively, you can dynamically pass on the values by defining a property that includes a list of headers.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers coming from the target system's response, separated by a pipe \(|\), to be received in the message. Use an asterisk\(\*\) to receive all the headers from the target system, which is also the default value.

</td>
</tr>
</table>

