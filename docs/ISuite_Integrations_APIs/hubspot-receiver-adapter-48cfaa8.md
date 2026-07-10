<!-- loio48cfaa8e109d46489c620c8125e8a1a9 -->

# HubSpot Receiver Adapter

The HubSpot Receiver adapter connects SAP Integration Suite to HubSpot. HubSpot is a dynamic platform enabling seamless integration across departments such as marketing, sales, and customer service. The HubSpot adapter helps you exchange data between the two systems.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio48cfaa8e109d46489c620c8125e8a1a9__section_gfd_dh1_fdc"/>

## How the HubSpot Receiver Adapter Works

If you have configured the HubSpot receiver adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to HubSpot \(this is a receiver system\), HubSpot works on the request and sends the data back to the SAP Integration Suite tenant.



<a name="loio48cfaa8e109d46489c620c8125e8a1a9__section_xw1_lh1_fdc"/>

## Configure the HubSpot Receiver Adapter

Once you have created a receiver channel and selected the HubSpot adapter, you can configure its parameters as shown below:

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

Specify the recipient’s endpoint URL.

Example: `https://api.hubapi.com`

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

Select an authentication method from the below options.

-   *OAuth2 Authorization Code* uses authorization tokens rather than a password to connect your app to a user account.
-   *Private App* allows you to use HubSpot's APIs to access specific data from your HubSpot account.



</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Credential Alias*

\(Only available if *Authentication* is *OAuth2 Authorization Code*\)

</td>
<td valign="top">

Specify the OAuth2 authorization alias which generates the token.

</td>
</tr>
<tr>
<td valign="top">

*Token Alias*

\(Only available if *Authentication* is *Private App*\)

</td>
<td valign="top">

Specify the token alias which stores the private app's access token.

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

This option enables the reuse of connection objects from the internal connection pool which in turn improves the network turnaround time for multiple communications to a same end point.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established with HubSpot.

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response message to be received from HubSpot.

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

Select the configuration type from the available options. You can select:

-   *Basic* to use the dropdowns and parameter text fields.
-   *Advanced* to provide the relative URL \(endpoint excluding the host\).



</td>
</tr>
<tr>
<td valign="top">

*API Version*

</td>
<td valign="top">

Select the version of the API to be used for this interaction with HubSpot.

</td>
</tr>
<tr>
<td valign="top">

*Category*

</td>
<td valign="top">

Select the required Category.

</td>
</tr>
<tr>
<td valign="top">

*Entity*

</td>
<td valign="top">

Specify the HubSpot Entity based on which the operation will be performed.

</td>
</tr>
<tr>
<td valign="top">

*Operation*

</td>
<td valign="top">

Specify the type of action to be executed.

</td>
</tr>
<tr>
<td valign="top">

*Relative URL*

</td>
<td valign="top">

Specify the endpoint path, excluding the Host.

Example: `/crm/v3/objects/contacts`

</td>
</tr>
<tr>
<td valign="top">

*HTTP Method*

</td>
<td valign="top">

Select the HTTP Method.

</td>
</tr>
<tr>
<td valign="top">

*Entity ID*

</td>
<td valign="top">

Specify the Entity ID corresponding to the Entity selected in the drop-down above.

Example: For Entity `Contacts`, specify the contact ID.

</td>
</tr>
<tr>
<td valign="top">

*From Object Type*

</td>
<td valign="top">

Specify the value of the object that you are associating with.

</td>
</tr>
<tr>
<td valign="top">

*To Object Type*

</td>
<td valign="top">

Specify the value of the object you are associating the record to.

</td>
</tr>
<tr>
<td valign="top">

*Object Type*

</td>
<td valign="top">

Specify the value for Object Type.

</td>
</tr>
<tr>
<td valign="top">

*Object ID*

</td>
<td valign="top">

Specify the value for Object ID .

</td>
</tr>
<tr>
<td valign="top">

*To Object ID*

</td>
<td valign="top">

