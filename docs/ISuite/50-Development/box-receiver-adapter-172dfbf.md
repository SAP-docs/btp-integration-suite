<!-- loio172dfbf4fae7463da0d404392eae864f -->

# Box Receiver Adapter

The Box Receiver adapter connects SAP Integration Suite to Box. The Box Receiver adapter enables you to access components on Box.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio172dfbf4fae7463da0d404392eae864f__section_zgt_twd_zcc"/>

## How the Box Receiver Adapter Works

If you have configured a Box receiver adapter, the data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Box \(this is a receiver system\), Box works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio172dfbf4fae7463da0d404392eae864f__section_ip2_sxd_zcc"/>

## Configure the Box Receiver Adapter

Once you have created a receiver channel and selected the Box adapter, you can configure its parameters as shown below:

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

Specify the address to connect to Box. Ensure that you specify the address corresponding to the operation as different operations might have different addresses.

Example:

-   `https://account.box.com`
-   `https://upload.box.com`



</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the required authentication type to be used. Currently *OAuth Client Credentials* is supported.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

Specify the name of OAuth2 Client Credentials artifact that stores the client secret \(Client Credentials Grant\).

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable to reuse the connection. This option enables the reuse of connection objects from the internal connection pool which in turn improves the network turnaround time for multiple communications to a same end point.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established.

Example: `6000`

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message.

Example: `60000`

</td>
</tr>
</table>

The Processing tab contains all operation related configurations for the Box Receiver adapter.

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

*Configuration Type*

</td>
<td valign="top">

Select the required configuration type:

-   *Basic* to use the dropdowns and parameter text fields.
-   *Advanced* to specify the relative URL.



</td>
</tr>
<tr>
<td valign="top">

*Entity*

</td>
<td valign="top">

Specify the entity based on which the operation is to be performed.

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

*File Name*

</td>
<td valign="top">

Specify the name of the file. The file name must be unique within its parent folder.

Example: `readme.txt`

</td>
</tr>
<tr>
<td valign="top">

*Parent ID*

</td>
<td valign="top">

Specify the ID of the parent folder to upload the file to it.

> ### Note:  
> Use 0 to specify user's root folder.



</td>
</tr>
<tr>
<td valign="top">

*Operation Parameters*

</td>
<td valign="top">

Specify the operation parameters as a key value pair.

</td>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Specify the key for the operation parameter.

Example: `file_id`

</td>
</tr>
<tr>
<td valign="top">

*Value*

</td>
<td valign="top">

Specify the key for the operation parameter.

Example: `131231233`

</td>
</tr>
<tr>
<td valign="top">

*HTTP Method*

</td>
<td valign="top">

Select the required HTTP method from the available dropdown:

-   *DELETE*
-   *GET*
-   *PATCH*
-   *POST*
-   *PUT*



</td>
</tr>
<tr>
<td valign="top">

*Relative URL*

</td>
<td valign="top">

Specify the endpoint path, excluding the Host.

Example: `/2.0/search`

</td>
</tr>
<tr>
<td valign="top">

*Query*

</td>
<td valign="top">

Specify the query that should be transferred with the HTTP request.

Example: `param1=value1&param2=value2`

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Specify a list of custom headers, separated by a pipe \(|\), to be sent to the target system. Use an asterisk \(\*\) to send all custom headers to the target system. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Specify a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value.

All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them.

</td>
</tr>
</table>

