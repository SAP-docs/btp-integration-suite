<!-- loioe73852e5cebf40558eb5903195e214b8 -->

# Adobe Sign Receiver Adapter

Adobe Sign Receiver Adapter for SAP Integration Suite allows you to connect to Adobe Sign to access APIs related to Agreement, Library Documents, and Message Templates, etc.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loioe73852e5cebf40558eb5903195e214b8__section_wqx_dwk_22c"/>

## How the Adobe Sign Receiver Adapter Works

-   The Adobe Sign Receiver adapter is designed to receive and process data from an integration flow in SAP Integration Suite and facilitate communication with Adobe Sign application \(external\) using REST-based APIs.
-   SAP Integration Suite acts as the initiator of the calls and sends a request to Adobe Sign \(this is the receiver system\) using the adapter.
-   Additionally, the adapter also handles responses and logs execution status and errors before returning them to SAP Integration Suite.



<a name="loioe73852e5cebf40558eb5903195e214b8__section_okv_pxk_22c"/>

## Configure the Adobe Sign Receiver Adapter

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

Specify the Adobe Sign Address.

Example: `https://api.eu2.adobesign.com`

</td>
</tr>
<tr>
<td valign="top">

*Key Alias Name*

</td>
<td valign="top">

Specify the Secure Parameter Alias that stores the Integration Key to connect to Adobe Sign.

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

Example: `60000`

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

-   *Basic* for convenient processing capability using dropdowns and parameter text fields.
-   *Advanced* enables proficient users to perform calls with greater control while connecting to any API endpoint.



</td>
</tr>
<tr>
<td valign="top">

*Entity*

\(Only available when *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Select the entity based on which the operation will be performed.

</td>
</tr>
<tr>
<td valign="top">

*Operation*

\(Only available when *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Select the operation to be performed.

</td>
</tr>
<tr>
<td valign="top">

*Operation Parameters*

\(Only available when *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Specify the operation parameters as a name value pair.

*Name*: `file`

*Value*: `readme.txt`

</td>
</tr>
<tr>
<td valign="top">

*Cursor*

\(Only available when *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Specify the cursor value as the starting point for retrieving the items. If not provided, the first page is returned.

</td>
</tr>
<tr>
<td valign="top">

*Page Size*

\(Only available when *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Specify the maximum number of items to be returned per page.

Example: `50`

</td>
</tr>
<tr>
<td valign="top">

*Request Payload Source*

\(Only available when *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Select an option to specify the source for request payload:

-   *UI Configurable* provides user-friendly fields to create the payload automatically.
-   *Exchange Body* allows you to specify the required structure and values.



</td>
</tr>
<tr>
<td valign="top">

*File Name*

\(Only available when *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Specify the name of the file along with the extension.

Example: `readme.txt`

</td>
</tr>
<tr>
<td valign="top">

*Mime-Type*

\(Only available when *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Specify the content type of the document being uploaded.

Example: `application/json`

</td>
</tr>
<tr>
<td valign="top">

*HTTP Method*

\(Only available when *Configuration Type* is *Advanced*\)

</td>
<td valign="top">

Select the required method from the available dropdown:

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

\(Only available when *Configuration Type* is *Advanced*\)

</td>
<td valign="top">

Specify the relative endpoint, excluding the Host.

Example: `/api/rest/v6/agreements`

</td>
</tr>
<tr>
<td valign="top">

*Enable Payload as Request Body*

\(Only available when *Configuration Type* is *Advanced*\)

</td>
<td valign="top">

Select to pass the payload as the request body.

> ### Note:  
> In Content Modifier, set header as content-type = application/json



</td>
</tr>
<tr>
<td valign="top">

*Query*

</td>
<td valign="top">

Specify the expression containing the query parameter and value.

> ### Note:  
> While using space \( \), ensure that you encode the query using %20 `jobId=34&applicationStatus=ALL&searchString=john.doe@gmail.com&newSince=2025-11-01%2013:00:00`



</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to be sent to the target system. Use an asterisk \(\*\) to send all custom headers to the target system. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property

</td>
</tr>
</table>