Specify the ID of the record to associate to.

</td>
</tr>
<tr>
<td valign="top">

*From Object ID*

</td>
<td valign="top">

Specify the ID of the record to associate with.

</td>
</tr>
<tr>
<td valign="top">

*App ID*

</td>
<td valign="top">

Specify the value for App ID.

</td>
</tr>
<tr>
<td valign="top">

*Task ID*

</td>
<td valign="top">

Specify the value for Task ID.

</td>
</tr>
<tr>
<td valign="top">

*Event Template ID*

</td>
<td valign="top">

Specify the value for Event Template ID.

</td>
</tr>
<tr>
<td valign="top">

*Event ID*

</td>
<td valign="top">

Specify the value for Event ID.

</td>
</tr>
<tr>
<td valign="top">

*Token Name*

</td>
<td valign="top">

Specify the value for Token Name.

</td>
</tr>
<tr>
<td valign="top">

*Group Name*

</td>
<td valign="top">

Specify the value for group name corresponding to the operation chosen above.

</td>
</tr>
<tr>
<td valign="top">

*Property Name*

</td>
<td valign="top">

Specify the value for property name corresponding to the operation chosen above.

</td>
</tr>
<tr>
<td valign="top">

*Stage ID*

</td>
<td valign="top">

Specify the value for Stage ID.

</td>
</tr>
<tr>
<td valign="top">

*Source List ID*

</td>
<td valign="top">

Specify the value for Source List ID.

</td>
</tr>
<tr>
<td valign="top">

*Revision ID*

</td>
<td valign="top">

Specify the value for Revision ID.

</td>
</tr>
<tr>
<td valign="top">

*Blog ID*

</td>
<td valign="top">

Specify the value for Blog ID.

</td>
</tr>
<tr>
<td valign="top">

*Table ID or Table Name*

</td>
<td valign="top">

Specify the value for Table ID or Table Name.

</td>
</tr>
<tr>
<td valign="top">

*Version ID*

</td>
<td valign="top">

Specify the value for Version ID.

</td>
</tr>
<tr>
<td valign="top">

*Media type*

</td>
<td valign="top">

Specify the value for Media Type.

Example: `IMAGE`

</td>
</tr>
<tr>
<td valign="top">

*oEmbed Domain Id*

</td>
<td valign="top">

Specify the value for oEmbed Domain ID.

</td>
</tr>
<tr>
<td valign="top">

*Path*

</td>
<td valign="top">

Specify the value for Path.

</td>
</tr>
<tr>
<td valign="top">

*Content ID*

</td>
<td valign="top">

Specify the value for Content ID.

</td>
</tr>
<tr>
<td valign="top">

*Environment*

</td>
<td valign="top">

Specify the value for Environment.

Example: `draft`

</td>
</tr>
<tr>
<td valign="top">

*User ID*

</td>
<td valign="top">

Specify the value for User ID.

</td>
</tr>
<tr>
<td valign="top">

*Folder Path*

</td>
<td valign="top">

Specify the value for Folder Path.

</td>
</tr>
<tr>
<td valign="top">

*Folder ID*

</td>
<td valign="top">

Specify the value for Folder ID.

</td>
</tr>
<tr>
<td valign="top">

*File Name*

</td>
<td valign="top">

Specify the value for File Name.

</td>
</tr>
<tr>
<td valign="top">

*File Content Type*

</td>
<td valign="top">

Select the value for media format.

Example: `application/pdf` or `text/plain`

</td>
</tr>
<tr>
<td valign="top">

*Options*

</td>
<td valign="top">

Specify a JSON object for file privacy and indexability. Note that this value can also be read dynamically.

Example: `{"access": "PUBLIC_INDEXABLE"}`

</td>
</tr>
<tr>
<td valign="top">

*Thread ID*

</td>
<td valign="top">

Specify the value for Thread ID.

</td>
</tr>
<tr>
<td valign="top">

*Actor ID*

</td>
<td valign="top">

