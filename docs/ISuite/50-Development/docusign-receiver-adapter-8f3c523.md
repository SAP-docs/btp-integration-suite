<!-- loio8f3c5236a99f41b7a010289e1c298680 -->

# Docusign Receiver Adapter

The Docusign receiver adapter connects SAP Integration Suite to Docusign and facilitates data exchange between the two systems. The Docusign adapter enables you to manage and configure Docusign objects to integrate features like embedded sending, e-signatures, etc into your applications.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio8f3c5236a99f41b7a010289e1c298680__section_zgt_twd_zcc"/>

## How the Docusign Receiver Adapter Works

If you have configured a Docusign receiver adapter, the data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Docusign \(this is a receiver system\), Docusign works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio8f3c5236a99f41b7a010289e1c298680__section_ip2_sxd_zcc"/>

## Configure the Docusign Receiver Adapter

Once you have created a receiver channel and selected the Docusign adapter, you can configure its parameters as shown below:

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

Specify the address of Docusign to be used for the connection.

Example: `https://account.docusign.com`

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Specify the address of Docusign to be used for the connection:

-   *JSON Web Token \(JWT\)*
-   *OAuth 2.0 Authorization Code*



</td>
</tr>
<tr>
<td valign="top">

*Authentication Base URL*

</td>
<td valign="top">

Specify the name of the Secure Parameter artifact that contains the User ID needed to connect to Docusign.

</td>
</tr>
<tr>
<td valign="top">

*Client ID Alias*

</td>
<td valign="top">

Specify the Secure Parameter artifact that contains the Client ID needed to connect to Docusign.

</td>
</tr>
<tr>
<td valign="top">

*User ID Alias*

</td>
<td valign="top">

Specify the Secure Parameter artifact that contains the User ID needed to connect to Docusign.

</td>
</tr>
<tr>
<td valign="top">

*RSA Key Alias*

</td>
<td valign="top">

Specify the RSA key alias for connecting to the Docusign account.

</td>
</tr>
<tr>
<td valign="top">

*Authorization Code Credentials*

\(Only available when *OAuth 2.0 Authorization Code* is selected\)

</td>
<td valign="top">

Specify the Secure Parameter key alias that stores the Docusign OAuth Authorization Code.

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

The Processing tab contains all operation related configurations for the Docusign Receiver adapter.

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

Specify the entity on which the operation is to be performed.

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

Specify the file name of the resource being uploaded.

</td>
</tr>
<tr>
<td valign="top">

*Query Parameter*

</td>
<td valign="top">

Specify the expression containing the query parameter and value.

Example:`include_external_references,include_logos`

</td>
</tr>
<tr>
<td valign="top">

*Count*

</td>
<td valign="top">

Specify the maximum number of results to return.

Acceptable values range from 1 to 100.

</td>
</tr>
<tr>
<td valign="top">

*Start Position*

</td>
<td valign="top">

Specify the zero-based index of the result from which to start returning results.

</td>
</tr>
<tr>
<td valign="top">

*Resource Parameters*

</td>
<td valign="top">

Specify the *Name* and *Value* in case the resource path includes parameters.

Example: Set *Name* to `propertyKey` & *Value* to `76548`.

</td>
</tr>
<tr>
<td valign="top">

*Request*

</td>
<td valign="top">

Select the format for request payload.

</td>
</tr>
<tr>
<td valign="top">

*Response*

</td>
<td valign="top">

Select the format for response payload.

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to send to the target system. By default, no custom headers are sent. Use an asterisk \(\*\) to send all custom headers to the target system. Alternatively, you can dynamically pass on the values by defining a property that includes a list of headers.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers coming from the target system's response, separated by a pipe \(|\), to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value.

</td>
</tr>
</table>

