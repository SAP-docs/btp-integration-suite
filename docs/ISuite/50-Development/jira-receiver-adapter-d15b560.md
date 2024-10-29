<!-- loiod15b560938c9446fbd9eb0ce84282fb0 -->

# Jira Receiver Adapter

The Jira receiver adapter connects SAP Integration Suite to Jira. The Jira adapter helps you exchange data between the two systems. Jira is a versatile software with multiple offerings like issue tracking, bug management, and agile project management.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loiod15b560938c9446fbd9eb0ce84282fb0__section_zgt_twd_zcc"/>

## How the Jira Receiver Adapter Works

If you have configured a Jira receiver adapter, the data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Jira \(this is a receiver system\), Jira works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loiod15b560938c9446fbd9eb0ce84282fb0__section_ip2_sxd_zcc"/>

## Configure the Jira Receiver Adapter

Once you have created a receiver channel and selected the Jira adapter, you can configure its parameters by referring the following description:

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

Specify the login endpoint to your Jira endpoint url.

Example: `https://your-domain.atlassian.net`

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select *Basic* to use simple authentication to connect to the Jira endpoint with a username and password.

</td>
</tr>
<tr>
<td valign="top">

*Basic Credentials Alias*

</td>
<td valign="top">

Specify the user credential to be stored as a security artifact in *Security Material*.

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

Example: 6000

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message.

Example: 6000

</td>
</tr>
</table>

The Processing tab contains all operation related configurations for the Jira Receiver adapter.

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

*API Version*

</td>
<td valign="top">

Select the API version of the Jira Adapter.

</td>
</tr>
<tr>
<td valign="top">

*Entity*

</td>
<td valign="top">

Select the type of entity in Jira.

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

*Resource Parameters*

</td>
<td valign="top">

Specify the parameter name and value in case resource path includes parameters.

Example: Set *Name* to `propertyKey` and *Value* to `23434`.

</td>
</tr>
<tr>
<td valign="top">

*Query Parameter*

</td>
<td valign="top">

Specify the expression containing the query parameter and value.

Example: `fields=summary,comment&properties=*all`

</td>
</tr>
<tr>
<td valign="top">

*Attachment*

</td>
<td valign="top">

Specify the filename containing the attachment.

</td>
</tr>
<tr>
<td valign="top">

*Start At*

</td>
<td valign="top">

Specify the index of the first item returned in the page.

> ### Note:  
> A value of `0` indicates a start from the first page.

Example: `5`

</td>
</tr>
<tr>
<td valign="top">

*Max Results*

</td>
<td valign="top">

Specify the maximum number of items that a page can return. Each operation can have a different limit for the number of items returned and these limits may change without notice.

Example: `45`

</td>
</tr>
<tr>
<td valign="top">

*JQL Query*

</td>
<td valign="top">

Specify the value of the Jira Query Language parameters.

Example: `created >= -30d AND project = STP ORDER BY created DESC`

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Specify a list of custom headers, separated by a pipe \(|\), to be sent to the target system. Use an asterisk \(\*\) to send all custom headers to the target system.

> ### Note:  
> All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them.



</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Specify a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value.

> ### Note:  
> All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them.



</td>
</tr>
</table>

