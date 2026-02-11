<!-- loio01bd8bb1ad2f44a48f160de6442dc672 -->

# Zendesk Receiver Adapter

Zendesk Receiver Adapter offers a comprehensive set of Ticketing CRUD \(Create, Read, Update and Delete\) operations for various entities such as Tickets, Attachments, Requests, Tags, etc.

Zendesk Adapter has the following features:

-   Supports secure authentication mechanisms like API Token and OAuth2 Client Credentials.
-   Supports Basic configuration type that provides a convenient processing capability for supported versions, whereas Advanced enables proficient users to perform calls with greater control while connecting to any API endpoint.
-   Utilise the Upload File operation to upload multiple files using a single token.
-   Create Many Tickets operation allows you to create tickets in bulk.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



## How the Zendesk Receiver Adapter Works

-   The Zendesk Receiver adapter is designed to receive and process data from an integration flow in SAP Integration Suite and facilitate communication with Zendesk application \(external\) using REST-based APIs.
-   SAP Integration Suite acts as the initiator of the calls and sends a request to Zendesk \(this is the receiver system\) using the adapter.
-   Additionally, the adapter also handles responses and logs execution status and errors before returning them to SAP Integration Suite.



## Configure the Zendesk Receiver Adapter

Once you have created a receiver channel and selected the Zendesk Receiver Adapter, you can configure its parameters as shown below:

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

Specify the Zendesk address.

Example: `https://YourDomain.zendesk.com`

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the required authentication mechanism to be used:

-   *API Token*
-   *OAuth2 Client Credentials*



</td>
</tr>
<tr>
<td valign="top">

*User Name*

\(Only available when *Authentication Type* is *API Token*\)

</td>
<td valign="top">

Specify the email address associated with your Zendesk account.

</td>
</tr>
<tr>
<td valign="top">

*API Token Alias*

\(Only available when *Authentication Type* is *API Token*\)

</td>
<td valign="top">

Specify the Secure Parameter alias that stores the Zendesk API token.

</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

\(Only available when *Authentication Type* is *OAuth Client Credentials*\)

</td>
<td valign="top">

Specify the OAuth 2.0 Client Credentials alias that stores the Client ID and Client Secret.

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable to reuse the connection.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting in milliseconds for the connection to be established.

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

\(Only available when the *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Select the entity based on which the operation will be performed.

</td>
</tr>
<tr>
<td valign="top">

*Operation*

\(Only available when the *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Select the required operation from the dropdown.

</td>
</tr>
<tr>
<td valign="top">

*Operation Parameters*

</td>
<td valign="top">

Specify the operation parameters as a key-value pair.

*Name*: `ticket_id`

*Value*: `54`

</td>
</tr>
<tr>
<td valign="top">

*HTTP Method*

\(Only available when the *Configuration Type* is *Advanced*\)

</td>
<td valign="top">

Select the required method from the available dropdown:

-   *DELETE*
-   *GET*
-   *PUT*
-   *POST*
-   *PATCH*



</td>
</tr>
<tr>
<td valign="top">

*Relative URL*

\(Only available when the *Configuration Type* is *Advanced*\)

</td>
<td valign="top">

Specify the relative endpoint, excluding the Host.

Example: `/api/v2/tickets.json`

</td>
</tr>
<tr>
<td valign="top">

*Query*

</td>
<td valign="top">

Specify the expression containing the query parameter and value.

Example: `param1=value1&param2=value2`

> ### Note:  
> While using space \( \), ensure that you encode the query using %20



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

