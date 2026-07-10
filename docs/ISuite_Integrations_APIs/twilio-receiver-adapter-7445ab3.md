<!-- loio7445ab37916742dd86d4a82a86f53bc3 -->

# Twilio Receiver Adapter

The Twilio Adapter for SAP Integration Suite enables seamless connectivity with Twilio, allowing you to access Twilio services and perform actions such as sending and receiving messages, managing voice calls, tracking communication status, and automating customer engagement workflows.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio7445ab37916742dd86d4a82a86f53bc3__section_wqx_dwk_22c"/>

## How the Twilio Receiver Adapter Works

-   The Twilio Receiver adapter is designed to receive and process data from an integration flow in SAP Integration Suite and facilitate communication with Twilio application \(external\) using REST-based APIs.
-   SAP Integration Suite acts as the initiator of the calls and sends a request to Twilio \(this is the receiver system\) using the adapter.
-   Additionally, the adapter also handles responses and logs.



<a name="loio7445ab37916742dd86d4a82a86f53bc3__section_okv_twi_22c"/>

## Configure the Twilio Receiver Adapter

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

Specify the address to connect to Twilio.

Example: `https://api.twilio.com`

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the authentication type to connect to the Twilio server:

-   *API Key*
-   *Auth Token*



</td>
</tr>
<tr>
<td valign="top">

*Credential Name*

</td>
<td valign="top">

-   When *Authentication Type* is set to *API Key,* specify User Credentials that store the SID and Secret.

-   When *Authentication Type* is set to *Auth Token,* specify the User Credentials artifacts that store the Account SID and Auth token.



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

> ### Note:  
> -   For *Basic* configuration type, the body must be provided in JSON.
> -   For *Advanced* configuration type, the body must be provided in *application/x-www-formurlencoded*.



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

*Next Page URI*

\(Only available when *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Specify the next page URI.

Example: `/2010-04-01/Accounts/ACXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX/Messages.json?PageSize=50&PageToken=PASMxxxxx2bfbxxxxxb1cf11a002exxxxxx&Page=`

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

Example: `/2010-04-01/Accounts/ACXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX/Messages`

</td>
</tr>
<tr>
<td valign="top">

*Send Body*

\(Only available when *Configuration Type* is *Advanced*\)

</td>
<td valign="top">

Enable to send the body of the message with the request.

> ### Note:  
> For methods GET and DELETE, the body isn't sent by default.



</td>
</tr>
<tr>
<td valign="top">

*Query*

</td>
<td valign="top">

Specify the expression containing the query parameter and value.

> ### Note:  
> While using space\(``\), ensure that you encode the query using %20



</td>
</tr>
<tr>
<td valign="top">

*Response Format*

</td>
<td valign="top">

Select the payload format of the response body.

-   *Application/XML*
-   *Application/JSON*
-   *Text/CSV*



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

Enter a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them. Note that this value can also be read dynamically using an exchange header or property.

</td>
</tr>
</table>