Specify the value for Actor ID.

</td>
</tr>
<tr>
<td valign="top">

*Channel ID*

</td>
<td valign="top">

Specify the value for Channel ID.

</td>
</tr>
<tr>
<td valign="top">

*Channel Account ID*

</td>
<td valign="top">

Specify the value for Channel Account ID.

</td>
</tr>
<tr>
<td valign="top">

*Definition ID*

</td>
<td valign="top">

Specify the value for Definition ID.

</td>
</tr>
<tr>
<td valign="top">

*Callback ID*

</td>
<td valign="top">

Specify the value for Callback ID.

</td>
</tr>
<tr>
<td valign="top">

*Function Type*

</td>
<td valign="top">

Specify the value for Function Type.

Example: `PRE_ACTION_EXECUTION`

</td>
</tr>
<tr>
<td valign="top">

*Function ID*

</td>
<td valign="top">

Specify the value for Function ID.

</td>
</tr>
<tr>
<td valign="top">

*Email ID*

</td>
<td valign="top">

Specify the value for Email ID.

</td>
</tr>
<tr>
<td valign="top">

*Creation Timestamp*

</td>
<td valign="top">

Specify the value for Timestamp Created.

Example: `2024-07-29T12:27:43.787Z`

</td>
</tr>
<tr>
<td valign="top">

*Campaign ID*

</td>
<td valign="top">

Specify the value for Campaign ID.

</td>
</tr>
<tr>
<td valign="top">

*Breakdown By*

</td>
<td valign="top">

Specify the value for Breakdown By.

Example: `sessions`

</td>
</tr>
<tr>
<td valign="top">

*Content Type*

</td>
<td valign="top">

Specify the value for Content Type.

Example: `standard-pages`

</td>
</tr>
<tr>
<td valign="top">

*Time Period*

</td>
<td valign="top">

Specify the value for Time Period.

Examples: `weekly`

</td>
</tr>
<tr>
<td valign="top">

*External Event ID*

</td>
<td valign="top">

Specify the value for External Event ID.

</td>
</tr>
<tr>
<td valign="top">

*Subscriber State*

</td>
<td valign="top">

Specify the value for Subscriber State.

Example: `REGISTERED`

</td>
</tr>
<tr>
<td valign="top">

*Token ID*

</td>
<td valign="top">

Specify the value for Token ID.

</td>
</tr>
<tr>
<td valign="top">

*VID*

</td>
<td valign="top">

Specify the value for VID of the contact.

> ### Note:  
> This is helpful for integrations that display contact data in other interfaces. The contact's unique ID is stored in the 'vid' field, which stands for 'visitor ID.'



</td>
</tr>
<tr>
<td valign="top">

*Offset*

</td>
<td valign="top">

Specify the value for offset as expected to the operation.

</td>
</tr>
<tr>
<td valign="top">

*Limit*

</td>
<td valign="top">

Specify the value for limit as expected for the operation.

</td>
</tr>
<tr>
<td valign="top">

*Property/Properties*

</td>
<td valign="top">

Specify the value for comma-separated values that are to be retrieved.

</td>
</tr>
<tr>
<td valign="top">

*Properties With History*

</td>
<td valign="top">

Specify the value for comma-separated values for which the history \(with timestamps\) should be retrieved.

</td>
</tr>
<tr>
<td valign="top">

*Query Parameters*

</td>
<td valign="top">

Specify comma-separated query parameters.

</td>
</tr>
<tr>
<td valign="top">

*Request Format*

</td>
<td valign="top">

Select the payload format of request body.

Example: *Application/XML*

</td>
</tr>
<tr>
<td valign="top">

*Response Format*

</td>
<td valign="top">

Select the payload format of response body.

Example: *Application/JSON*

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to send to the target system. By default, no custom headers are sent. Use an asterisk \(\*\) to send all custom headers to the target system. Alternatively, you can dynamically pass the values by defining a property that includes a list of headers.

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

